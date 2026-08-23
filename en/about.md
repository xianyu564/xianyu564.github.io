---
layout: default
title: "About"
lang: en
permalink: /en/about/
---

{% assign p = site.data.profile %}

# About

<div class="about-intro">
{{ p.identity.name_en }} · {{ p.identity.credential }}<br>
{{ p.identity.tagline_en }}
</div>

I work across **AI systems, AI for Science, and computational chemistry**. I currently work in technology at HSBC, contributing to AI-enabled software development and intelligent automation within a large-scale banking technology environment and collaborating across engineering, architecture, and business teams on emerging-technology applications.

My research background spans AI-assisted drug discovery, computational chemistry, and biomaterials. During my Ph.D. in Biomedical Engineering at the National University of Singapore, I received joint training with Pharmacy and Pharmaceutical Sciences, Temasek Life Sciences Laboratory, and National Cancer Centre Singapore. My research connected scientific literature mining and LLMs with docking, molecular dynamics, quantum chemistry, and experimental validation for diabetic-wound research.

Previously, I founded Jue-Ming Technology, with **Elephenotype** as one of its public-facing brands, and led AI/LLM software development and delivery.

## Research Focus

{% for item in p.research_focus.en %}- {{ item }}
{% endfor %}

## Core Skills

{% for item in p.skills.en %}- {{ item }}
{% endfor %}

## Education

{% for edu in p.education %}
**{{ edu.degree_en }} · {{ edu.field_en }}** | {{ edu.institution_en }} · {{ edu.start | replace: '-', '.' }}–{{ edu.end | replace: '-', '.' }}

{% if edu.joint_training %}
{% for jt in edu.joint_training %}- Joint Ph.D. training: {{ jt.en }} ({{ jt.period }})
{% endfor %}
{% endif %}
{% if edu.thesis %}- Thesis: *{{ edu.thesis }}*{% endif %}

{% endfor %}

## Now actively working on

[**{{ p.now.question_en }}**]({{ p.now.url }})

## Contact

- [{{ p.contact.email }}](mailto:{{ p.contact.email }})
- [LinkedIn]({{ p.contact.linkedin }})
- [ORCID]({{ p.contact.orcid }})
- [GitHub]({{ p.contact.github }})
- [Web of Science]({{ p.contact.web_of_science }})
- [English CV PDF]({{ p.contact.cv_en }}) · [中文简历]({{ p.contact.cv_zh }})
