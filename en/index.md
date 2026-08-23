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
  <h1>{{ p.identity.name_en }} <span style="font-size:0.55em; font-weight:500;">{{ p.identity.credential }}</span></h1>
  <p style="font-size:1.08rem; color:var(--text-secondary); margin:0.35rem 0;">{{ p.identity.tagline_en }}</p>
  <p style="font-size:0.92rem; color:var(--text-tertiary); margin:0;">{{ p.identity.location_en }}</p>
</div>

<hr class="section-divider">

## Current

<div class="cv-summary">
  {% for exp in p.experience %}
    {% if exp.current %}
    <div class="cv-item">
      <strong>{{ exp.role_en }}</strong><br>
      {{ exp.organization_en }} · {{ exp.start }}–Present<br>
      <span style="color:var(--text-secondary);">{{ exp.description_en }}</span>
    </div>
    {% endif %}
  {% endfor %}
  <div class="cv-item">
    <strong>{{ p.education[0].degree_en }} · {{ p.education[0].field_en }}</strong><br>
    {{ p.education[0].institution_en }} · {{ p.education[0].start }}–{{ p.education[0].end }}<br>
    <span style="color:var(--text-secondary);">Thesis: {{ p.education[0].thesis }}</span>
  </div>
</div>

<hr class="section-divider">

## Research & Technical Focus

<div class="research-topics">
  <div class="topic-card">
    <h3>AI Systems</h3>
    <p>AI/LLM applications, software development, and intelligent automation for real workflows. Current enterprise work is described only at an approved public level.</p>
  </div>
  <div class="topic-card">
    <h3>AI for Science</h3>
    <p>Connecting literature, models, simulation, and experiment into executable scientific workflows across drug discovery and biomaterials.</p>
  </div>
  <div class="topic-card">
    <h3>Computational Chemistry</h3>
    <p>Docking, molecular dynamics, quantum chemistry, and high-performance computing for protein–ligand and multi-scale biomolecular interactions.</p>
  </div>
</div>

<hr class="section-divider">

## Selected Work

<div class="publications-container">
  <div class="publication-item">
    <strong>{{ pubs.published[0].title }}</strong><br>
    <em>{{ pubs.published[0].venue }}</em> · {{ pubs.published[0].role_en }} · {{ pubs.published[0].year }}<br>
    <span style="color:var(--text-secondary);">{{ pubs.published[0].highlight_en }}</span><br>
    <div class="publication-links"><a href="{{ pubs.published[0].url }}" target="_blank">DOI</a></div>
  </div>

  {% for project in projects.selected limit:3 %}
  <div class="publication-item">
    <strong>{{ project.title_en }}</strong> <span style="color:var(--text-tertiary);">{{ project.period }}</span><br>
    <span style="color:var(--text-secondary);">{{ project.description_en }}</span>
    {% if project.links %}
    <div class="publication-links">
      {% for link in project.links %}<a href="{{ link.url }}" target="_blank">{{ link.label }}</a>{% endfor %}
    </div>
    {% endif %}
  </div>
  {% endfor %}
</div>

<hr class="section-divider">

## {{ p.now.label_en }}

<div class="update-item">
  <span class="update-content"><strong><a href="{{ p.now.url }}" target="_blank">{{ p.now.question_en }}</a></strong></span><br>
  <span style="color:var(--text-secondary); font-size:0.9rem;">{{ p.now.note_en }}</span>
</div>

<hr class="section-divider">

## Explore

- [About]({{ site.baseurl }}/en/about/): professional, educational, research, and technical archive
- [Publications & Scholarly Activities]({{ site.baseurl }}/en/publications/): publications, manuscripts, academic service, patents, and software copyrights
- [Projects & Open Source]({{ site.baseurl }}/en/projects/): selected research/technical work and secondary public repositories

<div class="language-notice">
📍 <em>本网站同时提供<a href="{{ site.baseurl }}/">中文版本</a></em>
</div>
