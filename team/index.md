---
title: People
layout: home
nav:
  order: 3
  tooltip: Meet the team
---

<section>
  <div class="container">
    <div class="section-head">
      <h1 class="section-title">The <em>team</em></h1>
      <span class="section-meta">Imperial College London</span>
    </div>

    {% assign pi = site.members | where: "role", "professor" | first %}
    {% include member-pi.html member=pi %}

    <div class="team-grid">
      {% assign others = site.members | where_exp: "m", "m.role != 'professor'" | sort: "order" %}
      {% for m in others %}
        {% include member-card.html member=m %}
      {% endfor %}
    </div>
  </div>
</section>
