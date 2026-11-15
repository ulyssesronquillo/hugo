---
title: 'ajax live search'
author: ulysses

date: 2022-05-22
slug: ajax-live-search
draft: false
---

Just implemented an Ajax live search on a website.

Here’s the search page. Results are displayed in div output.

```
<script src="https://code.jquery.com/jquery-3.4.1.js"></script>
<script type="text/javascript">
$(document).ready(function(){
    $("#search").keyup(function(){
        var query = $(this).val();
        if (query != "") {
        $.ajax({
            url: 'links-ajax.php',
            method: 'POST',
            data: {query:query},
            success: function(data){
            $('#output').html(data);
            $('#output').css('display', 'block');
            $("#output a").on("click", function(){
                $("#output").val($(this).html());
            });
            $("#search").focusout(function(){
                window.setTimeout(function() {
                $('#output').css('display', 'none');
                }, 500);
            });
            $("#search").focusin(function(){
                $('#output').css('display', 'block');
            });
            }
        });
        } else {
        $('#output').css('display', 'none');
    }
    });
});
</script>

<div class="form-row">
    <div class="col">
        <input autocomplete="off" class="form-control form-control-success" id="search" name="search" placeholder="Search here...." type="text"></input>
    </div>
</div>
<div id="output"></div>
```

Here’s the links-ajax.php which display the search results with links.

```
<?php $servername='localhost';
$username='';
$password='';
$dbname = "";
$conn=mysqli_connect($servername,$username,$password,"$dbname");
if(!$conn) { die('Could not Connect MySql Server:' .mysql_error()); }
if (isset($_POST['query'])) {
    $query = <<<"SQL
                 SELECT * FROM links WHERE `name` LIKE '%{$_POST['query']}%' 
                 OR `url` LIKE '%{$_POST['query']}%' 
                 OR `tag` LIKE '%{$_POST['query']}%' 
                 ORDER BY name ASC, url ASC"
             SQL;
    $result = mysqli_query($conn, $query);
    if (mysqli_num_rows($result) ?> 0) {
        while ($user = mysqli_fetch_array($result)) {
            echo "<a rel="noopener" target="_blank">".$user['name']."</a><br></br>";
        }
    } else {
        echo "<p style="color:red">No results found...</p>";
    }
}
?>
```

I couldn’t get the links working, until I added the 500ms of timeout in .focusout.