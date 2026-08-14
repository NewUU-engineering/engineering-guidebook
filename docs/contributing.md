# Contributing

This guidebook is not finished and is not meant to be. It describes a school that is still being built, by people who are still arriving. If you disagree with something in it, the disagreement is the contribution.

Everything here is maintained in the open at [github.com/NewUU-engineering/engineering-guidebook](https://github.com/NewUU-engineering/engineering-guidebook).

## Agreeing with it publicly

Adoption is voluntary, and a commitment nobody can see is not a commitment. To state publicly that you follow this guidebook, open a pull request adding your name to [`SIGNATORIES.md`](https://github.com/NewUU-engineering/engineering-guidebook/blob/main/SIGNATORIES.md). Students, staff and alumni all welcome.

You may remove your name at any time, in the same way, without explanation.

## Proposing changes

Open an [Issue or a Pull Request](https://docs.github.com/en/get-started/exploring-projects-on-github/contributing-to-a-project).

### Issue rules

1. Check that you are filing in the correct repository. Anything about operating a robot belongs in [robotics-docs](https://github.com/NewUU-engineering/robotics-docs); anything about coursework content belongs in the relevant course repository.
2. If you are reporting an error, check that no equivalent Issue exists yet.
3. Fill in the title and description precisely.
4. Prefix the title with one of: `[BUG]`, `[PROPOSAL]`, `[QUESTION]`.

### Pull request rules

1. For small changes — typos, formatting, a broken link — a Pull Request is preferred over an Issue.
2. Describe the problem and your proposed fix. Reference the Issue number where one exists.
3. Before changing formatting, confirm that the change is needed.
4. Follow the prevailing Markdown style of the repository.
5. Write in plain sentences. The guidebook is published in English and Russian — update both versions when the change is substantive, and say so in the pull request if you can only do one.

### Arguing with a principle

A pull request that changes what this School claims to stand for is a different kind of change from a typo fix, and it should look like one. Open an Issue first, say what the current text gets wrong, and propose replacement wording. Expect the discussion to take a while and to happen in public — that is the point, and it is the mechanism by which this document stays honest rather than becoming a monument.

## Style

The house style is the same one used across our documentation:

- **Concrete over abstract.** "Ask what the grading scheme is in week one" beats "students should engage proactively".
- **Say who does what.** Advice with no subject is advice nobody follows.
- **No slogans.** If a sentence would fit on a poster in a corridor, cut it.
- **Short sentences, ordinary words**, and no more adjectives than the meaning requires. A large share of readers work in English as a second or third language, and clarity is a courtesy to them.
- **Link, do not duplicate.** If a procedure already exists in another repository, link to it. Two copies of a rule means one of them is wrong.
- **Do not invent facts about the School.** If a channel, a policy or a scheme has not been agreed yet, leave a marked note asking for it rather than a confident sentence that turns out to be false.

## Versioning

The version and date live at the top of the [Introduction](index.md), with a change history beneath.

- **Patch** — typos, links, clarifications. No version bump needed.
- **Minor** — a new section or substantially rewritten guidance. Bump the minor version and add a line to the history.
- **Major** — a change to the orientations themselves. Requires public discussion in an Issue first.

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

Pushes to `main` trigger the `Deploy Docs` workflow, which runs `mkdocs gh-deploy --force` and publishes to GitHub Pages from the `gh-pages` branch.
