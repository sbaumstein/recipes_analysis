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

The relevant cleaned data:

|   calories |   minutes |   average_rating |
|-----------:|----------:|-----------------:|
|      138.4 |        40 |                4 |
|      595.1 |        45 |                5 |
|      194.8 |        40 |                5 |
|      878.3 |       120 |                5 |
|      267   |        90 |                5 |

<iframe
  src="../dist_cals_plot.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

<iframe
  src="../scatter_plot.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

Pivot Table:
| calorie_bin   |    mean |   count |
|:--------------|--------:|--------:|
| (0, 500]      | 4.62621 |   61076 |
| (500, 1000]   | 4.62457 |   15458 |
| (1000, 1500]  | 4.61285 |    2416 |
| (1500, 2000]  | 4.61402 |     826 |
| (2000, 2500]  | 4.64426 |     434 |

## Framing a Prediction Problem

- **Prediction Problem:** Can we predict the average rating of a recipe based on its calorie content and the minutes needed to cook the recipe?
-**Type of Prediction:** Regression