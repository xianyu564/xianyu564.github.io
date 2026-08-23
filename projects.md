---
layout: default
title: "项目与开源"
permalink: /projects/
---

{% assign p = site.data.profile %}
{% assign projects = site.data.projects %}

# 项目与开源

本页分为两层：上半部分是与当前专业主线直接相关的**代表性研究 / 技术工作**；下半部分保留其他真实公开仓库作为次级档案。私人仓库不自动列出。

## {{ p.now.label_zh }}

<div class="update-item">
<strong><a href="{{ p.now.url }}" target="_blank">{{ p.now.question_zh }}</a></strong><br>
<span style="color:var(--text-secondary);">{{ p.now.note_zh }}</span>
</div>

## 代表性研究与技术工作

<div class="projects-grid">
{% for project in projects.selected %}
<div class="project-card">
  <h3>{{ project.title_zh }}</h3>
  <p class="project-status">{{ project.role_zh }} · {{ project.period }}</p>
  <p class="project-description">{{ project.description_zh }}</p>
  {% if project.links %}
  <p class="project-links">
    {% for link in project.links %}<a href="{{ link.url }}" target="_blank">[{{ link.label }}]</a>{% endfor %}
  </p>
  {% endif %}
</div>
{% endfor %}
</div>

## 其他公开仓库

这些项目真实存在于我的 GitHub，但不承担主页的主要职业叙事。

{% for repo in projects.public_repositories %}
- **[{{ repo.name }}]({{ repo.url }})** — {{ repo.description_zh }}
{% endfor %}

## 已归档

{% for repo in projects.archived %}
- **[{{ repo.name }}]({{ repo.url }})** — {{ repo.description_zh }}
{% endfor %}

---

[查看 GitHub Profile]({{ p.contact.github }})。私人仓库、企业内部代码及未获授权公开的研究细节不在本页枚举。
