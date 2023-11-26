# Basic_DataEngineering_ByPSU : Day 2

## Replace Missing (or) Generic Value
### Ex1

```python
import numpy as np
import pandas as pd

temp_dict = {'one':[1,2,3,4,5,2000], 'two':[1000,np.nan,3,4,5,6]}
df = pd.DataFrame(temp_dict)
df
```

<details>
<summary>Result : </summary>

```
	one	two
0	1	1000.0
1	2	NaN
2	3	3.0
3	4	4.0
4	5	5.0
5	2000	6.0
```

</details>

```python
df = pd.DataFrame(temp_dict)
df.replace({1000:-10})
df
```

<details>
<summary>Result : </summary>

```

one	two
0	1	1000.0
1	2	NaN
2	3	3.0
3	4	4.0
4	5	5.0
5	2000	6.0
```

</details>

```python
df.replace({1000:-10, 2000:-20})
```

<details>
<summary>Result : </summary>

```

one	two
0	1	-10.0
1	2	NaN
2	3	3.0
3	4	4.0
4	5	5.0
5	-20	6.0
```

</details>


### Ex2
```python
import numpy as np
import pandas as pd
temp_dict = {'one':[1,2,3,4,5,2000], 'two':[1000,np.nan,3,4,5,6]}
df = pd.DataFrame(temp_dict)
df
```





---
<details>
<summary>Result : </summary>

```

```

</details>