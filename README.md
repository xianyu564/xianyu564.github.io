# Ziyang Zhang · Personal Academic & Technical Archive

[![Website](https://img.shields.io/badge/Website-xianyu564.github.io-274C5E?style=flat-square&logo=github)](https://xianyu564.github.io)
[![ORCID](https://img.shields.io/badge/ORCID-0000--0002--0350--5958-A6CE39?style=flat-square&logo=orcid)](https://orcid.org/0000-0002-0350-5958)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-ziyang--zhang--ai-0A66C2?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/ziyang-zhang-ai/)

This repository powers my bilingual personal website. The homepage functions as a **complete web CV**, while the supporting pages retain a broader academic, technical, and public-project archive.

## Public profile

- **Focus:** AI Systems · AI for Science · Computational Chemistry
- **Current role:** Consultant Specialist at HSBC
- **Education:** Ph.D. in Biomedical Engineering, National University of Singapore
- **Email:** z_zz@u.nus.edu

Current enterprise work follows the same high-level public disclosure boundary used on LinkedIn. Internal systems, implementation details, repositories, infrastructure, and workflow specifics are not used as public profile content.

## Information architecture

The site uses Jekyll and keeps reusable public factual records in `_data/` so that Chinese and English pages do not maintain separate copies of the same facts.

```text
_data/
  profile.yml       # identity, experience, education, internships, contact
  publications.yml  # publications, manuscripts, academic service, IP
  projects.yml      # CV-level projects and public repositories

cv/
  Ziyang_Zhang_CV_EN.pdf
  Ziyang_Zhang_CV_ZH.pdf

index.md / en/index.md                 # complete web CV + public extensions
about.md / en/about.md                 # concise profile narrative
publications.md / en/publications.md   # academic record
projects.md / en/projects.md           # project detail + public repositories
```

Principle: **one public fact, one canonical data owner**. The homepage should expose the substance of the current master CV directly rather than forcing readers through navigation links. CV files use stable paths so later revisions can replace the assets without changing public URLs.

## Disclosure boundary

- Public employment descriptions stay at an approved, high-level scope.
- Private repositories are not named or described automatically.
- A current private research line may be represented through a researcher-approved public anchor question and a generic GitHub activity link.
- Phone numbers, residential details, and internal enterprise implementation information are omitted from the public site.

## Site

- 中文：<https://xianyu564.github.io/>
- English: <https://xianyu564.github.io/en/>

## Development

The site is built with Jekyll / GitHub Pages and an explicit custom layout / stylesheet. Desktop presentation uses a persistent left profile sidebar and a full-width content column; mobile presentation collapses to a compact top navigation. Content changes should update canonical `_data/` records first when possible, then adjust presentation pages when the reader experience or information architecture changes.
