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

## Troubleshooting: Unknown model

If you see:

```
Error: Unknown model: ollama/qwen2.5:7b
```

It means Moltbot is pointing at a model that your local Ollama service does
not have installed. Fix it by doing one of the following:

- Install the model in Ollama (for example, `ollama pull qwen2.5:7b`), or
- Update your Moltbot config to a model that appears in `ollama list`.

After updating, restart Moltbot so the new model choice is picked up.