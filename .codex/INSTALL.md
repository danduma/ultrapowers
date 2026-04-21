# Installing Ultrapowers for Codex

Enable Ultrapowers skills in Codex via native skill discovery.

Ultrapowers is not currently available as a Codex plugin marketplace install. Install it directly from GitHub.

## Installation

1. Clone the fork:

```bash
git clone https://github.com/danduma/ultrapowers.git ~/.codex/ultrapowers
```

2. Create the skills symlink:

```bash
mkdir -p ~/.agents/skills
ln -s ~/.codex/ultrapowers/skills ~/.agents/skills/ultrapowers
```

3. Restart Codex.

## Verify

```bash
ls -la ~/.agents/skills/ultrapowers
```

You should see a symlink or junction pointing at `~/.codex/ultrapowers/skills`.

## Updating

```bash
cd ~/.codex/ultrapowers && git pull
```

## Uninstalling

```bash
rm ~/.agents/skills/ultrapowers
rm -rf ~/.codex/ultrapowers
```
