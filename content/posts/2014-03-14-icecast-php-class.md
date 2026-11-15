---
title: 'icecast php class'
author: ulysses

date: 2014-03-14
slug: icecast-php-class
draft: false
---

I modified an existing Icecast PHP class that I found online. I’ve added a couple of extra fields particularly the ‘status’ field where you’ll be able to determine if your Icecast server is streaming or not. I’ve initially set the status variable to ‘On Air’ and ‘Off Air.’ To use the class, take a look at the code below:

```
// include the class file
include( 'icecast.php' );

// instantiate class
$stream = new IceCast();

// set server and mount
$server = 'http://yourdomain.com:8001';
$file   = '/status.xsl?mount=/yourmount.ogg';

// set the url
$stream->setUrl($server,$file);

// get status info
$radio = $stream->getStatus();

// assign array to variables
extract($radio);

// echo the status
echo $status.'<br></br>';

// display more stats if ON AIR
if ($status=='ON AIR') :
echo $listeners.' listeners<br></br>';
echo $most_listeners.' max listeners<br></br>';
endif;
```

Here’s the Icecast class.

```
class IceCast {
    var $server = "http://yourdomain.com:8001";
    var $stats_file = "/status.xsl?mount=/yourmount.ogg";
    var $radio_info=array();

    function __construct() {
        // build array to store our Icecast stats   
        $this->radio_info['server'] = $this->server;
        $this->radio_info['title'] = '';
        $this->radio_info['description'] = '';
        $this->radio_info['content_type'] = '';
        $this->radio_info['mount_start'] = '';
        $this->radio_info['bit_rate'] = '';
        $this->radio_info['listeners'] = '';
        $this->radio_info['most_listeners'] = '';
        $this->radio_info['genre'] = '';
        $this->radio_info['url'] = '';
        $this->radio_info['now_playing'] = array();
        $this->radio_info['now_playing']['artist'] = 'Unknown';
        $this->radio_info['now_playing']['track'] = 'Unknown';
        $this->radio_info['status'] = 'OFF AIR';
    }

    function setUrl($url,$file) {
        $this->server=$url;
        $this->stats_file=$file;
        $this->radio_info['server'] = $this->server;
    }

    private function fetch() {
        // create a new curl resource
        $ch = curl_init();

        // set the url
        curl_setopt($ch,CURLOPT_URL,$this->server.$this->stats_file);

        // return as a string
        curl_setopt($ch,CURLOPT_RETURNTRANSFER,1);

        // $output = the status.xsl file
        $output = curl_exec($ch);

        // close curl resource to free up system resources
        curl_close($ch);

        return $output;
    }

    function getStatus() {
        $output=$this->fetch();

        // loop through $output and sort arrays
        $temp_array = array();

        $search_for = "<td>]*class=\"streamdata\">(.*)";
        $search_td = array('</td><td class="streamdata">','</td>');

        if(preg_match_all("/$search_for/siU",$output,$matches)) {
           foreach($matches[0] as $match) {
              $to_push = str_replace($search_td,'',$match);
              $to_push = trim($to_push);
              array_push($temp_array,$to_push);
           }
        }

        if(count($temp_array)) {
            //sort our temp array into our ral array
            $this->radio_info['title'] = $temp_array[0];
            $this->radio_info['description'] = $temp_array[1];
            $this->radio_info['content_type'] = $temp_array[2];
            $this->radio_info['mount_start'] = $temp_array[3];
            $this->radio_info['bit_rate'] = $temp_array[4];
            $this->radio_info['listeners'] = $temp_array[5];
            $this->radio_info['most_listeners'] = $temp_array[6];
            $this->radio_info['genre'] = $temp_array[7];
            $this->radio_info['url'] = $temp_array[8];

            if(isset($temp_array[9])) {
                $x = explode(" - ",$temp_array[9]);
                $this->radio_info['now_playing']['artist'] = $x[0];
                $this->radio_info['now_playing']['track'] = $x[1];
            }
            $this->radio_info['status'] = 'ON AIR';
        
        }
        return $this->radio_info;
        }

}
```