---
layout: default
title: Yolanda Zhou - Portfolio
permalink: /projects/
---

<div class="gallery-container">
<div class="project-gallery">
    {% for project in site.projects %}
      {% if project.in_main %}
        <div class="gallery-item">
          <a href="{{ project.url | relative_url }}">
            <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
            <p>{{ project.title}}</p>
          </a>
        </div>
      {% endif %}
    {% endfor %}
</div>
</div>