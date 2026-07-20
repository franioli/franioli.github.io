---
layout: about
title: about
permalink: /
subtitle: Post-doctoral Researcher in Geomatics @ <a href='https://www.dica.polimi.it/' target='_blank'>Politecnico di Milano</a> 

profile:
  align: right
  image: prof_pic.jpg
  image_circular: true # crops the image to make it circular
  more_info: >
    <p>Dept. of Civil and Environmental Engineering</p>
    <p>Politecnico di Milano</p>
    <p>Milan, Italy</p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

<!-- Page-scoped styles: the theme's Tailwind build is pruned, so custom layout
     classes are defined here and use the theme's --global-* variables so that
     light and dark mode both work. -->
<style>
  .focus-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin: 1.5rem 0 2rem;
    padding: 0;
    list-style: none;
  }

  .focus-tags li {
    padding: 0.25rem 0.75rem;
    font-size: 0.85rem;
    line-height: 1.6;
    color: var(--global-text-color-light);
    background-color: var(--global-card-bg-color);
    border: 1px solid var(--global-divider-color);
    border-radius: 999px;
    transition: color 0.2s ease, border-color 0.2s ease;
  }

  .focus-tags li:hover {
    color: var(--global-theme-color);
    border-color: var(--global-theme-color);
  }
</style>

I am a post-doctoral researcher in Geomatics at the [Dept. of Civil and Environmental Engineering](https://www.dica.polimi.it/) of [Politecnico di Milano](https://www.polimi.it/), where I work on **photogrammetry and computer vision for environmental monitoring**. I currently lead the image-based monitoring work of the **MOHYCAM** project, tackling hydrogeological hazards at the **Belvedere Glacier** (Monte Rosa).


My research spans multi-scale 4D monitoring — from low-cost terrestrial time-lapse cameras for high-frequency glacier dynamics to satellite multi-view stereo for regional mass-balance studies. Before returning to Politecnico di Milano I was a post-doc at [CNR IRPI](https://www.irpi.cnr.it/) in Turin, working on glacier-instability risk at the Planpincieux Glacier (Mont Blanc), and at the University of Zurich. I earned my PhD here in 2024, _cum laude_.

I am a firm believer in **open science** and actively build open-source tools. Off the screen I am a certified UAV pilot with a background in topographic surveying, and I spend most of my free time in the mountains — which is probably why I ended up working on glaciers.

<ul class="focus-tags">
  <li>Photogrammetry</li>
  <li>Image matching</li>
  <li>3D reconstruction</li>
  <li>Deep learning</li>
  <li>Glacier monitoring</li>
  <li>UAV &amp; time-lapse</li>
  <li>HPC</li>
</ul>

## code &amp; tools

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo.liquid repository="3DOM-FBK/deep-image-matching" %}
  {% include repository/repo.liquid repository="franioli/icepy4d" %}
  {% include repository/repo.liquid repository="3DOM-FBK/COLMAP_SLAM" %}
</div>
