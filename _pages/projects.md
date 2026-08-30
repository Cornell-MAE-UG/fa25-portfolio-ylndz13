---
layout: default
title: Yolanda Zhou - Portfolio
permalink: /projects/
---

<div class="timeline">

{% for project in site.projects %}
{% if project.in_main %}

<div class="timeline-item {% cycle 'left','right' %}">

    <div class="timeline-dot"></div>

    <a class="timeline-card" href="{{ project.url | relative_url }}">

        <img src="{{ project.image | relative_url }}"
             alt="{{ project.title }}">

        <div class="timeline-content">

            <span class="timeline-date">
                {{ project.timeline }}
            </span>

            <h2>{{ project.title }}</h2>

            <p class="timeline-subtitle">
                {{ project.subtitle }}
            </p>

            <p class="timeline-description">
                {{ project.excerpt }}
            </p>

            <div class="timeline-tags">

                {% for tech in project.tags %}

                <span class="timeline-tag">
                    {{ tech }}
                </span>

                {% endfor %}

            </div>

        </div>

    </a>

</div>

{% endif %}
{% endfor %}

</div>