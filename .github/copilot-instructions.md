# Overview

This project uses SKILLS to provide additional context and information to enhance the responses.

# How to use SKILLS

## Overview

Skills are markdown files that contain details about the project.
You may need to know those details to better answer the user's prompt.

## Indexing Skills

Indexing skills is important to know what skills are available to load when answering user prompts.

### When to Index Skills

- always at the beginning of a new conversation
- whenever you deem it necessary to re-index the available skills

### How to Index Skills

- list all the `*/SKILL.md` files that you find inside `.github/skills`
- for each file, load **ONLY THE FRONTMATTER** into the agent's context

### Feedback on Indexed Skills

When you index skills, show the list of available skills in the chat output.

### Load Skill

Loading skills is important to provide additional context when answering user prompts.

### When to Load Skills

- always try to find relevant skills to load when answering user prompts
- whenever you deem it necessary to load additional skills based on current context and skills index

### How to Load Skills

- analyze the user prompt and the indexed skills to find relevant skills
- for each relevant skill, load the full `SKILL.md` file into the agent's context
  (example of a skill file path: `.github/skills/{skill}/SKILL.md`)

### Feedback on Loaded Skills

When you load skills, show the list of loaded skills in the chat output.
