---
author: ulysses
title: 'file upload'
date: 2025-12-02
slug: file-upload
draft: false
---
I created a page for uploading file using HTML, PHP, CSS and Javascript.

- HTML displays the page
- PHP handles the input form
- Javascript displays the upload status
- CSS provides styling and spinning status
- Using the Roboto Google font

In addition, I also had to tweak the /etc/php.ini settings to allow upload of large files.

```
file_uploads = On
upload_max_filesize = 200M
post_max_size = 200M
max_file_uploads = 20
```

Here's the code all wrapped in a single file.

```
<html>
<head>
<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');
body {
   font-family: Roboto, sans-serif;
   font-optical-sizing: normal;
   font-weight: 400;
   font-style: normal;
   background-color: #222;
   color: #000;
}
.content {
   width: 1080px;
   margin: 20px auto;
   padding: 20px;
   background-color: #fff;
   min-height: 90vh;
}
.loader {
  border: 5px solid #f3f3f3; /* Light grey */
  border-top: 5px solid #3498db; /* Blue */
  border-radius: 50%;
  width: 40px;
  height: 40px;
  animation: spin 2s linear infinite;
  display: none; /* Hide loader by default */
  margin-left: 10px;
}
@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
hr {
  border: 1px solid #777;
}
</style>
</head>
<body>
<div class="content">
<h3>Upload Files:</h3>
<ol>
<li>Click on the "Choose Files" button.</li>
<li>You can select one or multiple files to upload.</li>
<li>Once files are selected, click on the Upload button to begin the upload process.</li>
<li>Depending on file size(s), the upload process could take a few seconds to a few minutes. Please be patient.</li>
<li>If uploads are successful, there will be a message saying 'files uploaded successfully.'</li>
</ol>
<form id="uploadForm" action="" method="post" enctype="multipart/form-data">
    <label>Select files to upload:</label>
    <input id="fileInput" type="file" name="files[]" multiple required>
    <button type="submit">Upload</button>
</form>
<div class="loader" id="loader"></div>
<?php
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $uploadDir = 'uploads/';
    // Ensure the directory exists
    if (!is_dir($uploadDir)) {
        mkdir($uploadDir, 0755, true);
    }
    // Check if files were uploaded
    if (isset($_FILES['files'])) {
        $totalFiles = count($_FILES['files']['name']);
        for ($i = 0; $i < $totalFiles; $i++) {
            if ($_FILES['files']['error'][$i] === UPLOAD_ERR_OK) {
                $fileName = basename($_FILES['files']['name'][$i]);
                $targetFile = $uploadDir . $fileName;
                if (move_uploaded_file($_FILES['files']['tmp_name'][$i], $targetFile)) {
                    echo "File uploaded successfully: " . htmlspecialchars($fileName) . "<br>";
                } else {
                    echo "Error uploading file: " . htmlspecialchars($fileName) . "<br>";
                }
            } else {
                echo "Error with file: " . htmlspecialchars($_FILES['files']['name'][$i]) . "<br>";
            }
        }
    } else {
        echo "No files uploaded.";
    }
}
?>
<script>
document.getElementById('uploadForm').addEventListener('submit', function() {
    // Show loader when form is submitted
    document.getElementById('loader').style.display = 'block';
});
</script>
<h3>Upload More Files:</h3>
<p><button onclick="document.location='upload.php'">Reload Page To Start Another Upload</button></p>
</div>
</body>
</html>
```

