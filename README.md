# persona-qa

Persona-driven launch QA for product flows. An expanded Roundtable-style roster: fifteen tester personas plus one **Judge** who consolidates findings and is **not** a tester.

Inspired by five-persona launch QA (impatient, mobile/slow network, non-native English, skeptic, breaker) and extended for interruption, mistakes, novices, returning/cross-device continuity, power use, privacy, accessibility, data migration, and integrations.

## Files

| Path | Purpose |
|------|---------|
| [`personas.tsv`](personas.tsv) | Roster: id, name, slug, role, model, effort, is_new, description |
| [`agents/`](agents/) | One full agent identity Markdown file per persona (`agents/<slug>.md`) |

## How to use

1. Pick the product or flow under test.
2. Load each tester from `agents/<slug>.md` (or filter via `personas.tsv` by model/effort/role).
3. Run testers independently; each follows its **Session procedure** and fills its **Report format**.
4. Hand all tester reports to **Judge** (`agents/judge.md`). The Judge ranks issues, proposes fixes, and produces a consolidated checklist — it does not walk the product as a user.

### TSV columns

`id`, `name`, `slug`, `role` (`tester` \| `judge`), `model` (`Fast` \| `Balanced` \| `Strong`), `effort` (`Low` \| `Medium` \| `High`), `is_new`, `description`

### Suggested harness mapping

- **Fast / Low–Medium** — quick smoke passes, shallow tool use
- **Balanced** — normal exploratory depth
- **Strong / High** — deep probing (a11y, integrations, adversarial edge cases, judgment)

## License

Use freely for internal QA and agent harnesses. Attribution to Roundtable-style launch QA is appreciated but not required.
