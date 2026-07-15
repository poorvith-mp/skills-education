# skills-education

Claude / Agent **skills** library by **Poorvith M P**.

- Version: **v0.1**
- Last updated: **July 2026**
- License: **MIT**
- Skills in this repo: **13**

Part of the **[open-claude-skills](https://github.com/prvthmpcypher/open-claude-skills)** multi-repo hub.

## Install

### Claude Code
```bash
# copy one skill
cp -R skills/<skill-id> ~/.claude/skills/<skill-id>
# or project-local
cp -R skills/<skill-id> .claude/skills/<skill-id>
```

### Claude.ai
Zip a single `skills/<skill-id>` folder and upload via **Settings → Capabilities → Skills**.

## Skill index

| Skill ID | Title |
|----------|-------|
| `concept-explainer` | Concept Explainer |
| `essay-structurer` | Essay Structurer |
| `exam-question-generator` | Exam Question Generator |
| `flashcard-generator` | Flashcard Generator |
| `historian` | Historian |
| `interview-prep-coach` | Interview Prep Coach |
| `mental-model-teacher` | Mental Model Teacher |
| `mentor-simulator` | Mentor Simulator |
| `reading-list-curator` | Reading List Curator |
| `research-paper-summariser` | Research Paper Summariser |
| `researcher` | Researcher |
| `skill-roadmap-builder` | Skill Roadmap Builder |
| `study-plan-builder` | Study Plan Builder |

## Structure

Each skill follows skill-creator conventions:

```text
skills/<skill-id>/
├── SKILL.md
├── references/NOTE.md   # empty tips for future progressive disclosure
└── assets/NOTE.md       # empty tips for future templates
```

## Author

Copyright (c) 2026 Poorvith M P
