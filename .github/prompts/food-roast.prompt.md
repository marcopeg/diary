---
name: FoodRoast
description: today, john oliver style
agent: agent
---

# Goal
  
Use the Food Tracker DB to read the user's food data and produce a classic roast so to make fun of their eating habits.

# Log and Style

Analyze the user's input to identify the log date that needs to be retrieved from the Food Tracker DB and the style of roast to be used (e.g., John Oliver style). Use the Food Tracker DB skill to fetch the relevant food data and then generate a humorous roast based on that data.

If no explict date is provided, assume the user is referring to today's food data.
If no style is specified, default to a John Oliver style roast.

# User Prompt

${input}
