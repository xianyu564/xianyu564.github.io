---
layout: default
title: "主页"
---

{% assign p = site.data.profile %}
{% assign pubs = site.data.publications %}
{% assign projects = site.data.projects %}

<div class="hero-section">
  <h1>{{ p.identity.name_zh }} <span style="font-size:0.55em; font-weight:500;">{{ p.identity.credential }}</span></h1>
  <p style="font-size:1.08rem; color:var(--text-secondary); margin:0.35rem 0;">{{ p.identity.tagline_zh }}</p>
  <p style="font-size:0.92rem; color:var(--text-tertiary); margin:0;">{{ p.identity.location_zh }}</p>
</div>

<hr class="section-divider">

## 当前

<div class="cv-summary">
  {% for exp in p.experience %}
    {% if exp.current %}
    <div class="cv-item">
      <strong>{{ exp.role_zh }}</strong><br>
      {{ exp.organization_zh }} · {{ exp.start }}–至今<br>
      <span style="color:var(--text-secondary);">{{ exp.description_zh }}</span>
    </div>
    {% endif %}
  {% endfor %}
  <div class="cv-item">
    <strong>{{ p.education[0].degree_zh }} · {{ p.education[0].field_zh }}</strong><br>
    {{ p.education[0].institution_zh }} · {{ p.education[0].start }}–{{ p.education[0].end }}<br>
    <span style="color:var(--text-secondary);">博士论文：{{ p.education[0].thesis }}</span>
  </div>
</div>

<hr class="section-divider">

## 研究与技术主线

<div class="research-topics">
  <div class="topic-card">
    <h3>AI 系统</h3>
    <p>面向真实工作流的 AI / LLM 应用、软件开发与智能自动化；公开主页对当前企业项目只保留经允许的高层描述。</p>
  </div>
  <div class="topic-card">
    <h3>AI for Science</h3>
    <p>把文献、模型、模拟与实验连接成可执行研究流程，关注药物发现、生物材料与科学知识工作流。</p>
  </div>
  <div class="topic-card">
    <h3>计算化学</h3>
    <p>分子对接、分子动力学、量子化学与高性能计算，用于蛋白质–小分子及多尺度生物分子互作分析。</p>
  </div>
</div>

<hr class="section-divider">

## 代表性工作

<div class="publications-container">
  <div class="publication-item">
    <strong>{{ pubs.published[0].title }}</strong><br>
    <em>{{ pubs.published[0].venue }}</em> · {{ pubs.published[0].role_zh }} · {{ pubs.published[0].year }}<br>
    <span style="color:var(--text-secondary);">{{ pubs.published[0].highlight_zh }}</span><br>
    <div class="publication-links"><a href="{{ pubs.published[0].url }}" target="_blank">DOI</a></div>
  </div>

  {% for project in projects.selected limit:3 %}
  <div class="publication-item">
    <strong>{{ project.title_zh }}</strong> <span style="color:var(--text-tertiary);">{{ project.period }}</span><br>
    <span style="color:var(--text-secondary);">{{ project.description_zh }}</span>
    {% if project.links %}
    <div class="publication-links">
      {% for link in project.links %}<a href="{{ link.url }}" target="_blank">{{ link.label }}</a>{% endfor %}
    </div>
    {% endif %}
  </div>
  {% endfor %}
</div>

<hr class="section-divider">

## {{ p.now.label_zh }}

<div class="update-item">
  <span class="update-content"><strong><a href="{{ p.now.url }}" target="_blank">{{ p.now.question_zh }}</a></strong></span><br>
  <span style="color:var(--text-secondary); font-size:0.9rem;">{{ p.now.note_zh }}</span>
</div>

<hr class="section-divider">

## 导航

- [关于我]({{ site.baseurl }}/about/)：完整的职业、教育、研究与技术档案
- [发表与学术活动]({{ site.baseurl }}/publications/)：论文、未刊稿件、学术服务、专利与软件著作权
- [项目与开源]({{ site.baseurl }}/projects/)：代表性研究 / 技术项目与次级公开仓库

<div class="language-notice">
📍 <em>This website is also available in <a href="{{ site.baseurl }}/en/">English</a></em>
</div>
