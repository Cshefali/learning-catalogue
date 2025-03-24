## Common How-Tos in Pandas/Matplotlib

| Sr. No. | How To .. | Code | Comments |
| :-- | :-- | :-- | :-- |
| 1. | remove an element from list (inplace) | list1.remove('v2') | list1 = ['v1', 'v2', 'v3'] |
| 2. | find total total data-points in each category in a column | data['column-name'].value_counts() | |
| 3. | see summary stats of numerical columns in dataframe | data.describe() | to see summary stats of specific set of columns: data[columns-list].describe() |
| 4. | convert all column names to lowercase | data.columns = data.columns.str.lower() | |
| 5. | extract date component from date-time values | data['date_column'].date() | |
| 6. | extract number of days from values like <code>[datetime.timedelta(days=663), datetime.timedelta(days=113)]</code> | data['date_column'].dt.days | |
| 7. | extract "year" from a date value | date.year | e.g. date1 = '2024-03-24'; date1.year gives 2024| |