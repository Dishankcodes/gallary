<!DOCTYPE html>
<html>
<head>
    <title>Image Preview</title>
    <style>
        #image {
            width: 500px;
            height: 300px;
            border: 1px solid black;
            text-align: center;
            line-height: 300px;
            font-size: 20px;
            background-color: #f0f0f0;
            background-size: cover;
        }
        .preview {
            width: 100px;
            height: 100px;
            margin: 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
<center>
    <div id="image">Hover over an image below to display here.</div>
    <img class="preview" src="skyblue.png" alt="Sky Blue" onmouseover="upDate(this)" onmouseout="undo()">
    <img class="preview" src="purple.png" alt="Purple" onmouseover="upDate(this)" onmouseout="undo()">
    <img class="preview" src="maroon.png" alt="Maroon" onmouseover="upDate(this)" onmouseout="undo()">

    <script>
        // Function to update the image preview
        function upDate(previewPic) {
            console.log("Event triggered");
            console.log("Alt text: " + previewPic.alt);
            console.log("Source: " + previewPic.src);
            document.getElementById("image").innerText = previewPic.alt;
            document.getElementById("image").style.backgroundImage = "url('" + previewPic.src + "')";
            console.log("Background image updated to: " + previewPic.src);
        }

        // Function to reset the image preview
        function undo() {
            document.getElementById("image").style.backgroundImage = "url('')";
            document.getElementById("image").innerText = "Hover over an image below to display here.";
            console.log("Background image and text reset to original state.");
        }
    </script>
</body>
</html>
