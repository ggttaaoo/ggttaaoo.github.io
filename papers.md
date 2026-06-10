---
layout: default
title: Papers
---

<h2>Papers</h2>

<!-- Publications + Preprints -->
<h3>Publications and Preprints</h3>

<ol class="paper-list">

{% assign items = site.data.publications %}

{% for p in items %}

  {% unless p.note or p.type == "thesis" %}

  <li class="paper">

    {% if p.authors and p.authors != "" %}
      ({{ p.authors }})
    {% endif %}

    <strong>{{ p.title }}</strong>.

    {% if p.journal %}

      {% if p.status == "to appear" %}
        To appear in <em>{{ p.journal }}</em>.
      {% else %}
        <em>{{ p.journal }}</em>
        {% if p.volume %} {{ p.volume }}{% endif %}
        {% if p.year %} ({{ p.year }}){% endif %}
        {% if p.pages %}, {{ p.pages }}{% endif %}.
      {% endif %}

    {% else %}
      Available at
      <a href="https://arxiv.org/abs/{{ p.preprint }}" target="_blank">
        arXiv:{{ p.preprint }}
      </a>.
    {% endif %}

    {% if p.preprint and p.journal %}
      Available at
      <a href="https://arxiv.org/abs/{{ p.preprint }}" target="_blank">
        arXiv:{{ p.preprint }}
      </a>.
    {% endif %}

  </li>

  {% endunless %}

{% endfor %}

</ol>


<!-- Notes -->
{% assign notes = site.data.publications | where: "note", true %}
{% if notes.size > 0 %}
<h3>Notes</h3>

<ol class="paper-list">

{% for n in notes %}
  <li class="paper">

    {% if n.authors and n.authors != "" %}
      ({{ n.authors }})
    {% endif %}

    <strong>{{ n.title }}</strong>.

    {% if n.year %}
      {{ n.year }}.
    {% endif %}

    {% if n.file_link %}
      <a href="{{ n.file_link }}" target="_blank">PDF</a>.
    {% endif %}

  </li>
{% endfor %}

</ol>
{% endif %}


<!-- Theses -->
{% assign theses = site.data.publications | where: "type", "thesis" %}
{% if theses.size > 0 %}
<h3>Theses</h3>

<ol class="paper-list">

{% for t in theses %}
  <li class="paper">

    <strong>{{ t.title }}</strong>.

    {% if t.degree %}
      {{ t.degree }}.
    {% endif %}

    {% if t.year %}
      {{ t.year }}.
    {% endif %}

  </li>
{% endfor %}

</ol>
{% endif %}

<p><a href="/">← Back to Home</a></p>