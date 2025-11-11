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
    <p>Office: MC275D</p>
  </section>

</div>