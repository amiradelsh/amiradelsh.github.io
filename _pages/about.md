---
layout: default
title: Home
permalink: /

# Optional metadata for social media
meta_description: "Welcome to Amiradel's personal homepage."
meta_keywords: "portfolio, minimalist, Amiradel, modern design"
---

<head>
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700&display=swap" rel="stylesheet">
  
  <!-- Add your custom styles -->
  <style>
    /* General Styling */
    body {
      font-family: 'Montserrat', sans-serif;
      font-size: 16px;
      color: #333;
      margin: 0;
      padding: 0;
    }

    h1, h2 {
      font-weight: 500;
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

    /* Project Section */
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
      .project-card {
        flex: 1 1 100%;
        max-width: 100%;
      }
    }
  </style>
</head>

<!-- Hero Section -->
<div class="hero-section">
  <img src="assets/img/facebook.png" alt="Amiradel's Logo" class="logo">
  <div class="text-content">
    <h1>Amiradel Shamshirgaran</h1>
    <p>
      Licensed architect and project manager with over 4 years of experience in solution-driven architectural design, BIM-based collaboration, visual presentations, and sustainability research.
    </p>
    <p>
      Feel free to reach out at <a href="mailto:shamshirgaran@campus.tu-berlin.de">shamshirgaran@campus.tu-berlin.de</a>.
    </p>
  </div>
</div>

<!-- Projects Section -->
<div class="projects-section">

  <!-- BIM Projects -->
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
    <h2>Graphics Projects</h2>
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

</div>
