---
layout: default
title: "关于我"
permalink: /about/
---

{% assign p = site.data.profile %}

# 关于我

<div class="about-intro">
{{ p.identity.name_zh }} · {{ p.identity.credential }}<br>
{{ p.identity.tagline_zh }}
</div>

我的工作横跨 **AI 系统、AI for Science 与计算化学**。目前在汇丰从事科技相关工作，参与大型银行科技环境中的 AI 软件开发与智能自动化，并与工程、架构及业务团队协作探索新兴技术的应用。

我的科研背景集中于 AI 辅助药物发现、计算化学与生物材料。博士期间就读于新加坡国立大学生物医学工程系，并接受药剂与药理科学、淡马锡生命科学实验室及新加坡国家癌症中心的联合培养；相关研究把科学文献挖掘、大语言模型、分子对接、分子动力学、量子化学和实验验证连接起来，用于糖尿病伤口相关药物研究。

此前创办决明科技，并以 **Elephenotype / 象对论** 作为对外品牌之一，负责 AI / LLM 软件开发与交付。

## 研究方向

{% for item in p.research_focus.zh %}- {{ item }}
{% endfor %}

## 核心技能

{% for item in p.skills.zh %}- {{ item }}
{% endfor %}

## 教育背景

{% for edu in p.education %}
**{{ edu.degree_zh }} · {{ edu.field_zh }}**｜{{ edu.institution_zh }} · {{ edu.start | replace: '-', '.' }}–{{ edu.end | replace: '-', '.' }}

{% if edu.joint_training %}
{% for jt in edu.joint_training %}- 联合培养：{{ jt.zh }}（{{ jt.period }}）
{% endfor %}
{% endif %}
{% if edu.thesis %}- 博士论文：*{{ edu.thesis }}*{% endif %}

{% endfor %}

## 近期研究问题

[**{{ p.now.question_zh }}**]({{ p.now.url }})

## 联系方式

- [{{ p.contact.email }}](mailto:{{ p.contact.email }})
- [LinkedIn]({{ p.contact.linkedin }})
- [ORCID]({{ p.contact.orcid }})
- [GitHub]({{ p.contact.github }})
- [Web of Science]({{ p.contact.web_of_science }})
- [中文简历 PDF]({{ p.contact.cv_zh }}) · [English CV]({{ p.contact.cv_en }})
