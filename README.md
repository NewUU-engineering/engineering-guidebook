# engineering-guidebook

A guidebook to the School of Engineering at New Uzbekistan University: what we aim at, how we try to get there, and what that means in practice.

📖 **[Read the guidebook](https://newuu-engineering.github.io/engineering-guidebook/)** — [English](https://newuu-engineering.github.io/engineering-guidebook/) · [Русский](https://newuu-engineering.github.io/engineering-guidebook/ru/)

It is written for students first. Instructors and staff will find themselves in it too.

The guidebook is published in both languages. English pages are `docs/*.md`, Russian pages are `docs/*.ru.md`, and the two are kept in step — a substantive change to one should be made to the other.

## Contents

| Chapter | What is in it |
|---|---|
| [Introduction](docs/index.md) | Why a guidebook exists, how to read it, ground rules |
| [What we aim at](docs/orientations.md) | Cooperation, open source, transparency, rationality, real problems, one culture |
| [How we get there](docs/methods.md) | Working in public, self-education, freedom and responsibility, widening your circle, open repositories |
| [Academic ethics](docs/ethics.md) | Asking well, conflict, instructors, credit and honesty, money |
| [Small groups and projects](docs/groups.md) | Why groups, what the School supports, what to work on, how to start |
| [Passing a course](docs/courses.md) | Week one, staying in contact, working the course, language, escalation |
| [Working with AI tools](docs/ai-tools.md) | Accountability, disclosure, verification, hard limits |
| [Safety is part of the culture](docs/safety.md) | Standing rules, no-blame reporting, written procedure |
| [Advice for your years here](docs/advice.md) | Assorted, unranked, non-obligatory |
| [For instructors](docs/teaching.md) | Setting a course up, running it, improving it |
| [Contributing](docs/contributing.md) | How to argue with any of the above |

## Before this is announced

The text contains marked notes where a local fact is required and must not be invented. Search the repository for `To be filled in by the School`. Open items:

- [ ] [`index.md`](docs/index.md) — canonical link to the university's academic regulations and Academic Integrity policy
- [ ] [`ethics.md`](docs/ethics.md) — the School's actual communication channels (student chat, course chat convention, office email and its response window)
- [ ] [`ethics.md`](docs/ethics.md) — scholarship, assistantship and internal grant schemes open to students, and the office that administers them
- [ ] [`ai-tools.md`](docs/ai-tools.md) — the university's official policy on generative AI in assessed work, and the School's default where a course is silent
- [ ] [`safety.md`](docs/safety.md) — induction, contacts and emergency procedure per laboratory, and the named safety officer for each
- [ ] [`advice.md`](docs/advice.md) — decide whether the Dean or the department heads endorse, edit or replace that chapter
- [ ] Confirm that `SIGNATORIES.md` is the mechanism the School wants for public adoption

## Reporting problems and proposing improvements

Open an [Issue or a Pull Request](https://docs.github.com/desktop/contributing-and-collaborating-using-github-desktop/creating-an-issue-or-pull-request). Rules are in [Contributing](docs/contributing.md).

To state publicly that you follow this guidebook, add your name to [`SIGNATORIES.md`](SIGNATORIES.md).

## Local deployment

### In a Docker container

```bash
git clone https://github.com/NewUU-engineering/engineering-guidebook
cd engineering-guidebook
docker pull squidfunk/mkdocs-material
docker run --rm -it -p 8000:8000 -v ${PWD}:/docs squidfunk/mkdocs-material
```

### In a Python virtual environment

```bash
git clone https://github.com/NewUU-engineering/engineering-guidebook
cd engineering-guidebook
python3 -m venv venv
source venv/bin/activate
pip install mkdocs-material "mkdocs-static-i18n[material]"
mkdocs serve
```

The site is then available at `http://127.0.0.1:8000`.

## Publishing

Pushes to `main` trigger the `Deploy Docs` workflow, which runs `mkdocs gh-deploy --force` and publishes the site to GitHub Pages from the `gh-pages` branch.
