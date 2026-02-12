---
layout: page
title: Architecture
permalink: /Architecture/
description:
nav: true
nav_order: 2
display_categories: [Architecture]
horizontal: false
---

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;700&family=Inter:wght@400;600&display=swap" rel="stylesheet">


<!-- pages/projects.md -->
<div class="projects">
  {% if site.enable_project_categories and page.display_categories %}
    <!-- Display categorized projects -->
    {% for category in page.display_categories %}
      <a id="{{ category }}" href=".#{{ category }}">
        <h2 class="category">{{ category }}</h2>
      </a>
      {% assign categorized_projects = site.projects | where: "category", category %}
      {% assign sorted_projects = categorized_projects | sort: "importance" %}
      <div class="container">
        <div class="row">
          {% for project in sorted_projects %}
            <div class="col-12 col-md-4 mb-4">
              <!-- Project Card -->
              <div class="project-card">
                <a href="{{ project.url }}">
                  <div class="project-image">
                    <!-- Background Image (force square aspect ratio) -->
                    <img src="{{ project.img }}" alt="{{ project.title }}" class="img-fluid square-img">
                  </div>
                </a>
                <!-- Left-aligned title and caption under the image -->
                <div class="project-caption">
                  <p class="project-title">{{ project.title }}</p>
                  <p class="project-description">{{ project.description }}</p>
                </div>
              </div>
            </div>
          {% endfor %}
        </div>
      </div>
    {% endfor %}
  {% endif %}
</div>

<style>
/* Full-width container */
.projects .container {
  padding: 0 15px;
}

.project-card {
  position: relative;
}

/* Project image - Force square aspect ratio */
.project-image {
  position: relative;
  padding-top: 100%; /* Makes the container square by setting the padding based on the width */
  overflow: hidden;
}

.project-image img.square-img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover; /* Ensures the image covers the square area */
}

/* Left-aligned caption styling */
.project-caption {
  background-color: rgba(255, 255, 255, 0.8); /* Light background with opacity */
  padding: 5px 10px;
  font-size: 0.75rem; /* Very small font size */
  color: #333; /* Dark text color */
  margin-top: 8px; /* Space between image and caption */
  border-radius: 5px; /* Rounded corners for the background */
  text-align: left; /* Align text to the left */
}

/* Title styling */
.project-caption .project-title {
  font-weight: bold; /* Bold for the title */
  margin-bottom: 3px; /* Space between title and description */
  font-size: 1rem; /* Slightly larger font for the title */
}

/* Description styling */
.project-caption .project-description {
  font-size: 0.75rem; /* Smaller font for the description */
}

/* Adjustments for mobile responsiveness */
@media (max-width: 767px) {
  .project-caption {
    font-size: 0.7rem; /* Smaller font on mobile */
  }
}
body {
  font-family: "Inter", sans-serif;
  color: #333;
  margin: 0;
  padding: 0;
}

h1, h2, h3, .project-title {
  font-family: "Space Grotesk", sans-serif;
  font-weight: 700;
}

/* Keep your existing styles */
.projects .container {
  padding: 0 15px;
}
</style>
