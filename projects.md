---
layout: default
title: "项目与开源"
permalink: /projects/
---

{% assign p = site.data.profile %}
{% assign projects = site.data.projects %}

# 项目与开源

## 代表性研究与技术工作

{% for project in projects.selected %}
<div class="cv-project">
  <div class="cv-entry-heading">
    <strong>{{ project.title_zh }}</strong>
    <span>{{ project.role_zh }}</span>
    <span class="cv-date">{{ project.period | replace: 'Present', '至今' }}</span>
  </div>
  {% if project.bullets_zh %}<ul>{% for bullet in project.bullets_zh %}<li>{{ bullet }}</li>{% endfor %}</ul>{% else %}<p>{{ project.description_zh }}</p>{% endif %}
  {% if project.links %}<div class="inline-links">{% for link in project.links %}<a href="{{ link.url }}" target="_blank" rel="noopener">{{ link.label }}</a>{% endfor %}</div>{% endif %}
</div>
{% endfor %}

## {{ p.now.label_zh }}

<div class="current-inquiry"><a href="{{ p.now.url }}" target="_blank" rel="noopener">{{ p.now.question_zh }}</a></div>

## 其他公开仓库

{% for repo in projects.public_repositories %}
- **[{{ repo.name }}]({{ repo.url }})** — {{ repo.description_zh }}
{% endfor %}

## 已归档

{% for repo in projects.archived %}
- **[{{ repo.name }}]({{ repo.url }})** — {{ repo.description_zh }}
{% endfor %}
