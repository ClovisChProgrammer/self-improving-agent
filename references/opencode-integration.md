# OpenCode Integration

How the self-improvement skill works within OpenCode.

## Skill Loading

Skills in OpenCode are loaded on-demand via the `skill` tool. When you invoke `skill("self-improvement")`:

1. The content of `SKILL.md` is injected into the current session context
2. The agent then reads the supporting files (SOUL.md, USER.md, etc.) from the skill directory
3. The agent reads existing `.learnings/` entries from the current project's working directory

## File Locations

**Skill directory** (global, shared across projects):
```
~/.config/opencode/skills/self-improving-agent/
├── SKILL.md
├── SOUL.md
├── USER.md
├── AGENTS.md
├── IDENTITY.md
└── ...
```

**.learnings/** (per project, created where you work):
```
<project-root>/.learnings/
├── LEARNINGS.md
├── ERRORS.md
└── FEATURE_REQUESTS.md
```

OpenCode searches for skills in multiple locations (including `~/.config/opencode/skills/`), so any OpenCode instance can find this skill.

## Plugin Integration (Optional)

For advanced users, this skill can be supplemented with an OpenCode plugin using `@opencode-ai/plugin`:

```typescript
// ~/.config/opencode/plugins/self-improvement.js
import { tool } from "@opencode-ai/plugin";

export const server = (ctx) => ({
  hooks: {
    "experimental.chat.system.transform": async (systemPrompt) => {
      // Inject a reminder to check .learnings/ before responding
      return systemPrompt + "\n\n[Check .learnings/ for relevant past context before responding.]";
    }
  }
});
```

## Troubleshooting

### Skill not loading
1. Verify SKILL.md is in `~/.config/opencode/skills/self-improving-agent/`
2. Check frontmatter has `name: self-improvement`
3. Try `skill("self-improvement")` explicitly

### Files not found
1. The skill directory is at `~/.config/opencode/skills/self-improving-agent/`
2. Use the Read tool with the full path to verify files exist
3. If missing, the init script will create .learnings/ files automatically
