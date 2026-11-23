# designer-GB

A design-partner agent skill plus Heraldo's style preferences.

Copy the `designer/` folder into `~/.claude/skills/` or the harness's skills dir, or reference `designer/SKILL.md` from `AGENTS.md`.

- `SKILL.md`: the workflow + token budget (always loaded, ~1k tokens)
- `style-profile.md`: Heraldo's taste profile (read every job, keep updating it)
- `references/anti-slop.md`: spec template, motion rules, critique list, render checks (loaded only when needed). Keep its license credits.

## Credits

This template paraphrases and condenses rules from:

- [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) (tasteskill 2.5.1), MIT License, Copyright (c) 2026 Leonxlnx
- [Impeccable](https://impeccable.style) / [pbakaus/impeccable](https://github.com/pbakaus/impeccable), Apache License 2.0, Copyright 2025 Paul Bakaus. Impeccable started from Anthropic's frontend-design skill. Its iOS and Android references are distilled from ehmo/platform-design-skills (MIT).
- [emilkowalski/skills](https://github.com/emilkowalski/skills), MIT License, Copyright (c) 2026 Emil Kowalski

The MIT copyright notices above must be kept when this file is copied. The Apache 2.0 portions are used under that license; see the Impeccable `LICENSE` and `NOTICE.md` for terms. This is a short derived workflow, not a substitute for those projects or their scripts.
