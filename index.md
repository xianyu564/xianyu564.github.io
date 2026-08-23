---
layout: default
title: "主页"
---

{% assign p = site.data.profile %}
{% assign pubs = site.data.publications %}
{% assign projects = site.data.projects %}

<div class="hero-section">
  <h1>{{ p.identity.name_zh }} <span class="credential">{{ p.identity.credential }}</span></h1>
  <p class="hero-tagline">{{ p.identity.tagline_zh }}</p>
  <p class="hero-meta">{{ p.identity.location_zh }} · <a href="mailto:{{ p.contact.email }}">{{ p.contact.email }}</a></p>
  <div class="hero-actions">
    <a href="{{ p.contact.cv_zh }}">中文简历 PDF</a>
    <a href="{{ p.contact.cv_en }}">English CV</a>
    <a href="{{ p.contact.linkedin }}" target="_blank" rel="noopener">LinkedIn</a>
    <a href="{{ p.contact.orcid }}" target="_blank" rel="noopener">ORCID</a>
    <a href="{{ p.contact.github }}" target="_blank" rel="noopener">GitHub</a>
  </div>
</div>

## 工作经历

{% for exp in p.experience %}
<div class="cv-entry">
  <div class="cv-entry-heading">
    <strong>{{ exp.role_zh }}</strong>
    <span>{{ exp.organization_zh }}{% if exp.brand_zh %} · {{ exp.brand_zh }}{% endif %}</span>
    <span class="cv-date">{{ exp.start | replace: '-', '.' }}–{% if exp.current %}至今{% else %}{{ exp.end | replace: '-', '.' }}{% endif %}</span>
  </div>
  <p>{{ exp.description_zh }}</p>
</div>
{% endfor %}

## 教育经历

{% for edu in p.education %}
<div class="cv-entry">
  <div class="cv-entry-heading">
    <strong>{{ edu.degree_zh }} · {{ edu.field_zh }}</strong>
    <span>{{ edu.institution_zh }}</span>
    <span class="cv-date">{{ edu.start | replace: '-', '.' }}–{{ edu.end | replace: '-', '.' }}</span>
  </div>
  {% if edu.joint_training %}
  <ul>
    {% for jt in edu.joint_training %}<li>联合培养：{{ jt.zh }}（{{ jt.period }}）</li>{% endfor %}
  </ul>
  {% endif %}
  {% if edu.thesis %}<p><strong>博士论文：</strong><em>{{ edu.thesis }}</em></p>{% endif %}
</div>
{% endfor %}

## 项目经历

{% for project in projects.selected %}
<div class="cv-project">
  <div class="cv-entry-heading">
    <strong>{{ project.title_zh }}</strong>
    <span>{{ project.role_zh }}</span>
    <span class="cv-date">{{ project.period | replace: 'Present', '至今' }}</span>
  </div>
  {% if project.bullets_zh %}
  <ul>
    {% for bullet in project.bullets_zh %}<li>{{ bullet }}</li>{% endfor %}
  </ul>
  {% else %}
  <p>{{ project.description_zh }}</p>
  {% endif %}
  {% if project.links %}
  <div class="inline-links">
    {% for link in project.links %}<a href="{{ link.url }}" target="_blank" rel="noopener">{{ link.label }}</a>{% endfor %}
  </div>
  {% endif %}
</div>
{% endfor %}

## 学术论文

<div class="cv-list">
{% for pub in pubs.published %}
<div class="cv-list-item">
  <strong>{{ pub.title }}</strong><br>
  <em>{{ pub.venue }}</em> · {{ pub.role_zh }} · {{ pub.year }}
  {% if pub.highlight_zh %}<div class="cv-detail">{{ pub.highlight_zh }}</div>{% endif %}
  {% if pub.url or pub.code %}<div class="inline-links">{% if pub.url %}<a href="{{ pub.url }}" target="_blank" rel="noopener">DOI</a>{% endif %}{% if pub.code %}<a href="{{ pub.code }}" target="_blank" rel="noopener">Code</a>{% endif %}</div>{% endif %}
</div>
{% endfor %}
</div>

## 未刊稿件

<ul class="cv-plain-list">
{% for item in pubs.manuscripts %}
  <li><strong>{{ item.status_zh }}</strong>：{{ item.title }}{% if item.venue %} · <em>{{ item.venue }}</em>{% endif %}</li>
{% endfor %}
</ul>

## 学术活动

<ul class="cv-plain-list">
{% for item in pubs.scholarly_activities %}<li>{{ item.zh }}</li>{% endfor %}
</ul>

## 发明专利

{% for item in pubs.patents %}
<div class="cv-list-item">
  <strong>{{ item.title_zh }}</strong><br>
  {{ item.number }} · {{ item.role_zh }} · {{ item.year }}
</div>
{% endfor %}

## 软件著作权

<p>{{ pubs.software_copyrights.note_zh }}</p>
<ol class="cv-plain-list">
{% for item in pubs.software_copyrights.items %}<li>{{ item.zh }}（登记号：{{ item.reg }}）</li>{% endfor %}
</ol>

## 实习经历

<p><strong>博士期间：</strong>{{ p.internships.phd_zh | join: '；' }}。</p>
<p><strong>本科期间：</strong>{{ p.internships.bsc_zh | join: '；' }}。</p>

## 其他

<p><strong>语言：</strong>{{ p.additional.languages_zh }}</p>
<p><strong>科研合作：</strong>{{ p.additional.collaborations_zh }}</p>
<p><strong>艺术创作与协会：</strong>{{ p.additional.arts_zh }}</p>

## {{ p.now.label_zh }}

<div class="current-inquiry">
  <a href="{{ p.now.url }}" target="_blank" rel="noopener">{{ p.now.question_zh }}</a>
</div>

## 公开项目与代码

<div class="repo-list">
{% for repo in projects.public_repositories %}
  <div class="repo-item"><a href="{{ repo.url }}" target="_blank" rel="noopener"><strong>{{ repo.name }}</strong></a><span>{{ repo.description_zh }}</span></div>
{% endfor %}
</div>

<div class="language-notice">
<a href="{{ site.baseurl }}/en/">English version</a>
</div>
