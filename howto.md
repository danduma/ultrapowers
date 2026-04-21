Yes, but not with one universal “if cwd == repo then load local skills” switch across all three tools.

The clean model is:

1. Install or expose the skill library once so the tool can discover it.
2. Add repo-local bootstrap files so, when the tool is run in this directory, it is told to use `ultrapowers`.

**What works best**

For `Codex`, the local docs already say it uses native discovery from `~/.agents/skills` via a symlink. So the best setup is:

```bash
mkdir -p ~/.agents/skills
ln -s /Users/masterman/NLP/omniharness/ultrapowers/skills ~/.agents/skills/ultrapowers
```

That means Codex is always able to see the live skills from this repo checkout. Then the repo’s [AGENTS.md](/Users/masterman/NLP/omniharness/AGENTS.md) becomes the project-local activation layer: it tells Codex to use `ultrapowers` behavior in this repo.

For `Gemini`, the easiest repo-local activation is a root [GEMINI.md](/Users/masterman/NLP/omniharness/ultrapowers/GEMINI.md)-style wrapper in this repo. Since `ultrapowers/GEMINI.md` already imports the right files, the root file can just point at it. That gives you true “inside this repo, Gemini picks it up” behavior.

For `Claude Code`, there are two realistic options:
- install `ultrapowers` as a plugin globally, then use a repo-local [CLAUDE.md](/Users/masterman/NLP/omniharness/ultrapowers/CLAUDE.md)-style bootstrap to make it the default in this repo, or
- expose the skills in Claude’s own skills location and still use a repo-local `CLAUDE.md` to activate them here.

So the important distinction is:
- `Codex`: global discovery, local activation
- `Claude`: global discovery/plugin, local activation
- `Gemini`: local activation is much easier because `GEMINI.md` is already the native hook point

**What I’d recommend**

Make this repo contain thin project bootstrap files:
- keep [AGENTS.md](/Users/masterman/NLP/omniharness/AGENTS.md) for Codex
- add a root `CLAUDE.md`
- add a root `GEMINI.md`

Those files should all say, in repo-specific terms:
- use the local `ultrapowers` skill system
- prefer the `ultrapowers` defaults
- for app/UI work, use the product-completeness pass
- use the skills from `/Users/masterman/NLP/omniharness/ultrapowers`

Then do one-time discovery setup per tool:
- Codex: symlink `~/.agents/skills/ultrapowers` to this repo’s `ultrapowers/skills`
- Claude: install/plugin or symlink into its skills location
- Gemini: root `GEMINI.md` is usually enough, depending on how you launch it

So yes, we can absolutely make it automatic in practice for this repo. The reliable path is not “project-local skill discovery only”; it’s “global discovery plus repo-local bootstrap.”

If you want, I can set up the repo-local bootstrap files next:
- strengthen [AGENTS.md](/Users/masterman/NLP/omniharness/AGENTS.md)
- create root `CLAUDE.md`
- create root `GEMINI.md`
- and add a small `scripts/link-ultrapowers.sh` so your machine can wire Codex and the others to this repo checkout in one command.