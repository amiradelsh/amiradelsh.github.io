---
layout: default
title: Home
permalink: /
meta_description: "Welcome to Amiradel's personal homepage."
meta_keywords: "portfolio, minimalist, Amiradel, modern design"
---

<head>
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;700&family=Inter:wght@400;600&display=swap" rel="stylesheet">
  
  <!-- Add your custom styles -->
  <style>
    /* General Styling */
    body {
  font-family: "Inter", sans-serif;
  color: #333;
  margin: 0;
  padding: 0;
}

h1, h2, h3, .hero-title {
  font-family: "Space Grotesk", sans-serif;
  font-weight: 700;

}

    a {
      color: #0077cc;
      text-decoration: none;
    }

    a:hover {
      text-decoration: none;
    }

    /* Hero Section */
    .hero-section {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      padding: 20px;
    }

    .logo {
      width: 160px;
      margin-bottom: 20px;
    }

    .text-content {
      max-width: 600px;
    }

    /* Section with image and text */
    .section-with-image {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 40px 20px;
    }

    .text-left {
      flex: 1;
      padding-right: 40px;
    }

    .text-left h2 {
      font-size: 2em;
      font-weight: Bold;
    }

    .text-left p {
      font-size: 1.1em;
      color: #555;
    }

    .image-right {
      flex: 1;
      max-width: 50%;
    }

    .image-right img {
      width: 100%;
      height: auto;
      border-radius: 12px;
      object-fit: cover;
    }

    /* Projects Section */
    .projects-section {
      padding: 40px 20px;
    }

    .projects {
      margin-bottom: 40px;
    }

    .projects h2 {
      font-size: 1.8em;
      margin-bottom: 20px;
    }

    .project-container {
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
    }

    .project-card {
      flex: 1 1 calc(33.333% - 20px);
      max-width: calc(33.333% - 20px);
      position: relative;
      border-radius: 0px;
      overflow: hidden;
      background-color: #f8f8f8;
    }

    .project-card img {
      width: 100%;
      aspect-ratio: 1 / 1;
      object-fit: cover;
    }

    .project-caption {
      padding: 0px;
      background-color: rgba(255, 255, 255, 0.8);
      text-align: left;
    }

    .project-caption p {
      margin: 0px 0;
    }

    .project-title {
      font-weight: bold;
      font-size: 1rem;
    }

    .project-description {
      font-size: 0.85rem;
      color: #555;
    }

    @media (max-width: 768px) {
      .section-with-image {
        flex-direction: column;
        text-align: center;
      }

      .image-right {
        max-width: 100%;
        margin-top: 20px;
      }

      .text-left {
        padding-right: 20;
      }

      .project-card {
        flex: 1 1 100%;
        max-width: 100%;
      }
    }
  </style>
</head>


<!-- Section with image on the right and text on the left -->
<div class="section-with-image">
  <div class="text-left">
    <h2><strong>Hallo, I'm</strong> AMIRADEL,</h2>
    <p style="text-align: justify;">
      
I'm an architect based in Berlin with a Master’s degree in Construction Management. Over the years, I've worked in various areas, from sketching building designs and coordinating construction teams to using BIM tools for efficient project workflows, and now exploring sustainable building practices through my Master’s degree in Building Sustainability at TU Berlin.
<br>
This site showcases a range of my work across architecture, BIM coordination, visual arts, and research publications, reflecting experience from practical site work to technology-driven design and sustainability assessment.
<br>
I’m open to opportunities in Berlin and beyond.

<!-- Social Links -->
<div style="margin-top:20px; display:flex; gap:20px; justify-content:flex-start;">

  <!-- LinkedIn -->
  <a href="https://www.linkedin.com/in/amiradelshamshirgaran/" target="_blank">
    <svg width="22" height="22" viewBox="0 0 24 24" fill="#333">
      <path d="M19 0h-14c-2.76 0-5 2.24-5 5v14c0 2.76 2.24 5 5 5h14c2.76 0 5-2.24 5-5v-14c0-2.76-2.24-5-5-5zm-11 19h-3v-10h3v10zm-1.5-11.25c-.966 0-1.75-.784-1.75-1.75s.784-1.75 1.75-1.75 1.75.784 1.75 1.75-.784 1.75-1.75 1.75zm13.5 11.25h-3v-5.5c0-3.299-4-3.05-4 0v5.5h-3v-10h3v1.528c1.396-2.586 7-2.777 7 2.476v6.996z"/>
    </svg>
  </a>

  <!-- Gmail -->
  <a href="mailto:amiradel.shamshirgaran@gmail.com
">
    <svg width="22" height="22" viewBox="0 0 24 24" fill="#333">
      <path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4-8 5-8-5V6l8 5 8-5v2z"/>
    </svg>
  </a>

</div>

 </p>
<!--
  <p> 
  <a href="/assets/pdf/Amiradel_Shamshirgaran.pdf" download>
    <i class="fas fa-file-pdf" style="margin-right: 0.5em; color: #2f71d3;"></i>
    Download CV
  </a>
</p>
-->
  </div>
  <div class="image-right">
    <img src="assets/img/UrbanFuture.jpg" alt="About Me Image" />
  </div>
</div>



  <!-- BIM Projects ß-->
  <div class="projects">
    <h2>BIM Projects</h2>
    <div class="project-container">
      {% assign bim_projects = site.projects | where: "category", "BIM" %}
      {% for project in bim_projects %}
      <a href="{{ project.url }}" class="project-card">
        <img src="{{ project.img }}" alt="{{ project.title }}">
        <div class="project-caption">
          <p class="project-title">{{ project.title }}</p>
          <p class="project-description">{{ project.description }}</p>
        </div>
      </a>
      {% endfor %}
    </div>
  </div>

  <!-- Architecture Projects -->
  <div class="projects">
    <h2>Architecture Projects</h2>
    <div class="project-container">
      {% assign architecture_projects = site.projects | where: "category", "Architecture" %}
      {% for project in architecture_projects %}
      <a href="{{ project.url }}" class="project-card">
        <img src="{{ project.img }}" alt="{{ project.title }}">
        <div class="project-caption">
          <p class="project-title">{{ project.title }}</p>
          <p class="project-description">{{ project.description }}</p>
        </div>
      </a>
      {% endfor %}
    </div>
  </div>

  <!-- Graphics Projects -->
  <div class="projects">
    <h2>Visual Designs</h2>
    <div class="project-container">
      {% assign graphics_projects = site.projects | where: "category", "Graphics" %}
      {% for project in graphics_projects %}
      <a href="{{ project.url }}" class="project-card">
        <img src="{{ project.img }}" alt="{{ project.title }}">
        <div class="project-caption">
          <p class="project-title">{{ project.title }}</p>
          <p class="project-description">{{ project.description }}</p>
        </div>
      </a>
      {% endfor %}
    </div>
  </div>


 <!-- Publications -->
  <div class="projects">
    <h2>Publications</h2>
    <div class="project-container">
      {% assign graphics_projects = site.projects | where: "category", "Publication" %}
      {% for project in graphics_projects %}
      <a href="{{ project.url }}" class="project-card">
        <img src="{{ project.img }}" alt="{{ project.title }}">
        <div class="project-caption">
          <p class="project-title">{{ project.title }}</p>
          <p class="project-description">{{ project.description }}</p>
        </div>
      </a>
      {% endfor %}
    </div>
  </div>