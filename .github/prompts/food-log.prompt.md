---
name: FoodLog
description: one apple
agent: agent
---

# Goal
  
Use the Food Tracker DB to log and read user food data.

# Load Skills

Use the Food Tracker DB skill to log new food entries and retrieve existing food data based on user prompts.

Understand the user's time references (e.g., "yesterday", "last week") and convert them to absolute dates using the Clock skill. If no specific time is mentioned, assume the current date and time.

# User Prompt

${input}
