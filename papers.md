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
<h3>Preprints</h3>
<ol class="paper-list">
  {% for p in preprints %}
  <li class="paper">
    <strong>{{ p.title }}</strong>.  
    {{ p.authors }}.  
    {{ p.year }}.  
    <a href="https://arxiv.org/abs/{{ p.preprint }}" target="_blank">arXiv:{{ p.preprint }}</a>
  </li>
  {% endfor %}
</ol>
{% endif %}

<!-- Notes Section -->
{% assign notes = site.data.publications | where: "note", true %}
{% if notes.size > 0 %}
<h3>Notes</h3>
<ol class="paper-list">
  {% for n in notes %}
  <li class="paper">
    <strong>{{ n.title }}</strong>.  
    {{ n.authors }}.  
    {{ n.year }}.  
    {% if n.file_link %}
      <a href="{{ n.file_link }}" target="_blank">[PDF]</a>
    {% endif %}
  </li>
  {% endfor %}
</ol>
{% endif %}

<!-- Theses Section -->
{% assign theses = site.data.publications | where: "type", "thesis" %}
{% if theses.size > 0 %}
<h3>Theses</h3>
<ol class="paper-list">
  {% for t in theses %}
  <li class="paper">
    <strong>{{ t.title }}</strong>.  
    {{ t.degree }} — {{ t.authors }}.  
    {{ t.year }}.
  </li>
  {% endfor %}
</ol>
{% endif %}



<p><a href="/">← Back to Home</a></p>
