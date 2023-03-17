I was trying to read a CSV file using Pandas and I got the following error:

```python
UnicodeDecodeError: 'utf-8' codec can't decode byte 0xb0 in position 40: invalid start byte
```

This is a simplified snipped of the initial code:
```python
# Import pandas as pd
import pandas as pd

# Import the SeoulBikeData.csv
df_data = pd.read_csv('SeoulBikeData.csv')

df_data.head()
```
The `SeoulBikeData.csv` file is from [
Seoul Bike Sharing Demand Data Set](https://archive.ics.uci.edu/ml/datasets/Seoul+Bike+Sharing+Demand#).

Description

It tries to use UTF-8 by default. So we need to specify the one suitable for the file we are loading. In my case, `encoding = 'unicode_escape'` made the trick. 


```python
# Import pandas as pd
import pandas as pd

# Import the SeoulBikeData.csv
df_data = pd.read_csv('SeoulBikeData.csv', encoding = 'unicode_escape')

df_data.head()
```

![image](https://user-images.githubusercontent.com/50062162/225784196-aba9ccf9-2929-4971-86a7-80ccb2a998b6.png)
