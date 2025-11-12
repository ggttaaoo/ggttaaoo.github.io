---
layout: default
title: Papers
---

<h2>Papers</h2>

<ol class="paper-list">
  {% for paper in site.data.publications %}
  <li class="paper">
    <span class="paper-authors">{{ paper.authors }}.</span>
    <span class="paper-title">{{ paper.title }}.</span>
    <span class="paper-year">{{ paper.year }}.</span>
    {% if paper.preprint %}
      Preprint: <a href="https://arxiv.org/abs/{{ paper.preprint }}">arXiv:{{ paper.preprint }}</a>.
    {% elsif paper.journal %}
      <span class="paper-journal">{{ paper.journal }}.</span>
      {% if paper.doi %}
        <a href="https://doi.org/{{ paper.doi }}">DOI:{{ paper.doi }}</a>.
      {% endif %}
    {% endif %}
  </li>
  {% endfor %}
</ol>

<p><a href="/">← Back to Home</a></p>
