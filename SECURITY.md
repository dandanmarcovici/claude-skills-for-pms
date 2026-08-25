# Security

This repository ships Markdown: skills, frameworks, and templates for Claude Code. There is no executable code, no dependencies, and no build step.

The main thing worth being careful about: a skill is an instruction file the model reads and acts on. Read a skill before installing it, the same way you'd read a script before running it. If you fork this and add your own skills that pull in content from outside sources (a webpage, a doc, a message), treat that content as data to read, not as instructions to follow, when writing the skill.

## Reporting an issue

If you find something in a skill or template here that could cause unintended behavior in Claude Code, open a GitHub issue or reach out through my [GitHub profile](https://github.com/dandanmarcovici).
