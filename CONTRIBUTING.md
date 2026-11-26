# Contributing

Thanks for helping keep this list useful. Open a pull request, or an issue if you are not sure something fits.

## What belongs here

- Tools that help **developers** use AI agents on Unity projects: Editor bridges (MCP or CLI), agent skills, rules and configs, Editor assistants, docs and context tools.
- Multi-engine tools only when they explicitly support Unity; they go under *Multi-engine game dev agents*.
- In-game or runtime AI (ML-Agents, Inference Engine, LLM-driven NPCs) is **out of scope**.

## Quality bar

An entry must:

- Not be archived, and have a push within the last 12 months.
- Have a README with install steps.
- State a license (closed-source products are fine if the entry says so).
- Do something an existing entry does not, or do it noticeably differently.

Entries that stop meeting the bar are removed during reviews.

## Entry format

One line per entry, alphabetical order not required:

```markdown
- [Name](https://link) - What it does, in one short sentence. ![](https://img.shields.io/github/stars/owner/repo?style=flat&label=)
```

- Write the description yourself; do not paste marketing copy.
- No star counts as plain text: use the shields.io badge so the number stays live.
- Omit the badge for entries that are not GitHub repositories.

## Updating the comparison table

The table compares Editor bridges. When you add or change a row:

- Take every value from the project's own README or docs, and link the source in your pull request description.
- Use "—" when the project does not state a value. Do not estimate.
- **Tools**: the count the README states. If you counted documented tools yourself, write "N listed".
- **Play Mode input**: ✅ only when simulated keyboard or mouse input during Play Mode is documented.
- Keep cells short; footnotes go below the table.

## Pull requests

- One entry or one topic per pull request.
- Use a title such as `Add <name>` or `Update <name> row`.
- Check that links work.
