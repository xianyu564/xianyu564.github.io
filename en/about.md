---
layout: default
title: "About"
lang: en
permalink: /en/about/
---

{% assign p = site.data.profile %}
{% assign pubs = site.data.publications %}

# About

<div class="about-intro">
{{ p.identity.name_en }} · {{ p.identity.credential }}<br>
{{ p.identity.tagline_en }}
</div>

## Profile

I work across **AI systems, AI for Science, and computational chemistry**. I currently work in technology at HSBC. Public descriptions of this role intentionally stay at the same high-level boundary used on LinkedIn: AI-enabled software development and intelligent automation within a large-scale banking technology environment, with cross-functional collaboration across engineering, architecture, and business teams.

My research background spans AI-assisted drug discovery, computational chemistry, and biomaterials. During my Ph.D. in Biomedical Engineering at the National University of Singapore, I received formal joint training with Pharmacy and Pharmaceutical Sciences, Temasek Life Sciences Laboratory, and National Cancer Centre Singapore. My research connected scientific literature mining and LLMs with docking, molecular dynamics, quantum chemistry, and experimental validation for diabetic-wound research.

Previously, I founded Jue-Ming Technology, with **Elephenotype** as one of its public-facing brands, and led AI/LLM software development and delivery.

## Professional Experience

{% for exp in p.experience %}
**{{ exp.role_en }}** | {{ exp.organization_en }}{% if exp.brand_en %} / {{ exp.brand_en }}{% endif %} · {{ exp.start }}–{% if exp.current %}Present{% else %}{{ exp.end }}{% endif %}

{{ exp.description_en }}

{% endfor %}

## Education

{% for edu in p.education %}
**{{ edu.degree_en }}, {{ edu.field_en }}** | {{ edu.institution_en }} · {{ edu.start }}–{{ edu.end }}

{% if edu.joint_training %}
Joint training:
{% for jt in edu.joint_training %}
- {{ jt.en }} ({{ jt.period }})
{% endfor %}
{% endif %}
{% if edu.thesis %}- Thesis: *{{ edu.thesis }}*{% endif %}

{% endfor %}

## Research Focus

{% for item in p.research_focus.en %}- {{ item }}
{% endfor %}

## Core Skills

{% for item in p.skills.en %}- {{ item }}
{% endfor %}

## Academic & Technical Archive

- [Publications & Scholarly Activities]({{ site.baseurl }}/en/publications/): published work, manuscripts, peer review, patents, and software copyrights.
- [Projects & Open Source]({{ site.baseurl }}/en/projects/): selected research/technical work and secondary public repositories.
- Representative Ph.D. work: {{ pubs.published[0].title }}, *{{ pubs.published[0].venue }}*, {{ pubs.published[0].role_en | downcase }}.
- CV: [English PDF]({{ p.contact.cv_en | relative_url }}) · [中文 PDF]({{ p.contact.cv_zh | relative_url }}).

## Additional Experience

**Internships / research placements**

- During Ph.D.: BioMap; Taikang Insurance Group; Beijing JuCreate Network Technology Co., Ltd.
- During B.Sc.: Department of Chemical Physics, University of Science and Technology of China; Technical Institute of Physics and Chemistry, Chinese Academy of Sciences.

**Research collaborations**  
{{ p.additional.collaborations_en }}

**Arts**  
{{ p.additional.arts_en }}

**Languages**  
{{ p.additional.languages_en }}

## {{ p.now.label_en }}

[**{{ p.now.question_en }}**]({{ p.now.url }})  
{{ p.now.note_en }}

## Contact

- Email: [{{ p.contact.email }}](mailto:{{ p.contact.email }})
- [LinkedIn]({{ p.contact.linkedin }})
- [ORCID]({{ p.contact.orcid }})
- [GitHub]({{ p.contact.github }})
- [Web of Science]({{ p.contact.web_of_science }})

> Phone numbers, detailed residential information, and internal enterprise implementation details are intentionally not published on this site.
