# Pandas
Open source data analysis and manipulation tool.

### Methods
```python
import pandas as pd
df = pd.read_csv('temporal.csv') 
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

#### Writing to HTML for Viewing
```python
def write_html(filename, command):
	f = open(filename, 'w')
	highlightmax_max(color='darkgreen')
	highlight_min(color='#ff0000')
	background_gradient(subset=['datascience'], cmap='BuGn')
	f.write(command.render())
	f.close()

format_dict = {'data science' : '$:.2f', 'Mes' : '{:%m-%Y}'}
#format month column to datetime format
df['Mes'] = pd.to_datetime(df['Mes'])
#apply to visualisation
write_html("demo.html", df.style.format(format_dict)) 
```