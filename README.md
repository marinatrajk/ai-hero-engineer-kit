# ai-hero-engineer-kit

Five engineering skills for a Vellum personal assistant, ported from Matt Pocock's [_5 Agent Skills I Use Every Day_](https://www.aihero.dev/5-agent-skills-i-use-every-day).

Plans, PRDs, vertical-slice issues, test-driven development, and codebase deepening, installed as one bundle.

## Install

```bash
# From your vellum-assistant checkout, after the catalog PR merges on main:
assistant plugins install ai-hero-engineer-kit

# Or, before the catalog lands, install straight from the branch:
assistant plugins install ai-hero-engineer-kit --ref catalog/ai-hero-engineer-kit
```

The runtime picks the five skills up from `skills/<name>/SKILL.md` and matches them against your conversation via the `description` and `metadata.vellum.activation-hints` frontmatter. No daemon hooks required for this kit.

## What's in here

| Skill                         | What it does                                                                                                  |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `grill-me`                    | Interview me relentlessly on a plan until we reach shared understanding, walking each branch of the tree.    |
| `to-prd`                      | Turn the current conversation into a PRD with user stories, implementation decisions, and testing decisions. |
| `to-issues`                   | Break a PRD into vertical-slice GitHub issues using tracer bullets, published in dependency order.           |
| `tdd`                         | Red-green-refactor with agents. One test, one implementation, repeat. Avoid horizontal slices.               |
| `improve-codebase-architecture` | Surface shallow modules and propose deepening opportunities. Driven by domain language and ADRs.            |

Read them in order. `grill-me` builds shared understanding, `to-prd` writes it down, `to-issues` slices it, `tdd` ships each slice, and `improve-codebase-architecture` keeps the codebase hygienic in between.

## Layout

```
ai-hero-engineer-kit/
├── package.json
├── skills/
│   ├── grill-me/SKILL.md
│   ├── to-prd/SKILL.md
│   ├── to-issues/SKILL.md
│   ├── tdd/SKILL.md
│   └── improve-codebase-architecture/SKILL.md
└── (no hooks — pure skill bundle)
```

This plugin does not ship TypeScript code, so there are no `hooks/`, `src/`, or `tests/` directories. It is just a `skills/` catalog. The `package.json` exists so the catalog loader can resolve the plugin and the peer dependency on `@vellumai/plugin-api` is declared.

## Notes

Skills are adapted directly from Matt Pocock's [_skills_](https://github.com/mattpocock/skills) repo. A few of them cross-reference sibling files in that repo (`tests.md`, `mocking.md`, `LANGUAGE.md`, `CONTEXT-FORMAT.md`, `ADR-FORMAT.md`, `INTERFACE-DESIGN.md`, `HTML-REPORT.md`). If you want the full experience for any of those skills, fetch the file from upstream.

Two of the skills reference `/setup-matt-pocock-skills`, which is the CLI scaffold Matt ships separately. That command is not part of this kit — the skills still work without it; the issue tracker vocabulary just needs to be available to the assistant another way (or accepted as a default).

## Attribution

- Skills: © [Matt Pocock](https://www.aihero.dev), MIT licensed upstream. Adapted and repackaged under the same terms.
- Plugin packaging: Marina Trajkovska.
- See [`LICENSE`](./LICENSE) for the full text.

## License

MIT.
