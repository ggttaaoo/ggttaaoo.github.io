---
layout: default
title: Tao Gong
permalink: /
---

<div class="intro">
  <div class="intro-text">
    I am a PhD student under the supervision of Matthias Franz at the University of Western Ontario in Canada. Before that I got the Bachelor's and Master's degrees under the supervision of Xu'an Zhao at Beijing Normal University in China.
  </div>
  <div class="intro-image">
    ![Profile Photo](/assets/images/profile.jpg) <!-- Add your image -->
  </div>
</div>

## Papers

<div class="papers">
{% for pub in site.data.publications %}
  <div class="paper">
    <div class="paper-title">{{ pub.title }}</div>
    <div class="paper-authors">{{ pub.authors }}</div>
    <div class="paper-meta">{{ pub.journal }}, {{ pub.year }}</div>
    {% if pub.link %}
    <a href="{{ pub.link }}" class="paper-link">[PDF]</a>
    {% endif %}
  </div>
{% endfor %}
</div>

## Contact

<div class="contact">
  Email: <a href="mailto:{{ site.email }}">{{ site.email }}</a>
</div>



 <!-- Jekyll usage documentation at [jekyllrb.com](https://jekyllrb.com/) -->
