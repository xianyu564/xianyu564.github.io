---
layout: default
title: "发表与学术活动"
permalink: /publications/
---

{% assign pubs = site.data.publications %}

# 发表与学术活动

## 博士论文

**{{ pubs.thesis.title }}**  
{{ pubs.thesis.venue_zh }} · {{ pubs.thesis.year }}

## 已发表论文与会议摘要

{% for paper in pubs.published %}
<div class="publication-item">
<strong>{% if paper.url %}<a href="{{ paper.url }}" target="_blank" rel="noopener">{{ paper.title }}</a>{% else %}{{ paper.title }}{% endif %}</strong><br>
<em>{{ paper.venue }}</em> · {{ paper.role_zh }} · {{ paper.year }}
{% if paper.highlight_zh %}<br><span class="cv-detail">{{ paper.highlight_zh }}</span>{% endif %}
<div class="publication-links">
{% if paper.url %}<a href="{{ paper.url }}" target="_blank" rel="noopener">DOI / Publisher</a>{% endif %}
{% if paper.code %}<a href="{{ paper.code }}" target="_blank" rel="noopener">Code</a>{% endif %}
</div>
</div>
{% endfor %}

## 未刊稿件

{% for item in pubs.manuscripts %}
<div class="publication-item">
<strong>{{ item.title }}</strong>{% if item.venue %}<br><em>{{ item.venue }}</em>{% endif %}<br>
<span class="cv-detail">{{ item.status_zh }}</span>
</div>
{% endfor %}

## 学术活动

{% for item in pubs.scholarly_activities %}- {{ item.zh }}
{% endfor %}

## 发明专利

{% for item in pubs.patents %}
**{{ item.title_zh }}**  
{{ item.number }} · {{ item.role_zh }} · {{ item.year }}
{% endfor %}

## 软件著作权

{{ pubs.software_copyrights.note_zh }}

{% for item in pubs.software_copyrights.items %}- {{ item.zh }}（登记号：{{ item.reg }}）
{% endfor %}
