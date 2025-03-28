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
| 8. | find xth percentile in a column | data['column_name'].quantile(0.99) | gives 99th percentile; |
| 9. | get column-names that "start" with a pattern | data.columns[data.columns.str.startswith('pattern')].tolist() |If <code>.tolist()</code> isn't used, it returns a Pandas Index object which looks like a Py list but is not really a list.|
| 10. | get column-names which "contain" a pattern | data.columns[data.columns.str.contain('pattern')].tolist() | |
| 11. | add another list to an existing list | list1.extend(list2) | |
| 12. | add values row-wise in selected columns and store in a new column| data['new_column'] = data[columns].sum(axis=1)| axis=1 means "sum across columns for each row" |
| 13. | replace values in a column with another value | data['column-name'] = data['column-name'].replace({'old-value1':'new-value1', 'old-value2':'new-value2'}) |

