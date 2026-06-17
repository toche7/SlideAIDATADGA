---
description: "Create or update Marp slides for this course using the Mahidol theme and concrete teaching examples"
name: "Create Mahidol Marp Slide"
argument-hint: "Topic, audience level, and whether to create a new deck or add slides to an existing file"
agent: "agent"
---
Create or revise Marp slides for this workspace.

Primary goal:
- Produce slides that are ready to teach immediately with clear examples, not abstract bullets only.

Required context:
- Follow workspace instructions in [AGENTS.md](../../AGENTS.md).
- Use the theme conventions from [theme-mahidol.css](../../themes/theme-mahidol.css).
- Prefer editing an existing session file under [slides](../../slides/) unless the user explicitly asks for a new file.

Content rules:
- Keep frontmatter aligned with this workspace style: marp true, theme mahidol, paginate true, size 16:9.
- For course wording, use "Gemini in Colab" when describing the learning platform.
- Add concrete examples for each key concept:
  - Example question
  - Recommended chart or method
  - Short interpretation for public-sector decision making
- If images are inserted, use Marpit image syntax or existing theme helper classes like center.
- Keep Thai language clear and instructor-friendly.

Output style:
- Keep slide titles concise.
- Balance theory and practice.
- For workshop slides, include runnable snippets and practical prompts.

Execution checklist:
1. Read the target slide file first.
2. Apply minimal, focused edits.
3. Export with Marp when possible to validate rendering.
4. Summarize what changed and where.
