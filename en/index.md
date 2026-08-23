---
layout: default
title: "Home"
lang: en
permalink: /en/
---

{% assign p = site.data.profile %}
{% assign pubs = site.data.publications %}
{% assign projects = site.data.projects %}

<div class="hero-section">
  <h1>{{ p.identity.name_en }} <span class="credential">{{ p.identity.credential }}</span></h1>
  <p class="hero-tagline">{{ p.identity.tagline_en }}</p>
  <p class="hero-meta">{{ p.identity.location_en }} · <a href="mailto:{{ p.contact.email }}">{{ p.contact.email }}</a></p>
  <div class="hero-actions">
    <a href="{{ p.contact.cv_en }}">English CV PDF</a>
    <a href="{{ p.contact.cv_zh }}">中文简历</a>
    <a href="{{ p.contact.linkedin }}" target="_blank" rel="noopener">LinkedIn</a>
    <a href="{{ p.contact.orcid }}" target="_blank" rel="noopener">ORCID</a>
    <a href="{{ p.contact.github }}" target="_blank" rel="noopener">GitHub</a>
  </div>
</div>

## Professional Experience

{% for exp in p.experience %}
<div class="cv-entry">
  <div class="cv-entry-heading">
    <strong>{{ exp.role_en }}</strong>
    <span>{{ exp.organization_en }}{% if exp.brand_en %} · {{ exp.brand_en }}{% endif %}</span>
    <span class="cv-date">{{ exp.start | replace: '-', '.' }}–{% if exp.current %}Present{% else %}{{ exp.end | replace: '-', '.' }}{% endif %}</span>
  </div>
  <p>{{ exp.description_en }}</p>
</div>
{% endfor %}

## Education

{% for edu in p.education %}
<div class="cv-entry">
  <div class="cv-entry-heading">
    <strong>{{ edu.degree_en }} · {{ edu.field_en }}</strong>
    <span>{{ edu.institution_en }}</span>
    <span class="cv-date">{{ edu.start | replace: '-', '.' }}–{{ edu.end | replace: '-', '.' }}</span>
  </div>
  {% if edu.joint_training %}
  <ul>
    {% for jt in edu.joint_training %}<li>Joint Ph.D. training: {{ jt.en }} ({{ jt.period }})</li>{% endfor %}
  </ul>
  {% endif %}
  {% if edu.thesis %}<p><strong>Thesis:</strong> <em>{{ edu.thesis }}</em></p>{% endif %}
</div>
{% endfor %}

## Selected Projects

{% for project in projects.selected %}
<div class="cv-project">
  <div class="cv-entry-heading">
    <strong>{{ project.title_en }}</strong>
    <span>{{ project.role_en }}</span>
    <span class="cv-date">{{ project.period }}</span>
  </div>
  {% if project.bullets_en %}
  <ul>
    {% for bullet in project.bullets_en %}<li>{{ bullet }}</li>{% endfor %}
  </ul>
  {% else %}
  <p>{{ project.description_en }}</p>
  {% endif %}
  {% if project.links %}
  <div class="inline-links">
    {% for link in project.links %}<a href="{{ link.url }}" target="_blank" rel="noopener">{{ link.label }}</a>{% endfor %}
  </div>
  {% endif %}
</div>
{% endfor %}

## Publications

<div class="cv-list">
{% for pub in pubs.published %}
<div class="cv-list-item">
  <strong>{% if pub.url %}<a href="{{ pub.url }}" target="_blank" rel="noopener">{{ pub.title }}</a>{% else %}{{ pub.title }}{% endif %}</strong><br>
  <em>{{ pub.venue }}</em> · {{ pub.role_en }} · {{ pub.year }}
  {% if pub.highlight_en %}<div class="cv-detail">{{ pub.highlight_en }}</div>{% endif %}
  {% if pub.url or pub.code %}<div class="inline-links">{% if pub.url %}<a href="{{ pub.url }}" target="_blank" rel="noopener">DOI / Publisher</a>{% endif %}{% if pub.code %}<a href="{{ pub.code }}" target="_blank" rel="noopener">Code</a>{% endif %}</div>{% endif %}
</div>
{% endfor %}
</div>

## Manuscripts

<ul class="cv-plain-list">
{% for item in pubs.manuscripts %}
  <li><strong>{{ item.status_en }}</strong>: {{ item.title }}{% if item.venue %} · <em>{{ item.venue }}</em>{% endif %}</li>
{% endfor %}
</ul>

## Scholarly Activities

<ul class="cv-plain-list">
{% for item in pubs.scholarly_activities %}<li>{{ item.en }}</li>{% endfor %}
</ul>

## Selected Patent

{% for item in pubs.patents %}
<div class="cv-list-item">
  <strong>{{ item.title_en }}</strong><br>
  {{ item.number }} · {{ item.role_en }} · {{ item.year }}
</div>
{% endfor %}

## Registered Software Copyrights

<p>{{ pubs.software_copyrights.note_en }}</p>
<ol class="cv-plain-list">
{% for item in pubs.software_copyrights.items %}<li>{{ item.en }} (Reg. No. {{ item.reg }})</li>{% endfor %}
</ol>

## Internships

<p><strong>During Ph.D.:</strong> {{ p.internships.phd_en | join: '; ' }}.</p>
<p><strong>During B.Sc.:</strong> {{ p.internships.bsc_en | join: '; ' }}.</p>

## Additional Information

<p><strong>Languages:</strong> {{ p.additional.languages_en }}</p>
<p><strong>Collaborations:</strong> {{ p.additional.collaborations_en }}</p>
<p><strong>Arts:</strong> {{ p.additional.arts_en }}</p>

## {{ p.now.label_en }}

<div class="current-inquiry">
  <a href="{{ p.now.url }}" target="_blank" rel="noopener">{{ p.now.question_en }}</a>
</div>

## Public Projects & Code

<div class="repo-list">
{% for repo in projects.public_repositories %}
  <div class="repo-item"><a href="{{ repo.url }}" target="_blank" rel="noopener"><strong>{{ repo.name }}</strong></a><span>{{ repo.description_en }}</span></div>
{% endfor %}
</div>

<div class="language-notice">
<a href="{{ site.baseurl }}/">中文版本</a>
</div>
