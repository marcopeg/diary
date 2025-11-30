---
name: Food Status
description: Provides a summary of the current day's food intake and nutritional progress. Responds to the "/FoodStatus" command.
version: 1.0.0
---

## Overview

The Food Status skill provides a quick summary of the current day's food intake and nutritional progress. It reads from the Food Journal Database and presents a concise status report.

Related skills:

- [Food Journal DB](../food-journal-db/SKILL.md): store and read food data
- [Clock](../clock/SKILL.md): get current date/time

## Command

The skill responds to the `/FoodStatus` command (case-insensitive).

## Execution Plan

When the user invokes `/FoodStatus`, follow this plan:

1. Get the current date using the `Clock` skill
2. Read today's food journal entry from `{root}/food-journal/YYYY-MM-DD.md`
3. If no entry exists for today, report that no food has been logged yet
4. If an entry exists, extract and present:
   - The daily nutritional facts summary table
   - A brief status of each meal section that has entries
   - Recommendations for remaining meals based on goals

## Output Format

Present the status in the following format. Note: The status output includes a "Remaining" column (Goal - Consumed) which is specific to this status view and differs from the Food Journal DB format.

```markdown
## 📊 Food Status for {Day of Week}, {Date}

### Daily Progress

| Nutritional Facts | Goal | Consumed | Remaining | Progress |
|-------------------|-----:|---------:|----------:|---------:|
| Calories          | 2100 |      907 |      1193 |      43% |
| Carbs             | 230g |      68g |      162g |      30% |
| Fats              |  70g |      48g |       22g |      68% |
| Proteins          | 160g |      57g |      103g |      36% |
| Fibers            |  35g |       3g |       32g |       9% |

### Meals Logged

- ✅ Breakfast: 165 cal
- ✅ Morning Snack: 57 cal
- ✅ Lunch: 685 cal
- ⬜ Afternoon Snack: not logged
- ⬜ Dinner: not logged
- ⬜ Night Snack: not logged

### Recommendations

{Brief recommendations based on remaining nutritional needs and goals from GOALS.md}
```

## Status Indicators

- ✅ = meal logged with entries
- ⬜ = meal section empty or not logged

## Recommendations Logic

1. Read the user's goals from `{root}/food-journal/GOALS.md`
2. Calculate remaining nutritional needs
3. Provide actionable suggestions:
   - If protein is below 50% progress and it's past lunch: prioritize protein-rich foods
   - If fiber is below 30% progress: suggest vegetables and whole grains
   - If fats are above 80% progress: recommend lean protein sources
   - If calories are close to goal: suggest lighter options

## No Entry Scenario

If no food journal entry exists for today, output:

```markdown
## 📊 Food Status for {Day of Week}, {Date}

No food has been logged for today yet.

To start logging, tell me what you've eaten! For example:
- "I had coffee and toast for breakfast"
- "For lunch I ate a chicken salad"
```
