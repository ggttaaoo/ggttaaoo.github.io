---
layout: default
title: Papers
---

<h2>Papers</h2>

<!-- Publications Section -->
{% assign pubs = site.data.publications | where_exp: "p", "p.journal" %}
{% if pubs.size > 0 %}
<section class="publications">
  <h3>Publications</h3>
  <ol class="paper-list">
    {% for paper in pubs %}
    <li class="paper">
      <span class="paper-authors">{{ paper.authors }}.</span>
      <span class="paper-title">{{ paper.title }}.</span>
      <span class="paper-year">{{ paper.year }}.</span>
      {% if paper.doi %}
      <a href="https://doi.org/{{ paper.doi }}">DOI</a>.
      {% endif %}
      {% if paper.pdf %}
      <a href="{{ paper.pdf }}">[PDF]</a>
      {% endif %}
    </li>
    {% endfor %}
  </ol>
</section>
{% endif %}

<!-- Preprints Section -->
{% assign preprints = site.data.publications | where_exp: "p", "p.preprint" %}
{% if preprints.size > 0 %}
<section class="preprints">
  <h3>Preprints</h3>
  <ol class="paper-list">
    {% for paper in preprints %}
    <li class="paper">
      <span class="paper-authors">{{ paper.authors }}.</span>
      <span class="paper-title">{{ paper.title }}.</span>
      <span class="paper-year">{{ paper.year }}.</span>
      <a href="https://arxiv.org/abs/{{ paper.preprint }}">arXiv</a>
      {% if paper.pdf %}
      <a href="{{ paper.pdf }}">[PDF]</a>
      {% endif %}
    </li>
    {% endfor %}
  </ol>
</section>
{% endif %}

<!-- Notes Section -->
{% assign notes = site.data.publications | where_exp: "p", "p.note" %}
{% if notes.size > 0 %}
<section class="notes">
  <h3>Notes</h3>
  <ol class="paper-list">
    {% for paper in notes %}
    <li class="paper">
      <span class="paper-authors">{{ paper.authors }}.</span>
      <span class="paper-title">{{ paper.title }}.</span>
      <span class="paper-year">{{ paper.year }}.</span>
      {% if paper.pdf %}
      <a href="{{ paper.pdf }}">[PDF]</a>
      {% endif %}
    </li>
    {% endfor %}
  </ol>
</section>
{% endif %}

<p><a href="/">← Back to Home</a></p>
