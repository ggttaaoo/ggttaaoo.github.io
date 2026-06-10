---
layout: default
title: Papers
---

<h2>Papers</h2>

<!-- Publications -->
{% assign publications = site.data.publications | where_exp: "p", "p.journal" %}
{% if publications.size > 0 %}
<section class="publications">
  <h3>Publications</h3>

  <ul class="paper-list">
    {% for p in publications %}
    <li>

      {% if p.authors and p.authors != "" %}
      ({{ p.authors }})
      {% endif %}

      <em>{{ p.title }}</em>.

      {% if p.status == "to appear" %}
        To appear in <em>{{ p.journal }}</em>.
      {% else %}
        <em>{{ p.journal }}</em>
        {% if p.volume %} {{ p.volume }}{% endif %}
        {% if p.year %} ({{ p.year }}){% endif %}
        {% if p.pages %}, {{ p.pages }}{% endif %}.
      {% endif %}

      {% if p.preprint %}
        Also available at
        <a href="https://arxiv.org/abs/{{ p.preprint }}" target="_blank">
          arXiv:{{ p.preprint }}
        </a>.
      {% endif %}

      {% if p.doi %}
        <a href="https://doi.org/{{ p.doi }}" target="_blank">DOI</a>.
      {% endif %}

    </li>
    {% endfor %}
  </ul>
</section>
{% endif %}

<!-- Preprints -->
{% assign preprints = site.data.publications | where_exp: "p", "p.preprint and p.journal == nil" %}
{% if preprints.size > 0 %}
<section class="preprints">
  <h3>Preprints</h3>

  <ul class="paper-list">
    {% for p in preprints %}
    <li>

      {% if p.authors and p.authors != "" %}
      ({{ p.authors }})
      {% endif %}

      <em>{{ p.title }}</em>,
      <a href="https://arxiv.org/abs/{{ p.preprint }}" target="_blank">
        arXiv:{{ p.preprint }}
      </a>.

    </li>
    {% endfor %}
  </ul>
</section>
{% endif %}

<!-- Notes -->
{% assign notes = site.data.publications | where: "note", true %}
{% if notes.size > 0 %}
<section class="notes">
  <h3>Notes</h3>

  <ul class="paper-list">
    {% for n in notes %}
    <li>

      {% if n.authors and n.authors != "" %}
      {{ n.authors }}.
      {% endif %}

      <em>{{ n.title }}</em>.

      {% if n.year %}
      {{ n.year }}.
      {% endif %}

      {% if n.file_link %}
      <a href="{{ n.file_link }}" target="_blank">PDF</a>.
      {% endif %}

    </li>
    {% endfor %}
  </ul>
</section>
{% endif %}

<!-- Theses -->
{% assign theses = site.data.publications | where: "type", "thesis" %}
{% if theses.size > 0 %}
<section class="theses">
  <h3>Theses</h3>

  <ul class="paper-list">
    {% for t in theses %}
    <li>

      <em>{{ t.title }}</em>.

      {% if t.degree %}
      {{ t.degree }}.
      {% endif %}

      {% if t.year %}
      {{ t.year }}.
      {% endif %}

    </li>
    {% endfor %}
  </ul>
</section>
{% endif %}

<p><a href="/">← Back to Home</a></p>