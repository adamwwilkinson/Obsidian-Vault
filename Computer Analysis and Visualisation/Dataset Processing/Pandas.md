# Pandas
Open source data analysis and manipulation tool.

### Methods
```python
import pandas as pd
df = pf.read_cav('temporal.cav') #like cv file
df.head(10) #preview first 10 data rows
df.describe() #shows basic statistic about data
df.info() #shows metadata about the content
```

#### Display Options
```python
pd.set_opetion('display.max_rows', 500)
pd.set_option('display.max_columns', 500)
pd.set_option('display.width', 1000)
```