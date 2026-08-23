---
layout: default
title: "Projects & Open Source"
lang: en
permalink: /en/projects/
---

{% assign p = site.data.profile %}
{% assign projects = site.data.projects %}

# Projects & Open Source

## Selected Research & Technical Work

{% for project in projects.selected %}
<div class="cv-project">
  <div class="cv-entry-heading">
    <strong>{{ project.title_en }}</strong>
    <span>{{ project.role_en }}</span>
    <span class="cv-date">{{ project.period }}</span>
  </div>
  {% if project.bullets_en %}<ul>{% for bullet in project.bullets_en %}<li>{{ bullet }}</li>{% endfor %}</ul>{% else %}<p>{{ project.description_en }}</p>{% endif %}
  {% if project.links %}<div class="inline-links">{% for link in project.links %}<a href="{{ link.url }}" target="_blank" rel="noopener">{{ link.label }}</a>{% endfor %}</div>{% endif %}
</div>
{% endfor %}

## {{ p.now.label_en }}

<div class="current-inquiry"><a href="{{ p.now.url }}" target="_blank" rel="noopener">{{ p.now.question_en }}</a></div>

## Other Public Repositories

{% for repo in projects.public_repositories %}
- **[{{ repo.name }}]({{ repo.url }})** — {{ repo.description_en }}
{% endfor %}

## Archived

{% for repo in projects.archived %}
- **[{{ repo.name }}]({{ repo.url }})** — {{ repo.description_en }}
{% endfor %}
