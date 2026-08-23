---
layout: default
title: "Publications & Scholarly Activities"
lang: en
permalink: /en/publications/
---

{% assign pubs = site.data.publications %}

# Publications & Scholarly Activities

## Ph.D. Thesis

**{{ pubs.thesis.title }}**  
{{ pubs.thesis.venue_en }} · {{ pubs.thesis.year }}

## Published Work & Conference Abstract

{% for paper in pubs.published %}
<div class="publication-item">
<strong>{{ paper.title }}</strong><br>
<em>{{ paper.venue }}</em> · {{ paper.role_en }} · {{ paper.year }}
{% if paper.highlight_en %}<br><span class="cv-detail">{{ paper.highlight_en }}</span>{% endif %}
<div class="publication-links">
{% if paper.url %}<a href="{{ paper.url }}" target="_blank" rel="noopener">DOI / Publisher</a>{% endif %}
{% if paper.code %}<a href="{{ paper.code }}" target="_blank" rel="noopener">Code</a>{% endif %}
</div>
</div>
{% endfor %}

## Manuscripts

{% for item in pubs.manuscripts %}
<div class="publication-item">
<strong>{{ item.title }}</strong>{% if item.venue %}<br><em>{{ item.venue }}</em>{% endif %}<br>
<span class="cv-detail">{{ item.status_en }}</span>
</div>
{% endfor %}

## Scholarly Activities

{% for item in pubs.scholarly_activities %}- {{ item.en }}
{% endfor %}

## Patent

{% for item in pubs.patents %}
**{{ item.title_en }}**  
{{ item.number }} · {{ item.role_en }} · {{ item.year }}
{% endfor %}

## Registered Software Copyrights

{{ pubs.software_copyrights.note_en }}

{% for item in pubs.software_copyrights.items %}- {{ item.en }} (Reg. No. {{ item.reg }})
{% endfor %}
