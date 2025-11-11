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
    <p>I am interested in algebraic topology and homotopy theory. I am currently working in toric topology.</p>
  </section>

 <section class="papers">
  <h2>Papers</h2>
  <ol class="paper-list">
    {% for paper in site.data.publications %}
    <li class="paper">
      <span class="paper-authors">{{ paper.authors }}.</span>
      <span class="paper-title">{{ paper.title }}.</span>
      <span class="paper-year">{{ paper.year }}.</span>
      {% if paper.preprint %}
        Preprint available at <span class="paper-link"> <a href="https://arxiv.org/abs/{{ paper.preprint}}">arXiv:{{ paper.preprint}}</a>.</span>
      {% elsif paper.journal %}
        <span class="paper-journal">{{ paper.journal }}.</span>
        {% if paper.doi %}
          <a href="https://doi.org/{{ paper.doi }}" class="paper-link">DOI:{{ paper.doi }}</a>.
        {% endif %}
        {% if paper.pdf %}
          <a href="{{ paper.pdf }}" class="paper-link">[PDF]</a>
        {% endif %}
      {% endif %}
    </li>
    {% endfor %}
  </ol>
</section>

  <!-- Projects Section -->
  <section class="projects">
    <h2>Projects</h2>
    <ul class="project-list">
      {% for project in site.data.projects %}
      <li class="project">
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <p>
          🔗 <a href="{{ project.colab_link }}" target="_blank" rel="noopener noreferrer">Run in Google Colab</a><br>
        </p>
      </li>
      {% endfor %}
    </ul>
  </section>


  <!-- Contact Section -->
  <section class="contact">
    <h2>Contact</h2>
    <p>Email: <a href="mailto:{{ site.email }}">{{ site.email }}</a></p>
    <p>Office: MC275D</p>
  </section>

</div>