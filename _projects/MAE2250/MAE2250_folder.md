---
layout: project_folder
title: MAE 2250 Folder (SP 2026)
permalink: /projects/MAE2250/
image: /assets/images/2250_first_prototype_cad.png
folder: MAE2250
in_main: true
---
Check out:
- our group's pitch to the Cornell CALS clients: [Client Pitch]({{ '/projects/MAE2250/client-outline/' | relative_url }})

- our first prototype: [Functional Prototype]({{ '/projects/MAE2250/functional-prototype/' | relative_url }})

- our client report: [Client Report]({{ '/projects/MAE2250/client-report/' | relative_url }})

<!-- <h1>{{ page.title }}</h1>
{% if page.image %}
<img src="{{ page.image }}" alt="{{ page.title }}" style="max-width:300px; margin-bottom:20px;">
{% endif %}

<div>{{ content }}</div> -->

<!-- <h2>Child Files</h2>
<ul>
{% assign current_folder = page.path | split: '/' | slice: 1,1 | first %}
{% for file in site.projects %}
  {% assign file_folder = file.path | split: '/' | slice: 1,2 | first %}
  <li> {{file.url}}</li> -->
  <!-- <li> {{ file.title | default: file.name | replace: '.md', '' }} </li> -->
  <!-- {% if file_folder == current_folder and file.url != page.url %}
    <li> true </li>
    <li>  {{file.basename}}</li>
    <li><a href="{{ file.url }}">{{ file.title | default: file.basename }}</a></li>
  {% endif %}
{% endfor %}
</ul> -->

<!-- <h2>Debug Child Files</h2>
<ul>
{% for file in site.projects %}
  {% assign file_folder = file.path | split: '/' | slice: 1,1 | first %}
  <li>
    {{ file.title }} - {{ file.path }} - file_folder: {{ file_folder }} | current_folder: {{ folder_name }}
  </li>
{% endfor %}
</ul> -->