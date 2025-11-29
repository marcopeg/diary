---
name: FoodStatus
description: today
agent: agent
---

# Goal
  
Use the Food Tracker DB to compute the amount of food still available for the user today.

# Timeframe

Analyze the _User Prompt_ to determine the specific date or timeframe for which the food availability should be computed. If no explicit date is provided, assume the user is referring to today's food data.

# Secondary Instructions

Analyze the _User Prompt_ for any additional instructions like providing hints on how to optimize food consumption for the rest of the day, or suggesting recipes based on available food.

If no secondary instructions are provided, propose the user some follow up actions like:
- "Would you like me to suggest recipes based on your available food?"
- "Do you want tips on how to optimize your food consumption for the rest of the day?"
- "Shall I log a new food entry for you?"

# Output Format

Output order:
1. High-level progress of calories as level 1 title, e.g., "Calories: 1500/2000 Kcal (75%)"
2. A formatted table with current daily nutritional facts (calories, carbs, fats, proteins, fibers)
3. A brief revidew of the user's food consumption for the day
4. A brief suggestion what to eat next based on available food

# User Prompt

${input}
