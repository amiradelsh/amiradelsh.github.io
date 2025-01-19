---
layout: page
title: Project 2
description: A project with a background image
img: /assets/img/11.jpg
importance: 2
category: BIM
related_publications: true
---

<!-- Project Header with Background Image -->
<div class="project-header" style="background-image: url('{{ page.img }}');">
  <div class="overlay"></div>
  <div class="header-content">
    <h1>{{ page.title }}</h1>
    <p>{{ page.description }}</p>
  </div>
</div>

<!-- Project Images in a Clean Grid Layout -->
<div class="container mt-5">
  <div class="row">
    <div class="col-sm mt-3 mt-md-0">
      {% include figure.liquid path="assets/img/1.jpg" title="Example Image 1" class="img-fluid rounded" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
      {% include figure.liquid path="assets/img/3.jpg" title="Example Image 2" class="img-fluid rounded" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
      {% include figure.liquid path="assets/img/5.jpg" title="Example Image 3" class="img-fluid rounded" %}
    </div>
  </div>
  
  <!-- Caption for Images -->
  <div class="caption mt-4">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
  </div>

  <!-- Another Row of Images -->
  <div class="row">
    <div class="col-sm mt-3 mt-md-0">
      {% include figure.liquid path="assets/img/5.jpg" title="Example Image 4" class="img-fluid rounded" %}
    </div>
  </div>

  <div class="caption mt-4">
    This image can also have a caption. It's like magic.
  </div>

  <!-- Text Between Images -->
  <div class="project-description mt-5">
    <p>Say you wanted to write a bit about your project before you posted the rest of the images. You describe how you toiled, sweated, <em>bled</em> for your project, and then... you reveal its glory in the next row of images.</p>
  </div>

  <!-- Final Row with Styled Images -->
  <div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
      {% include figure.liquid path="assets/img/6.jpg" title="Example Image 5" class="img-fluid rounded" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
      {% include figure.liquid path="assets/img/11.jpg" title="Example Image 6" class="img-fluid rounded" %}
    </div>
  </div>

  <div class="caption mt-4">
    You can also have artistically styled 2/3 + 1/3 images, like these.
  </div>
</div>

<style>
/* Minimal Styling for the Project Page */

/* Background Header */
.project-header {
  position: relative;
  background-size: cover;
  background-position: center;
  padding: 100px 0;
  color: white;
  text-align: center;
}

.project-header .overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}

.project-header .header-content {
  position: relative;
  z-index: 1;
}

.project-header h1 {
  font-size: 3rem;
  margin-bottom: 20px;
}

.project-header p {
  font-size: 1.5rem;
}

/* Image Gallery */
.img-fluid {
  width: 100%;
  height: auto;
}

.caption {
  font-size: 1rem;
  color: #555;
  text-align: center;
  margin-top: 15px;
}

.project-description {
  font-size: 1rem;
  margin: 30px 0;
  color: #333;
}

/* Mobile Responsiveness */
@media (max-width: 768px) {
  .project-header h1 {
    font-size: 2rem;
  }

  .project-header p {
    font-size: 1rem;
  }

  .row {
    display: block;
  }

  .row .col-sm {
    width: 100%;
    margin-bottom: 20px;
  }
}
</style>
