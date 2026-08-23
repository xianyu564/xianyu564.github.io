---
layout: default
title: "关于我"
permalink: /about/
---

{% assign p = site.data.profile %}
{% assign pubs = site.data.publications %}

# 关于我

<div class="about-intro">
{{ p.identity.name_zh }} · {{ p.identity.credential }}<br>
{{ p.identity.tagline_zh }}
</div>

## 简介

我的工作主要横跨 **AI 系统、AI for Science 与计算化学**。目前在汇丰从事科技相关工作，公开介绍仅保留与 LinkedIn 一致的高层口径：参与大型银行科技环境中的 AI 软件开发与智能自动化，并与工程、架构及业务团队协作探索新兴技术的应用。

我的科研背景集中于 AI 辅助药物发现、计算化学和生物材料。博士期间在新加坡国立大学生物医学工程系学习，并接受药剂与药理科学、淡马锡生命科学实验室及新加坡国家癌症中心的正式联合培养。相关研究把科学文献挖掘、大语言模型与分子对接、分子动力学、量子化学和实验验证连接起来，用于糖尿病伤口相关药物研究。

此前创办决明科技，并以 **Elephenotype / 象对论** 作为对外品牌之一，负责 AI / LLM 软件开发与交付。

## 工作经历

{% for exp in p.experience %}
**{{ exp.role_zh }}** | {{ exp.organization_zh }}{% if exp.brand_zh %} / {{ exp.brand_zh }}{% endif %} · {{ exp.start }}–{% if exp.current %}至今{% else %}{{ exp.end }}{% endif %}

{{ exp.description_zh }}

{% endfor %}

## 教育背景

{% for edu in p.education %}
**{{ edu.degree_zh }}，{{ edu.field_zh }}** | {{ edu.institution_zh }} · {{ edu.start }}–{{ edu.end }}

{% if edu.joint_training %}
联合培养：
{% for jt in edu.joint_training %}
- {{ jt.zh }}（{{ jt.period }}）
{% endfor %}
{% endif %}
{% if edu.thesis %}- 博士论文：*{{ edu.thesis }}*{% endif %}

{% endfor %}

## 研究方向

{% for item in p.research_focus.zh %}- {{ item }}
{% endfor %}

## 核心技能

{% for item in p.skills.zh %}- {{ item }}
{% endfor %}

## 学术与技术档案

- [发表与学术活动]({{ site.baseurl }}/publications/)：已发表论文、未刊稿件、同行评审、专利与软件著作权。
- [项目与开源]({{ site.baseurl }}/projects/)：代表性研究 / 技术工作与次级公开仓库。
- 博士阶段代表研究：{{ pubs.published[0].title }}，*{{ pubs.published[0].venue }}*，{{ pubs.published[0].role_zh }}。
- 简历下载：[中文 PDF]({{ p.contact.cv_zh | relative_url }}) · [English PDF]({{ p.contact.cv_en | relative_url }})。

## 其他经历

**实习 / 研究实践**

- 博士期间：百图生科、泰康保险集团、北京聚创造网络科技有限公司。
- 本科期间：中国科学技术大学化学物理系、中国科学院理化技术研究所。

**科研合作**  
{{ p.additional.collaborations_zh }}

**艺术创作**  
{{ p.additional.arts_zh }}

**语言**  
{{ p.additional.languages_zh }}

## {{ p.now.label_zh }}

[**{{ p.now.question_zh }}**]({{ p.now.url }})  
{{ p.now.note_zh }}

## 联系方式

- 邮箱：[{{ p.contact.email }}](mailto:{{ p.contact.email }})
- [LinkedIn]({{ p.contact.linkedin }})
- [ORCID]({{ p.contact.orcid }})
- [GitHub]({{ p.contact.github }})
- [Web of Science]({{ p.contact.web_of_science }})

> 本页不公开手机号、详细住址或企业内部实现信息。
