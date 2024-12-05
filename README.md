# recipes_analysis
## Introduction
This project examines a recipe dataset containing nutritional and rating information. 
The central question is: **What is the relationship between calories and average ratings?**

- **Number of rows**: 83782  
- **Relevant columns**:  
  - `nutrition`: List of all recipes nutritional info (including calories)
  - `minutes`: Time required to prepare the recipe.  
  - `average_rating`: The average user rating for the recipe.

- **All columns**:  
  - 'name', 'id', 'minutes', 'contributor_id', 'submitted', 'tags',
       'nutrition', 'n_steps', 'steps', 'description', 'ingredients',
       'n_ingredients', 'average_rating'
       
## Data Cleaning
- Extracted calorie information from the nutrition column.
- Dropped rows where the calories, minutes were missing.
- Filtered  calorie values  to those <= 5000.
- Drop rows where average rating was missing.

Here’s a snapshot of the cleaned DataFrame:

|| name                    | id      | minutes | contributor_id | submitted   | ... |
|-------------------------|---------|---------|----------------|-------------|-----|
| brownies in the world best ever | 333281  | 40      | 985201         | 2008-10-27  | ... |
| in canada chocolate chip cookies | 453467  | 45      | 1848091        | 2011-04-11  | ... |
| 412 broccoli casserole   | 306168  | 40      | 50969          | 2008-05-30  | ... |
