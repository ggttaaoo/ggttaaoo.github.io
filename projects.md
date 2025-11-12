---
layout: default
title: Projects
---

<h2>Projects</h2>

<ul class="project-list">
  {% for project in site.data.projects %}
  <li class="project">
    <h3>{{ project.title }}</h3>
    {% if project.time %}
    <p><strong>{{ project.time }}</strong></p>
    {% endif %}
    {% if project.authors %}
    <p><em>{{ project.authors }}</em></p>
    {% endif %}
    <p>{{ project.description }}</p>
    {% if project.colab_link %}
    <p>🔗 <a href="{{ project.colab_link }}" target="_blank">View on Google Colab</a></p>
    {% endif %}
    {% if project.file_link %}
    <p>📘 <a href="{{ project.file_link }}" target="_blank">Read the Project</a></p>
    {% endif %}
  </li>
  {% endfor %}
</ul>

<p><a href="/">← Back to Home</a></p>
