# scanrepo.dev

Additional wrappers, tools & AI skills for the [scanrepo](https://www.scanrepo.dev/) malware scanner.

## Install

Requires Node.js. The skills CLI runs via `npx` — no manual file copying:

```bash
# all supported agents, global install
npx skills add mkdev-ai/scanrepo-agent-skill -g -y

# specific agents only (OpenCode, Claude Code)
npx skills add mkdev-ai/scanrepo-agent-skill -g -a opencode -a claude-code -y

# just the scanrepo skill from this collection
npx skills add mkdev-ai/scanrepo-agent-skill --skill scanrepo -y

# inspect before installing
npx skills add mkdev-ai/scanrepo-agent-skill --list
```

The `scanrepo` skill enforces a **mandatory scan-before-clone gate**: any agent with it loaded runs a static malware scan (`npx scanrepo github.com/owner/repo`) before `git clone` or before installing/running code fetched from a repository, and blocks on suspicious, dangerous, or inconclusive verdicts. See `scanrepo/SKILL.md` for the full rule.