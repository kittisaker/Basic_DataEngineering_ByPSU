# Basic_DataEngineering_ByPSU : Day 1

## Creates a DataFrame using pandas

### Create DataFrame from list
```python
import pandas as pd

mydataset = { 'cars': ['BMW', 'Volvo', 'Ford'], 'passings': [3, 7, 2] }

myvar = pd.DataFrame(mydataset)
print(myvar)
```

<details>
<summary>Result : </summary>

```
        0
0   Apple
1      10
2  Orange
3    55.5
```

</details>

#### Index

```python
fruits_df = pd.DataFrame(fruits_list, index=['Fruit1', 'Fruit2', 'Fruit3', 'Fruit4'])
print(fruits_df)
```

<details>
<summary>Result : </summary>

```
             0
Fruit1   Apple
Fruit2      10
Fruit3  Orange
Fruit4    55.5
```

</details>


#### Columns
```python
fruits_df = pd.DataFrame(fruits_list, index=['Fruit1', 'Fruit2', 'Fruit3', 'Fruit4'], columns=['Fruit'])
print(fruits_df)
```

<details>
<summary>Result : </summary>

```
         Fruit
Fruit1   Apple
Fruit2      10
Fruit3  Orange
Fruit4    55.5
```

</details>

###  Create DataFrame from dict
```python
import pandas as pd

# Create dict object
student_dict = {"name": ["Joe", "Nat", "Harry"],
                        "age": [20, 21, 19],
                        "marks": [85.10, 77.80, 91.54]}

# Create DataFrame from dict
student_df = pd.DataFrame(student_dict)
print(student_df)
```

<details>
<summary>Result : </summary>

```
    name  age  marks
0    Joe   20  85.10
1    Nat   21  77.80
2  Harry   19  91.54
```

</details>

#### Index
```python
student_df = pd.DataFrame(student_dict, index = ["R0", "R1", "R2"])
print(student_df)
```

<details>
<summary>Result : </summary>

```
     name  age  marks
R0    Joe   20  85.10
R1    Nat   21  77.80
R2  Harry   19  91.54
```

</details>

#### Reset index
```python
student_df = student_df.reset_index()
print(student_df)
```

<details>
<summary>Result : </summary>

```
  index   name  age  marks
0    R0    Joe   20  85.10
1    R1    Nat   21  77.80
2    R2  Harry   19  91.54
```

</details>

### Read the CSV File Using pandas
#### Download the CSV File (command prompt)
```shell
!wget --no-check-certificate 'https://docs.google.com/uc?export=download&id=1ZIyi1Xh0qhJoPuicKcFYllx1e6m1iiDV' -O mystudents.csv
```

#### Read the CSV File Using pandas
```python
import pandas as pd

df = pd.read_csv('/content/mystudents.csv')
print(df)
```

<details>
<summary>Result : </summary>

```shell
    Student ID    Name  Age   Score Grade       Province
0   5010110405    Jane   31   53.75     D        Songkla
1   5110110580     Joe   32   37.65     E        Bangkok
2   6310110042     Dan   19  ขาดสอบ   NaN      Chiangmai
3   6310110073    Tida   18      65    C+        Bangkok
4   6310110076    Jane   21      62     C           Yala
5   6310110092   Smile   20    60.5     C      Chiangrai
6   6310110107    Cole   18     NaN   NaN         Phuket
7   6310110109   Tommy   19   51.75     D        Bangkok
8   6310110145   Jerry   19   64.75     C            Nan
9   6310110147    Anna   18   28.25     E          Krabi
10  6310110150   Scott  -15    24.5     E      Ang Thong
11  6310110243     Utz   20   56.25    D+        Kalasin
12  6310110250    Rome   19   17.25     E   Kanchanaburi
13  6310110251   Ronda   18   59.63    D+        Lampang
14  6310110260   Wanda   21    54.5     D        Bangkok
15  6310110349    Nita   20   32.75     E   Mae Hong Son
16  6310110363    Nida   18      50     D           Loei
17  6310110383    Swat   19    88.5     A  Nakhon Pathom
18  6310110389     Tim   19   29.38     E        Bangkok
19  6310110401  Andrew   18   75.13     B        Bangkok
```

</details>

### DataFrame with method and attribute

#### DataFrame : reset_index()
```python
df.reset_index()
```

<details>
<summary>Result : </summary>

```
	index	Student ID	Name	Age	    Score	Grade	Province
0	0	    5010110405	Jane	31	    53.75	D	    Songkla
1	1	    5110110580	Joe	    32	    37.65	E	    Bangkok
2	2	    6310110042	Dan	    19	    ขาดสอบ	NaN	    Chiangmai
3	3	    6310110073	Tida	18	    65	    C+	    Bangkok
4	4	    6310110076	Jane	21	    62	    C	    Yala
5	5	    6310110092	Smile	20	    60.5	C	    Chiangrai
6	6	    6310110107	Cole	18	    NaN	    NaN	    Phuket
7	7	    6310110109	Tommy	19	    51.75	D	    Bangkok
8	8	    6310110145	Jerry	19	    64.75	C	    Nan
9	9	    6310110147	Anna	18	    28.25	E	    Krabi
10	10	    6310110150	Scott	-15	    24.5	E	    Ang Thong
11	11	    6310110243	Utz	    20	    56.25	D+	    Kalasin
12	12	    6310110250	Rome	19	    17.25	E	    Kanchanaburi
13	13	    6310110251	Ronda	18	    59.63	D+	    Lampang
14	14	    6310110260	Wanda	21	    54.5	D	    Bangkok
15	15	    6310110349	Nita	20	    32.75	E	    Mae Hong Son
16	16	    6310110363	Nida	18	    50	    D	    Loei
17	17	    6310110383	Swat	19	    88.5	A	    Nakhon Pathom
18	18	    6310110389	Tim	    19	    29.38	E	    Bangkok
19	19	    6310110401	Andrew	18	    75.13	B	    Bangkok
```

</details>

#### DataFrame : set_index()
```python
df.set_index('Name')
```

<details>
<summary>Result : </summary>

```
	    Student ID	Age	Score	Grade	Province
Name					
Jane	5010110405	31	53.75	D	    Songkla
Joe	    5110110580	32	37.65	E	    Bangkok
Dan	    6310110042	19	ขาดสอบ	NaN	    Chiangmai
Tida	6310110073	18	65	    C+	    Bangkok
Jane	6310110076	21	62	    C	    Yala
Smile	6310110092	20	60.5	C	    Chiangrai
Cole	6310110107	18	NaN	    NaN	    Phuket
Tommy	6310110109	19	51.75	D	    Bangkok
Jerry	6310110145	19	64.75	C	    Nan
Anna	6310110147	18	28.25	E	    Krabi
Scott	6310110150	-15	24.5	E	    Ang Thong
Utz	    6310110243	20	56.25	D+	    Kalasin
Rome	6310110250	19	17.25	E	    Kanchanaburi
Ronda	6310110251	18	59.63	D+	    Lampang
Wanda	6310110260	21	54.5	D	    Bangkok
Nita	6310110349	20	32.75	E	    Mae Hong Son
Nida	6310110363	18	50	    D	    Loei
Swat	6310110383	19	88.5	A	    Nakhon Pathom
Tim	    6310110389	19	29.38	E	    Bangkok
Andrew	6310110401	18	75.13	B	    Bangkok
```

</details>


#### DataFrame : head()
```python
df.head()   # return first 5 row by default

df.head(10) # return first 10 row

df.head(-5) # return first all - 5 row, 20 - 5 = 15 row
```

#### DataFrame : tail()
```python
df.tail()   # return last 5 row by default
df.tail(10) # return last 20 row
```

#### DataFrame : sample()
```python
df.sample()
```

#### DataFrame : df.info()
```python
df.info()
```

#### DataFrame : df.describe()
```python
df.describe()
```

#### DataFrame : index
```python
df.index
```

#### DataFrame : info
```python
df.info
```

#### DataFrame : dtypes
```python
df.dtypes
```

#### DataFrame : values
```python
df.values
```

#### DataFrame : empty
```python
df.empty
```

#### DataFrame : shape
```python
df.shape
```

#### DataFrame : size
```python
df.size
```

#### DataFrame : describe
```python
df.describe
```

#### DataFrame : flags
```python
df.flags
```

#### DataFrame with Columns 
```python
df["Name"]

df[ ['Name', 'Age'] ]

df.Name

df.get('Name')

df.get(['Name', 'Age'] )
```

```python
df[0:2]     # start : stop

df[0:10:3] # start : stop : step
```

#### DataFrame : at[row_label, column_label]
```python
df.at[0, 'Name']        

df.at[4, "Province"]
```

#### DataFrame : iat[row_index, column_index]
```python
df.at[0, 'Name']        

df.at[4, "Province"]
```

#### DataFrame : loc[row_label], loc[row_label, column_label], loc[[row_label1, row_label2], [column_label1, column_label2]] 
```python
df.loc[[2, 4]]    
df.loc[[11, 2, 5]]


df.loc[[2, 4], ["Name"]]
df.loc[0:11:2, ['Score', 'Grade']] # start:stop:step, columns

df.loc[: , :]
```

#### DataFrame : iloc[row_index], iloc[row_index, column_index], iloc[[row_index1, row_index2], [column_index1, column_index2]]
```python
df.iloc[0, 0]
```

#### DataFrame : notnull(), isnull()
```python
df.notnull() # NaN : ruturn False

df.isnull()  # NaN : ruturn True

df["Score"].isnull()

df["Score"].isnull().sum()
```

#### Numpy : nan
```python
import pandas as pd
import numpy as np

student_dict = {"name": ["Joe", "Sam", "Harry"], "age": [20, 21, 19], "marks": [85.10, np.nan, 91.54]}
df = pd.DataFrame(student_dict)
df
```

<details>
<summary>Result : </summary>

```
	name	age	marks
0	Joe	20	85.10
1	Sam	21	NaN
2	Harry	19	91.54
```

</details>

#### DataFrame : fillna 
```python
print("Replace NaN with '0':")
df1 = df.fillna(0)
df1
```

#### DataFrame : mean()
```python
df.mean()
``` 

<details>
<summary>Result : </summary>

```
age      20.00
marks    88.32
dtype: float64
```

</details>

```python
# print(df.mean())
print("\nReplace NaN with means:")
df1 = df.fillna(df.mean())
df1
```

<details>
<summary>Result : </summary>

```
name	age	marks
0	Joe	20	85.10
1	Sam	21	88.32
2	Harry	19	91.54
```

</details>

#### DataFrame : fillna With value
```python
student_dict = {"name": ["Joe", "Sam", "Harry"], "age": [20, 21, 19], "marks": [85.10, np.nan, 91.54]}
df = pd.DataFrame(student_dict)
df

change_dict = {'name': 'John Doe', 'marks': -100}
df1 = df.fillna(value=change_dict)
df1
```

<details>
<summary>Result : </summary>

```
	name	age	marks
0	Joe	20	85.10
1	Sam	21	NaN
2	Harry	19	91.54

	name	age	marks
0	Joe	20	85.10
1	Sam	21	-100.00
2	Harry	19	91.54
```

</details>

#### DataFrame : reindex()
```python
df1 = df.reindex([0, 1, 2, 3])
df1

change_dict = {'name': 'John Doe', 'marks': -100}
df1 = df1.fillna(value=change_dict)
df1
```

<details>
<summary>Result : </summary>

```
	name	age	    marks
0	Joe	    20.0	85.10
1	Sam	    21.0	NaN
2	Harry	19.0	91.54
3	NaN	    NaN	    NaN


	name	    age	    marks
0	Joe	        20.0	85.10
1	Sam	        21.0	-100.00
2	Harry	    19.0	91.54
3	John Doe	NaN	    -100.00
```

</details>

---