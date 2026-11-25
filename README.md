# Empirical Code Audit

An agent skill for checking whether economics research code implements the analysis described in a paper and generates the reported results.

The skill traces inputs through data preparation, estimation or numerical solution, and the final tables and figures. When feasible, it independently reconstructs consequential calculations. Its reports distinguish verified errors, unresolved concerns, and documentation gaps.

## Use the skill

Download or clone this repository. Keep `SKILL.md` and `references/` together when adding the folder to a compatible agent. You can also point an agent directly to `SKILL.md` and ask it to follow the workflow.

For example:

> Audit this manuscript and replication package using the empirical-code-audit skill. Check whether the code implements the stated analysis. Where feasible, independently verify the main results, and explain what could not be checked.

The skill also supports a code-only audit, a review of changes, or a check of replication readiness. Provide the relevant files and any instructions or restrictions for execution and data access.

## Credits

The workflow draws on Claes Bäckman's [AI Research Feedback](https://github.com/claesbackman/AI-research-feedback) and Lee Crawfurd's [Claude Skills](https://github.com/lcrawfurd/claude-skills). See [workflow provenance and references](references/sources.md) for details.
