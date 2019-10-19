### Create a DataFrame 1
```
import pandas as pd

df1 = pd.DataFrame({
  'Product ID': [1, 2, 3, 4],
  # add Product Name and Color here
  'Product Name': ['t-shirt','t-shirt','skirt','skirt'],
  'Color':['blue','green','red','black']
})

print(df1)
```
You can pass in a dictionary to `pd.DataFrame()`. Each key is a column name and each value is a list of column values.

### Create a DataFrame 2
You can also add data using lists.
```
df2 = pd.DataFrame([
    ['John Smith', '123 Main St.', 34],
    ['Jane Doe', '456 Maple Ave.', 28],
    ['Joe Schmo', '789 Broadway', 51]
    ],
    columns=['name', 'address', 'age'])
```

### Loading and Saving CSVs
```
pd.read_csv('my-csv-file.csv')
```
```
df.to_csv('new-csv-file.csv')
```

### Inspect a DataFrame
```
import codecademylib
import pandas as pd

df = pd.read_csv('imdb.csv')
print(df.head()) # can be df.head(10)
print(df.info())
```

### Selecting
```
customers['age']
customers.age # the name of a column follows all of the rules for a variable name
clinic_north_south = df[['clinic_north','clinic_south']] # 选两列
```
```
march = df.iloc[2] # 选第三行
april_may_june = df.iloc[3:6] # 不包括6
```
```
df[df.age == 30]
df[df.age > 30]
df[df.name != 'Clara Oswald']
```
```
df = pd.DataFrame([
  ['January', 100, 100, 23, 100],
  ['February', 51, 45, 145, 45],
  ['March', 81, 96, 65, 96],
  ['April', 80, 80, 54, 180],
  ['May', 51, 54, 54, 154],
  ['June', 112, 109, 79, 129]],
  columns=['month', 'clinic_east',
           'clinic_north', 'clinic_south',
           'clinic_west'])

january_february_march = df[df.month.isin(['January', 'February', 'March'])]
```
```
df2 = df.loc[[1, 3, 5]] # 选择某几行
```
```
df3 = df2.reset_index(drop=True) 
```
```
month	clinic_east	clinic_north	clinic_south	clinic_west
0	February	51	45	145	45
1	April	80	80	54	180
2	June	112	109	79	129
```
```
df3 = df2.reset_index()
print(df3)
```
```
index	month	clinic_east	clinic_north	clinic_south	clinic_west
0	1	February	51	45	145	45
1	3	April	80	80	54	180
2	5	June	112	109	79	129
```
