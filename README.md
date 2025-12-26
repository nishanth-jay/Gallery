# Ex.07 Design of Interactive Image Gallery
# Date:16-12-2025
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
gallery.html

<!DOCTYPE html>
<html>
<head>
  <title>Interactive Image Gallery</title>

  <!-- CSS -->
  <style>
    body{
      font-family: Arial, sans-serif;
      background: #f3f3f3;
      margin: 0;
      padding: 20px;
      text-align: center;
    }

    h1{
      color: #333;
    }

    .gallery-container{
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
      max-width: 1000px;
      margin: auto;
    }

    .image-card{
      position: relative;
      overflow: hidden;
      border-radius: 12px;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
      transition: transform .3s;
    }

    .image-card img{
      width: 100%;
      height: 250px;
      object-fit: cover;
      transition: transform .3s;
    }

    .image-card:hover{
      transform: scale(1.03);
    }

    .image-card:hover img{
      transform: scale(1.1);
    }

    /* Preview Modal */

    .preview-modal{
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,.8);
      justify-content: center;
      align-items: center;
    }

    .preview-box{
      background: white;
      padding: 15px;
      border-radius: 10px;
    }

    .preview-box img{
      width: 600px;
      max-width: 90vw;
      border-radius: 10px;
    }

    .close-btn{
      margin-top: 10px;
      padding: 8px 16px;
      border: none;
      background: crimson;
      color: white;
      border-radius: 8px;
      cursor: pointer;
    }
  </style>
</head>

<body>

<h1>Interactive Image Gallery</h1>

<div class="gallery-container">

  <div class="image-card" onclick="showPreview('https://picsum.photos/id/1015/800/600')">
    <img src="https://picsum.photos/id/1015/400/300">
  </div>

  <div class="image-card" onclick="showPreview('https://picsum.photos/id/1024/800/600')">
    <img src="https://picsum.photos/id/1024/400/300">
  </div>

  <div class="image-card" onclick="showPreview('https://picsum.photos/id/1035/800/600')">
    <img src="https://picsum.photos/id/1035/400/300">
  </div>

  <div class="image-card" onclick="showPreview('https://picsum.photos/id/1041/800/600')">
    <img src="https://picsum.photos/id/1041/400/300">
  </div>

  <div class="image-card" onclick="showPreview('https://picsum.photos/id/1050/800/600')">
    <img src="https://picsum.photos/id/1050/400/300">
  </div>

</div>

<!-- Modal Preview -->
<div class="preview-modal" id="previewModal">
  <div class="preview-box">
    <img id="previewImage">
    <br>
    <button class="close-btn" onclick="closePreview()">Close</button>
  </div>
</div>

<!-- JavaScript -->
<script>
  function showPreview(src){
    document.getElementById("previewImage").src = src;
    document.getElementById("previewModal").style.display = "flex";
  }

  function closePreview(){
    document.getElementById("previewModal").style.display = "none";
  }
</script>

</body>
</html>
```
```
urls.py

from django.urls import path
from pictures import views

urlpatterns = [
    path('', views.image_gallery, name="image_gallery"),
]
```
```
views.py

from django.shortcuts import render

def image_gallery(request):
    return render(request, "gallery.html")
```
# OUTPUT:
![alt text](<Screenshot 2025-12-26 203356.png>)
# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
