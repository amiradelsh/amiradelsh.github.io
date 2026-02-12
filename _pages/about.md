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
    <h2><strong>Hello, I'm</strong> AMIRADEL,</h2>
    <p style="text-align: justify;">
      
      Licensed architect with 3+ years of experience in solution-driven design, BIM-based collaboration, project management, and sustainability research. Proven track record in delivering BIM models up to LOD 350, conducting clash detection, and coordinating multidisciplinary workflows across architecture, structure, and MEP. Skilled in enhancing stakeholder engagement through immersive AR/VR/XR technologies and effective visual communication. Currently pursuing a second Master’s in Building Sustainability at TU Berlin, I’m seeking roles that intersect architecture, data-driven design, and climate innovation.
 </p>

  <p> 
  <a href="/assets/pdf/Amiradel_Shamshirgaran.pdf" download>
    <i class="fas fa-file-pdf" style="margin-right: 0.5em; color: #2f71d3;"></i>
    Download CV
  </a>
</p>
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

</div>