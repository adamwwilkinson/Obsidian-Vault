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

### Plotting
Instead of writing:
```python
plt.plot(df["Rank"], df["P75th"])
```

Can instead write:

```python
df.plot(x="Rank", y="P75th")
```

Example:
Here we have the for require format be:
-   figure size is set to (10, 8)
-   x-axis tick labels are aligned vertically, not horizontally
-   legend is removed
-   a grid is applied over the plot area with line width of 1 and a line style of '--'
-   x-axis label is 'Month'
-   y-axis label is 'Sales Units'
-   plot title is 'Bathing Soap Sales Data'
```python
def bathing_soap_sales(fp, output_name= 'output.png'):  
        df = pd.read_csv(fp)  
		df.plot(x= 'month_number',y= 'bathingsoap', kind="bar", 
                    figsize= (10, 8), legend= False)  
        plt.xticks(rotation= 90)  
        plt.grid(linestyle = '--', linewidth = 1)  
        plt.xlabel('Month')  
        plt.ylabel('Sales Units')  
        plt.title('Bathing Soap Sales Data')  
        plt.show()  
  
bathing_soap_sales('company_sales_data.csv')
```