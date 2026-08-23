---
layout: default
title: "Projects & Open Source"
lang: en
permalink: /en/projects/
---

{% assign p = site.data.profile %}
{% assign projects = site.data.projects %}

# Projects & Open Source

This page has two layers: **selected research / technical work** that directly supports my current professional profile, followed by other genuine public repositories as a secondary archive. Private repositories are not listed automatically.

## {{ p.now.label_en }}

<div class="update-item">
<strong><a href="{{ p.now.url }}" target="_blank">{{ p.now.question_en }}</a></strong><br>
<span style="color:var(--text-secondary);">{{ p.now.note_en }}</span>
</div>

## Selected Research & Technical Work

<div class="projects-grid">
{% for project in projects.selected %}
<div class="project-card">
  <h3>{{ project.title_en }}</h3>
  <p class="project-status">{{ project.role_en }} · {{ project.period }}</p>
  <p class="project-description">{{ project.description_en }}</p>
  {% if project.links %}
  <p class="project-links">
    {% for link in project.links %}<a href="{{ link.url }}" target="_blank">[{{ link.label }}]</a>{% endfor %}
  </p>
  {% endif %}
</div>
{% endfor %}
</div>

## Other Public Repositories

These projects are genuine parts of my public GitHub record, but they do not carry the main professional narrative of this homepage.

{% for repo in projects.public_repositories %}
- **[{{ repo.name }}]({{ repo.url }})** — {{ repo.description_en }}
{% endfor %}

## Archived

{% for repo in projects.archived %}
- **[{{ repo.name }}]({{ repo.url }})** — {{ repo.description_en }}
{% endfor %}

---

[View GitHub Profile]({{ p.contact.github }}). Private repositories, internal enterprise code, and research details not approved for public disclosure are intentionally not enumerated here.
