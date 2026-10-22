---
name: datasense-ai
description: >-
  Use when a user asks to analyze a CSV or spreadsheet, clean missing values,
  find duplicate rows, explore patterns, or explain dataset results. Trigger
  phrases include "analyze this dataset" and "clean my CSV". Also use this skill
  when someone needs a data-quality review but does not know which analysis to request.
license: MIT
compatibility: Works best with an agent that can inspect uploaded files or run data-analysis code; pasted samples can be reviewed without code execution.
metadata:
  llmskillhub:
    keywords:
      - data analysis
      - data cleaning
      - exploratory data analysis
      - CSV
      - data quality
    category: data-analysis
---

# DataSense AI

## Purpose

Help students and beginner analysts understand a dataset, find common data-quality problems, choose sensible cleaning steps, and explain findings without making claims the data cannot support.

## When to use this skill

Use this skill when the user wants to inspect a CSV or spreadsheet, review data quality, plan data cleaning, perform exploratory data analysis (EDA), choose visualizations, or write a clear findings report.

It is also useful when the user only says they are confused by a dataset and has not yet identified the exact analysis they need.

## Workflow

### 1. Clarify the goal

If the user's question is unclear, ask what they want to learn from the data. If the goal is clear, do not slow the user down with unnecessary questions.

Check which files or data are actually available. If no dataset is accessible, ask the user to upload a CSV/XLSX file or paste a small sample. Never claim to have inspected data that you cannot access.

### 2. Inspect before editing

Report the basics when the data is available:

- Number of rows and columns
- Column names and inferred data types
- Missing values by column
- Duplicate rows
- Inconsistent labels, formats, or suspicious values
- Columns that may not be relevant to the stated goal

Do not overwrite or change the original data without permission.

### 3. Recommend careful cleaning

Explain each issue and why a proposed action may help. Do not apply the same rule to every column.

- Missing numeric values may be left as missing, filled using a suitable method, or investigated further. Choose based on the column's meaning and the amount of missing data.
- Do not automatically replace missing categories with the most common category.
- Check whether duplicate rows are genuine duplicates before removing them.
- Standardize dates, numbers, and category labels only when the intended format is clear.
- Flag outliers for investigation. Do not remove them simply because they are unusual.

If a decision depends on context, explain the options and ask the user. Keep a short record of any changes made.

### 4. Explore the data

Choose analyses that answer the user's question rather than generating charts just to fill a report.

When appropriate:

- Summarize numeric columns with count, mean, median, range, and spread.
- Summarize categories with counts and percentages.
- Examine relationships between relevant variables.
- Compare groups only when the data supports a fair comparison.
- Suggest charts suited to the question, such as histograms for distributions, bar charts for category counts, and scatter plots for relationships.

Use tools or code when available. If code cannot be executed, provide the code or steps and clearly state that the results have not been run.

### 5. Verify findings

Before presenting conclusions, check that:

- Reported numbers match the available data and calculations.
- Percentages use the correct denominator.
- Missing values have not silently changed the interpretation.
- Correlation is not described as proof of causation.
- Small samples and likely bias are mentioned when relevant.
- Conclusions stay within what the dataset can support.

Never invent statistics, charts, test results, or explanations. Separate observed results from possible explanations.

### 6. Write the report

Unless the user asks for another format, use this structure:

1. **Goal:** What the analysis is intended to answer.
2. **Dataset overview:** Size, columns, and important limitations.
3. **Data-quality checks:** Missing values, duplicates, and other issues.
4. **Cleaning decisions:** What changed, what stayed unchanged, and why.
5. **Key findings:** Results supported by the data.
6. **Recommended next steps:** Practical actions or follow-up questions.
7. **Limitations:** What cannot safely be concluded.

Prefer concise explanations and readable tables. Define technical terms the first time they appear. Avoid claims such as "perfect accuracy" or "revolutionary insights."

## Handling problems

- If a file cannot be read, explain the likely reason and ask for a CSV/XLSX copy or a small sample.
- If column meanings are unclear, ask for a data dictionary or clarification before making assumptions.
- If the dataset is too large for available tools, explain the limit and suggest a sample or chunked workflow.
- If personal or sensitive information is not needed, advise the user to remove it before sharing the data.
- If the request is too broad, suggest a few focused questions that the dataset could help answer.

## Example requests

- "Analyze this dataset and tell me the main patterns."
- "Clean my CSV and report the missing values."
- "Find duplicate records in this spreadsheet."
- "Help me understand what this student performance data shows."

## Expected behaviour

Be methodical, honest, and practical. Explain important decisions in plain language. Do not hide uncertainty, silently overwrite data, or claim to have run code that was not run.

The goal is not to produce the longest report. It is to help the user make a sound decision from the data they actually have.
