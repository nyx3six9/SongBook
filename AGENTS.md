# SongBook — AI Development & QA Working Rules

These instructions apply to AI-assisted work on this repository. Communicate with the project owner in Hebrew, using clear, nontechnical explanations when needed.

## Mission
Deliver reliable, measurable improvements to the Hebrew lyrics-and-chords app, with minimal manual work for the owner. Prioritize correctness, reproducibility, usability on iPhone/iPad and desktop, data integrity, security, and maintainability over speed or speculative fixes.

## GitHub as source of truth
- Treat the GitHub repository as the authoritative source for code, issues, pull requests, commits, and releases. Inspect current files and history before editing; never assume a prior chat attachment is the current version.
- Track every meaningful bug or feature in an Issue with: problem, reproduction steps, expected/actual behavior, environment, evidence, acceptance criteria, and links to related work.
- For each code change, create a narrowly scoped feature/fix branch from the latest main. Never directly modify main for substantive changes.
- Make small, descriptive commits. Open a Pull Request referencing the relevant Issue, with summary, alternatives, risks, tests performed, test results, and rollback instructions.
- Do not merge to main or publish a new production version without explicit owner approval. A successful commit or PR is not evidence that a fix works.
- Use semantic version tags/releases for verified milestones, with a concise changelog. Distinguish development, tested, and published versions.

## Debugging and validation
- Reproduce the reported problem before changing code whenever possible. Distinguish observed facts from hypotheses.
- Find the root cause rather than applying broad workarounds. Make the smallest defensible fix; avoid unrelated refactors.
- For OCR, test both dark/light backgrounds, varied chord colors, Hebrew lyrics, different image formats/sizes, and direct iPhone screenshots. Include known expected chord/lyric results and regression cases.
- Test on the relevant device/browser where possible. If actual device testing is unavailable, say so explicitly; never claim a test passed without running it.
- Review user-facing text, UI accessibility, RTL layout, image upload, edit, save/load, transpose, capo, print/export, and existing song library behavior when changes could affect them.
- Before publishing, report what was tested, what remains unverified, known limitations, and a safe rollback path.

## Decision support and proactive advice
- When there is a potentially more efficient or robust method, proactively explain it to the owner rather than silently choosing.
- For meaningful choices, compare options briefly: benefits, drawbacks, complexity, cost, privacy/security, maintenance, and risk to existing functionality. Recommend a path and state uncertainty.
- Proactively flag missing requirements, hidden dependencies, technical debt, browser constraints, licensing/copyright, backup needs, and long-term maintainability.
- Avoid unnecessary tools, infrastructure, subscriptions, or overengineering. Prefer simple solutions that satisfy requirements and remain testable.
- Ask for approval before consequential architecture changes, cloud integrations, paid services, permission expansion, data migrations, destructive operations, or publication.

## Data and privacy
- GitHub Pages and public repositories are public; never commit secrets, tokens, private song libraries, or copyrighted source screenshots to public repos.
- Use the private `nyx3six9/songbook_tests` repository for authorized private OCR fixtures. Do not copy those fixtures into the public repository.
- Browser localStorage is device/browser-specific, not cross-device cloud sync. Preserve existing song data, plan backups/export, and test migration carefully before changing persistence.
- Do not imply private GitHub fixtures can be fetched automatically by a public Pages site. Separate developer-side testing from deployed browser behavior.

## Working communication
- For each task, provide: current status, concrete findings, recommended next action, and any decision needed from the owner.
- Use exact GitHub links to Issues, branches, PRs, and releases when available.
- Explain failures plainly; do not conceal uncertainty or invent outcomes.
- Keep the owner informed of useful alternatives and risks even when not explicitly requested.
