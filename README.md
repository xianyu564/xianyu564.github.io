# Ziyang Zhang · Personal Academic & Technical Archive

[![Website](https://img.shields.io/badge/Website-xianyu564.github.io-274C5E?style=flat-square&logo=github)](https://xianyu564.github.io)
[![ORCID](https://img.shields.io/badge/ORCID-0000--0002--0350--5958-A6CE39?style=flat-square&logo=orcid)](https://orcid.org/0000-0002-0350-5958)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-ziyang--zhang--ai-0A66C2?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/ziyang-zhang-ai/)

This repository powers my bilingual personal website and serves as a **public academic and technical archive**, rather than a copy of my résumé.

## Public profile

- **Focus:** AI Systems · AI for Science · Computational Chemistry
- **Current role:** Consultant Specialist at HSBC
- **Education:** Ph.D. in Biomedical Engineering, National University of Singapore
- **Email:** z_zz@u.nus.edu

Current enterprise work is intentionally described only at the same high-level public disclosure boundary used on LinkedIn. Internal systems, implementation details, repositories, infrastructure, and workflow specifics are out of scope for this website.

## Information architecture

The site uses Jekyll and keeps public factual records in `_data/` so that Chinese and English pages do not maintain separate copies of the same facts.

```text
_data/
  profile.yml       # identity, experience, education, contact, disclosure boundary
  publications.yml  # publications, manuscripts, academic service, IP
  projects.yml      # selected research/technical work and public repositories

cv/
  Ziyang_Zhang_CV_EN.pdf
  Ziyang_Zhang_CV_ZH.pdf

index.md / en/index.md
about.md / en/about.md
publications.md / en/publications.md
projects.md / en/projects.md
```

Principle: **one public fact, one canonical data owner**. Reader-facing pages summarize and render those records rather than redefining them. CV files use stable paths so future résumé refreshes can replace the assets without changing public links.

## Disclosure boundary

- Public employment descriptions stay at an approved, high-level scope.
- Private repositories are not named or described automatically.
- A current private research line may be represented only through a researcher-approved public anchor question and a generic GitHub activity link.
- Phone numbers, residential details, and internal enterprise implementation information are intentionally omitted.

## Site

- 中文：<https://xianyu564.github.io/>
- English: <https://xianyu564.github.io/en/>

## Development

The site is built with Jekyll / GitHub Pages and a customized Minimal theme. Content changes should update the canonical `_data/` record first when possible, then adjust presentation pages only when the information architecture or reader experience changes.
