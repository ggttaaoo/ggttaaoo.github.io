---
layout: default
title: Tao Gong
---

<div class="header">
  <h1>Tao Gong</h1>
  <p class="subtitle">PhD Student, University of Western Ontario</p>
</div>

<div class="content">

  <!-- Introduction Section -->
  <section class="intro">
    <p>I am a PhD student under the supervision of Matthias Franz at the University of Western Ontario in Canada. Before that I obtained my Bachelor's and Master's degrees under the supervision of Xu'an Zhao at Beijing Normal University in China.</p>
  </section>

  <!-- Papers Section -->
  <section class="papers">
    <h2>Papers</h2>
    
    {% for paper in site.data.publications %}
    <div class="paper">
      <h3>{{ paper.title }}</h3>
      <p class="authors">{{ paper.authors }}</p>
      <p class="venue">{{ paper.journal }}, {{ paper.year }}</p>
      {% if paper.pdf %}
        <a href="{{ paper.pdf }}" class="paper-link">[PDF]</a>
      {% endif %}
      {% if paper.arxiv %}
        <a href="{{ paper.arxiv }}" class="paper-link">[arXiv]</a>
      {% endif %}
      {% if paper.doi %}
        <a href="https://doi.org/{{ paper.doi }}" class="paper-link">[DOI]</a>
      {% endif %}
    </div>
    {% endfor %}
  </section>

  <!-- Education Section
  <section class="education">
    <h2>Education</h2>
    <div class="degree">
      <h3>PhD in Mathematics</h3>
      <p>University of Western Ontario, 202X-present</p>
      <p>Supervisor: Matthias Franz</p>
    </div>
    <div class="degree">
      <h3>MSc in Mathematics</h3>
      <p>Beijing Normal University, 20XX-20XX</p>
      <p>Supervisor: Xu'an Zhao</p>
    </div>
  </section> -->

  <!-- Contact Section -->
  <section class="contact">
    <h2>Contact</h2>
    <p>Email: <a href="mailto:{{ site.email }}">{{ site.email }}</a></p>
    <p>Office: MC275D</a></p>
    <p>Department of Mathematics<br>
    University of Western Ontario<br>
    London, ON, Canada</p>
  </section>

</div>