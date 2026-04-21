# Installing Ultrapowers for OpenCode

Add Ultrapowers to the `plugin` array in your `opencode.json`:

```json
{
  "plugin": ["ultrapowers@git+https://github.com/danduma/ultrapowers.git"]
}
```

Restart OpenCode, then verify by asking it to list or load an Ultrapowers skill.

Ultrapowers is installed from GitHub directly here; it is not currently available as an official plugin marketplace entry.

## Example

```text
use skill tool to load ultrapowers/brainstorming
```

## Updating

Restart OpenCode to reinstall the git-based plugin, or pin a tag or commit hash in the plugin URL.
