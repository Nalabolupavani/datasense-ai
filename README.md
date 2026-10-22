# DataSense AI examples

Use these examples to check whether the skill follows its workflow. The expected behaviour describes what a good answer should include; it does not claim that a test has already been run.

## Example 1: Missing values

**Request:** "Check this data for missing values and suggest what to do."

**Expected behaviour:** Report missing-value counts by column. Explain that the right treatment depends on the column meaning and amount of missing data. Do not fill every missing value with zero automatically.

## Example 2: Duplicate records

**Request:** "Find duplicate records in my spreadsheet."

**Expected behaviour:** Report the number of exact duplicate rows if the data can be inspected. Explain that repeated values in one column do not necessarily mean an entire row is a duplicate. Ask before deleting records.

## Example 3: Explain a relationship

**Request:** "Does attendance affect student scores?"

**Expected behaviour:** Examine the available attendance and score data if possible. Describe any observed association without claiming that attendance caused the scores. Mention data limitations.

## Example 4: No file attached

**Request:** "Analyze my dataset."

**Expected behaviour:** Do not pretend to have seen the data. Ask the user to upload the file or paste a sample and, if useful, ask what they want to find out.
