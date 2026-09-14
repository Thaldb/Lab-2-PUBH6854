# AI Usage Disclosure

## Tool used

I used OpenAI Codex in the Codex desktop app with a GPT-5 model on September 14, 2026. I used it as an interactive guide while completing this assignment rather than asking it to produce the finished submission independently.

## Assignment planning

I asked Codex to walk me through Lab 2 using learning checkpoints similar to the process I used for Lab 1. It helped me connect each part of the rubric to a repository file or notebook section. It also suggested examining observed 10-year CHD prevalence across age groups and current-smoking status as a question that could be implemented consistently in Python and R.

I chose to continue with this question because it was appropriate for the epidemiology dataset and required a meaningful transformation, grouped analysis, visualization, and interpretation.

## Python assistance

Codex explained how to:

- Create and activate a Conda environment
- Start JupyterLab and create a Python notebook
- Load the public CSV using `pandas`
- Examine variable coding and missing values
- Create age categories using `pd.cut()`
- Group participants and calculate counts and proportions
- Calculate percentage-point differences
- Create and label a grouped bar chart
- Execute and export the notebook using `nbconvert`

I typed and ran the notebook cells, reviewed the resulting tables and graph, and confirmed that the analysis contained 4,240 participants and 644 recorded CHD cases.

## R assistance

Codex helped me translate the same analysis into R Markdown using `dplyr` and `ggplot2`. It explained the roles of `select()`, `filter()`, `mutate()`, `group_by()`, and `summarise()`.

When R reported that it could not find `mutate()`, Codex explained that `dplyr` was not attached in the current R session. I added a setup chunk containing `library(dplyr)`, `library(ggplot2)`, and `library(scales)`. I restarted R and knitted the document to confirm that the packages loaded automatically in a clean session.


## How I verified the work

I personally:

- Confirmed that both languages loaded 4,240 rows and 16 columns
- Checked that age, smoking status, and the CHD outcome had no missing values
- Verified the age-group totals
- Confirmed that the grouped results represented all 4,240 participants and 644 CHD cases
- Compared the Python and R results
- Restarted and executed the Python notebook from top to bottom
- Knitted the R Markdown notebook in a clean R session
- Opened both rendered HTML files and checked their contents
- Revised the written interpretation in my own words

## What I learned

This assignment helped me understand why reproducibility requires more than saving completed output. The environments, package records, source notebooks, and clean execution tests allow another person to reproduce the analysis.
