## Common How-Tos in Pandas/Matplotlib

| Sr. No. | How To .. | Code | Comments |
| :-- | :-- | :-- | :-- |
| 1. | remove an element from list (inplace) | <code>list1.remove('v2')</code> | list1 = ['v1', 'v2', 'v3'] |
| 2. | find total total data-points in each category in a column | <code>data['column-name'].value_counts()</code> | |
| 3. | see summary stats of numerical columns in dataframe | <code>data.describe()</code> | to see summary stats of specific set of columns: data[columns-list].describe() |
| 4. | convert all column names to lowercase | <code>data.columns = data.columns.str.lower()</code> | |
| 5. | extract date component from date-time values | <code>data['date_column'].date()</code> | |
| 6. | extract number of days from values like <code>[datetime.timedelta(days=663), datetime.timedelta(days=113)]</code> | data['date_column'].dt.days | |
| 7. | extract "year" from a date value | <code>date.year</code> | e.g. date1 = '2024-03-24'; date1.year gives 2024| |
| 8. | find xth percentile in a column | <code>data['column_name'].quantile(0.99)</code> | gives 99th percentile; |
| 9. | filter column-names that "start" with a pattern | <code>data.columns[data.columns.str.startswith('pattern')].tolist()</code> |If <code>.tolist()</code> isn't used, it returns a Pandas Index object which looks like a Py list but is not really a list.|
| 10. | filter column-names which "contain" a pattern | <code>data.columns[data.columns.str.contain('pattern')].tolist()</code> | |
| 11. | add another list to an existing list | <code>list1.extend(list2)</code> | |
| 12. | add values row-wise in selected columns and store in a new column| <code>data['new_column'] = data[columns].sum(axis=1)</code>| axis=1 means "sum across columns for each row" |
| 13. | replace values in a column with another value | <code>data['column-name'] = data['column-name'].replace({'old-value1':'new-value1', 'old-value2':'new-value2'})</code> |
| 14. | rename columns | <code>data = data.rename(columns = {'oldname: newname', 'old-name2':'new-name2'})</code> | |
| 15. | to see all columns of type object | <code>s = (data.dtypes == 'object'); list(s[s].index)</code> | The 2nd line returns the names of all columns |
| 16. | sort each category in correct numeric/alphabetic order | <code>.sort_index()</cpde> | E.g. data['cat_type'].value_counts().sort_index() arranges category names alphabetically|
| 17. | clean column-names, remove special chars, spaces, convert to lowercase | <code>data.columns = [re.sub('\W+', '_', col.lower()).strip('_') for col in data.columns]</code> | "\W+" is regex pattern for all non-alphanumeric characters. all chars except [a-z][A-Z][0-9] and '_'|
| 18. | create list of all column names excluding one column | <code>columns = [col for col in data.columns if col != 'specific_column']</code> | replace "specific_column" with desired colname.|
| 19. | extract all unique alphabets in a column from all rows. | <code>data.col_name.str.extractall(r'([A-Za-z])')[0]</code> |
| 20. | check if all values follow a pattern or not | <code>data.col_name.fullmatch(r'A-Z\d{4}').all()</code> | checks if all values start with capital letter, followed by 4 digits. Useful for user-id kinda columns.|
| 21. | join one-hot encoded columns to original df | <code>data2 = data.join(pd.get_dummies(data[selected_cols], dtype='int'))</code> | `dtype=int` makes sure values in encoded cols are 0/1 instead of False/True |
| 22. | sort unique values in a column in correct order | <code>np.sort(data['Year'].unique())</code> | -- |
| 23. | find total duplicate rows | <code>data.duplicated().sum()</code> | -- |
| 24. | print all unique values in one column, for each value in another column | <code>data.groupby('Continent')['Country'].unique()</code> | prints all countries per Continent in the dataframe |
| 25. | sort a list with values | sorted(list-name) | -- |
| 26. | sort a pandas column values (Series) | data['colname'].unique().sort() | |
| 27. | sort a dataframe based on a column | data.sort_values(by='column-name') | |
| 28. | filter out specific rows when a column doesn't match some pattern | <code>data[~data['col-name'].str.match(r'regex-pattern',na=False)]</code> | this will return all rows in which col-name doesnt match given regex pattern. |
| 29. | filter out rows and columns based on multiple conditions | data.loc[(data['col1'] == 'abc') & (data['col2'] == 23) & (data['col3'].isna()), 'rating'] = 3.0 | That ".loc" part is important |
| 30. | filter out only rows with NA in a column | <code>data[data['col7'].isna()]</code> OR data[~data['col7'].notna()] | Both work. |
| 31. | group-by one column, count values of another | </code>data.groupby('col1')['col2'].value_counts()</code> | -- |
| 32. | perform a check across a given set of columns | <code>data2[(data2[columns-list] < 0).all(axis=1)]</code> | .all() checks across all columns, .any() returns if any of the columns contain -ve value.|
| 33. | delete a row based on row-index | <code>data.drop(23, inplace=True)</code> | deletes row 23; inplace = True ensures row gets deleted in same df without having to create new dataframe|
| 34. | delete rows based on condition | <code>data2 = data[(data['col1'].notna()) & (data['col2']>0)]</code> | Make sure each condition is within () |
| 35. | convert the output of <code>.value_counts()</code> to a pd dataframe | <code>temp = pd.DataFrame(data['colname'].value_counts()).reset_index()</code> | <code>.reset_index()</code> makes sure values in "colname" form a column instead of row labels.|
| 36. | round off outcome of division of series | <code>(df['count']/df['count'].sum()).round(2)</code> | .round(2) function works on series, round(..., 2) works on numpy values |
| 37. | sort values in one or more columns in df | <code>df = df.sort_values(['city', 'rating'], ascending=['True', 'False'])</code> | arranges animal name in alphabetical order, count in descending order. For e.g. to get best rated outlets per city, arrange city in ascending, but ratings in descending so that we get highest-rated outlet names first|
| 38. | extract top n (any number) values from each group | top5 = df.groupby('col-name').head(5) | the columns should be pre-arranged in correct descending/ascending order as per need.|
| 39. | group-by columns and then find mode for another column | <code>data.groupby('col1')['col2'].apply(lambda x:x.mode())</code> | simply adding .mode() wont work.|
| 40. | group-by columns & then find mean/median for another columns | <code>data.groupby('col1')['col2'].mean()</code> | use .median() for median value. |
| 41. | group-by a column and find median, mean and total number of those values in dataset | <code>data.groupby('food_name').agg(['mean', 'median', 'count']).reset_index()</code> | reset_index() converts the outcome to a PD dataframe.|
