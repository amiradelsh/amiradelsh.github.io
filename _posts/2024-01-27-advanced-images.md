---
layout: post
title: a post with advanced image components
date: 2024-01-27 11:46:00
description: this is what advanced image components could look like
tags: formatting images
categories: sample-posts
thumbnail: assets/img/9.jpg
images:
  compare: true
  slider: true
---

This is an example post with advanced image components.

## Image Slider

This is a simple image slider. It uses the [Swiper](https://swiperjs.com/) library. Check the [examples page](https://swiperjs.com/demos) for more information of what you can achieve with it.

<swiper-container keyboard="true" navigation="true" pagination="true" pagination-clickable="true" pagination-dynamic-bullets="true" rewind="true">
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/9.jpg" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/7.jpg" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/8.jpg" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/10.jpg" class="img-fluid rounded z-depth-1" %}</swiper-slide>
  <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/14.jpg" class="img-fluid rounded z-depth-1" %}</swiper-slide>
</swiper-container>

## Image Comparison Slider

This is a simple image comparison slider. It uses the [img-comparison-slider](https://img-comparison-slider.sneas.io/) library. Check the [examples page](https://img-comparison-slider.sneas.io/examples.html) for more information of what you can achieve with it.

<img-comparison-slider>
  {% include figure.liquid path="assets/img/prof_pic.jpg" class="img-fluid rounded z-depth-1" slot="first" %}
  {% include figure.liquid path="assets/img/prof_pic_color.png" class="img-fluid rounded z-depth-1" slot="second" %}
</img-comparison-slider>




<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>Swiper Demo</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  
  <!-- Swiper CSS -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css" />
  
  <style>
    /* Ensure white background */
    html, body {
      position: relative;
      height: 100%;
      margin: 0;
      padding: 0;
      background: #fff; /* Changed from #eee (gray) to #fff (white) */
      font-family: Helvetica, Arial, sans-serif;
    }

    /* Swiper Container */
    .swiper {
      width: 100%;
      max-width: 1200px;
      height: calc(100vw * 9 / 16);
      max-height: 600px;
      margin: auto;
    }

    /* Swiper Slides */
    .swiper-slide {
      display: flex;
      justify-content: center;
      align-items: center;
      background: #fff;
      position: relative;
    }

    /* Slide Images */
    .swiper-slide img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    /* Caption Styling */
    .caption {
      position: absolute;
      bottom: 10px;
      left: 10px;
      background: rgba(0, 0, 0, 0.6);
      color: #fff;
      padding: 5px 10px;
      font-size: 14px;
      border-radius: 5px;
    }

    /* Navigation Arrows */
    .swiper-button-next, .swiper-button-prev {
      color: #000; /* Changed from white to black for visibility */
    }

    /* Pagination Bullets */
    .swiper-pagination-bullet {
      border: 1px solid #000; /* Added border for visibility */
      background: rgba(0, 0, 0, 0.5); /* Darker bullets */
    }

    .swiper-pagination-bullet-active {
      background: #000; /* Active bullet is solid black */
    }
  </style>
</head>
<body>

  <!-- Swiper Slider -->
  <div class="swiper mySwiper">
    <div class="swiper-wrapper">
      <div class="swiper-slide">
        <img src="/assets/img/1.jpg" alt="Slide 1">
        <div class="caption">Caption for Slide 1</div>
      </div>
      <div class="swiper-slide">
        <img src="/assets/img/2.jpg" alt="Slide 2">
        <div class="caption">Caption for Slide 2</div>
      </div>
      <div class="swiper-slide">
        <img src="/assets/img/3.jpg" alt="Slide 3">
        <div class="caption">Caption for Slide 3</div>
      </div>
      <div class="swiper-slide">
        <img src="/assets/img/4.jpg" alt="Slide 4">
        <div class="caption">Caption for Slide 4</div>
      </div>
      <div class="swiper-slide">
        <img src="/assets/img/14.jpg" alt="Slide 5">
        <div class="caption">Section of the complex from left</div>
      </div>
    </div>
    
    <!-- Navigation & Pagination -->
    <div class="swiper-button-next"></div>
    <div class="swiper-button-prev"></div>
    <div class="swiper-pagination"></div>
  </div>

  <!-- Swiper JS -->
  <script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>
  <script>
    var swiper = new Swiper(".mySwiper", {
      spaceBetween: 30,
      centeredSlides: true,
      autoplay: { delay: 2500, disableOnInteraction: false },
      pagination: { el: ".swiper-pagination", clickable: true },
      navigation: { nextEl: ".swiper-button-next", prevEl: ".swiper-button-prev" },
    });
  </script>

</body>
</html>