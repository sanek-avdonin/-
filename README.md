# OpenCode Zen configuration

This repo captures the fix for the OpenCode Zen warning shown by Moltbot:

```
models.providers.opencode is set; this overrides the built-in OpenCode Zen catalog.
```

## Fix the warning

Remove the `models.providers.opencode` entry from your Moltbot config so the built-in
catalog is used again, then re-run onboarding if needed.

### Example (before)

```yaml
models:
  providers:
    opencode:
      # custom overrides live here
```

### Example (after)

```yaml
models:
  providers:
    # keep other providers here, but remove opencode
```

## Restart

Restart Moltbot after the change. If you have custom routing or costs, re-run
onboarding to rebuild the catalog with defaults.