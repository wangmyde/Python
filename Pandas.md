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

### Adding a Column 
```
df = pd.DataFrame([
  [1, '3 inch screw', 0.5, 0.75],
  [2, '2 inch nail', 0.10, 0.25],
  [3, 'hammer', 3.00, 5.50],
  [4, 'screwdriver', 2.50, 3.00]
],
  columns=['Product ID', 'Description', 'Cost to Manufacture', 'Price']
)

# Add columns here
df['Is taxed?'] = 'Yes'
```
```
Product ID	Description	Cost to Manufacture	Price	Is taxed?
0	1	3 inch screw	0.5	0.75	Yes
1	2	2 inch nail	0.1	0.25	Yes
2	3	hammer	3.0	5.5	Yes
3	4	screwdriver	2.5	3.0	Yes
```
```
df = pd.DataFrame([
  [1, '3 inch screw', 0.5, 0.75],
  [2, '2 inch nail', 0.10, 0.25],
  [3, 'hammer', 3.00, 5.50],
  [4, 'screwdriver', 2.50, 3.00]
],
  columns=['Product ID', 'Description', 'Cost to Manufacture', 'Price']
)

# Add columns here
df['Sold in Bulk?'] = ['Yes', 'Yes', 'No', 'No']
print(df)
```
```
Product ID	Description	Cost to Manufacture	Price	Sold in Bulk?
0	1	3 inch screw	0.5	0.75	Yes
1	2	2 inch nail	0.1	0.25	Yes
2	3	hammer	3.0	5.5	No
3	4	screwdriver	2.5	3.0	No
```
```
import codecademylib
import pandas as pd

df = pd.DataFrame([
  [1, '3 inch screw', 0.5, 0.75],
  [2, '2 inch nail', 0.10, 0.25],
  [3, 'hammer', 3.00, 5.50],
  [4, 'screwdriver', 2.50, 3.00]
],
  columns=['Product ID', 'Description', 'Cost to Manufacture', 'Price']
)

# Add columns here
df['Revenue'] = df.Price - df['Cost to Manufacture']
print(df)
```
```
Product ID	Description	Cost to Manufacture	Price	Revenue
0	1	3 inch screw	0.5	0.75	0.25
1	2	2 inch nail	0.1	0.25	0.15
2	3	hammer	3.0	5.5	2.5
3	4	screwdriver	2.5	3.0	0.5
```
```
df = pd.DataFrame([
  ['JOHN SMITH', 'john.smith@gmail.com'],
  ['Jane Doe', 'jdoe@yahoo.com'],
  ['joe schmo', 'joeschmo@hotmail.com']
],
columns=['Name', 'Email'])

# Add columns here
df['Lowercase Name'] = df.Name.apply(lower) #还有upper可以用，也可以应用在自己这一列
print(df)
```
```
Name	Email	Lowercase Name
0	JOHN SMITH	john.smith@gmail.com	john smith
1	Jane Doe	jdoe@yahoo.com	jane doe
2	joe schmo	joeschmo@hotmail.com	joe schmo
```

### Return the first and last letters og a string
```
mylambda = lambda x: x[0] + x[-1]
print(mylambda('This is a string'))
```
```
Tg
```

### Split function
```
df['Email Provider'] = df.Email.apply(
    lambda x: x.split('@')[-1]
    )                                  # john.smith@gamil.com
                                       #从@处将名字分开，取“-1”处的，即得到“gmail.com”
```
```
print('This is a string'.split())
```
```
['This', 'is', 'a', 'string']
```
```
import codecademylib
import pandas as pd

df = pd.read_csv('employees.csv')

# Add columns here
get_last_name = lambda x: x.split()[-1]
df['last_name'] = df.name.apply(get_last_name)

print(df)
```
```
id	name	hourly_wage	hours_worked	last_name
0	10310	Lauren Durham	19	43	Durham
1	18656	Grace Sellers	17	40	Sellers
2	61254	Shirley Rasmussen	16	30	Rasmussen
3	16886	Brian Rojas	18	47	Rojas
```

### Applying a Lambda to a Row
```
import codecademylib
import pandas as pd

df = pd.read_csv('employees.csv')

total_earned = lambda row: (row.hourly_wage * 40) + ((row.hourly_wage * 1.5) * (row.hours_worked - 40)) \
	if row.hours_worked > 40 \
  else row.hourly_wage * row.hours_worked
  
df['total_earned'] = df.apply(total_earned, axis = 1) # 注意“axis = 1”这点

print(df)
```
```
id	name	hourly_wage	hours_worked	total_earned
0	10310	Lauren Durham	19	43	845.5
1	18656	Grace Sellers	17	40	680.0
2	61254	Shirley Rasmussen	16	30	480.0
3	16886	Brian Rojas	18	47	909.0
4	89010	Samantha Mosley	11	38	418.0
```

### Renaming Columns
```
df = pd.DataFrame({
    'name': ['John', 'Jane', 'Sue', 'Fred'],
    'age': [23, 29, 21, 18]
})
df.columns = ['First Name', 'Age']
```
```
Renaming Columns
```
```
import codecademylib
import pandas as pd

df = pd.read_csv('imdb.csv')

# Rename columns here
df.rename(columns={'name': 'movie_title'}, inplace = True)
print(df)
```

### Calculating Column Statistics
The general syntax for these calculations is:
```
df.column_name.command()
```
```
print(customers.age)
>> [23, 25, 31, 35, 35, 46, 62]
print(customers.age.median())
>> 35
```
```
print(shipments.state)
>> ['CA', 'CA', 'CA', 'CA', 'NY', 'NY', 'NJ', 'NJ', 'NJ', 'NJ', 'NJ', 'NJ', 'NJ']
print(shipments.state.nunique())
>> 3
```
```
print(inventory.color)
>> ['blue', 'blue', 'blue', 'blue', 'blue', 'green', 'green', 'orange', 'orange', 'orange']
print(inventory.color.unique())
>> ['blue', 'green', 'orange']
```
```
most_expensive = orders.price.max()
```

### groupby
```
df.groupby('column1').column2.measurement()
column1 is the column that we want to group by ('student' in our example)
column2 is the column that we want to perform a measurement on (grade in our example)
measurement is the measurement function we want to apply (mean in our example)
```
```
pricey_shoes = orders.groupby('shoe_type').price.max()
print(pricey_shoes)

print(type(pricey_shoes))
```

### reset_index
```
pricey_shoes = orders.groupby('shoe_type').price.max().reset_index()
print(pricey_shoes)
print(type(pricey_shoes))
```
```
shoe_type  price
0  ballet flats    498
1       sandals    498
2     stilettos    468
3        wedges    488
<class 'pandas.core.frame.DataFrame'>
```

```
import codecademylib
import numpy as np
import pandas as pd

orders = pd.read_csv('orders.csv')

cheap_shoes = orders.groupby('shoe_color').price.apply(lambda x: np.percentile(x, 25)).reset_index() 
# Let’s calculate the 25th percentile for shoe price for each shoe_color

print(cheap_shoes)
```
```
df.groupby(['Location', 'Day of Week'])['Total Sales'].mean().reset_index() #注意学习'Total Sales'不能写为df.***的形式时如何处理
```

### pivot table
Reorganizing a table in this way is called pivoting. The new table is called a pivot table.
```
# First use the groupby statement:
unpivoted = df.groupby(['Location', 'Day of Week'])['Total Sales'].mean().reset_index()
# Now pivot the table
pivoted = unpivoted.pivot(
    columns='Day of Week',
    index='Location',
    values='Total Sales').reset_index()  #不要忘记reset_index(),否则pivoted是series，而不是dataframe
```

### Merge
```
sales = pd.read_csv('sales.csv')
print(sales)
targets = pd.read_csv('targets.csv')
print(targets)

sales_vs_targets = pd.merge(sales, targets)

print(sales_vs_targets)
```
```
month	revenue
0	January	300
1	February	290
2	March	310
3	April	325
4	May	475
5	June	495
```
```
month	target
0	January	310
1	February	270
2	March	300
3	April	350
4	May	475
5	June	500
```
```
month	revenue	target
0	January	300	310
1	February	290	270
2	March	310	300
3	April	325	350
4	May	475	475
5	June	495	500
```
```
crushing_it = sales_vs_targets[sales_vs_targets.revenue > sales_vs_targets.target]
```

