# Files 
### How to Call
open(path, [mode])
path is the file path as a string, "H:/folder/test.txt"
mode options are: 'r', 'w', 'a'. Read, write and, append respectively
Read usually requires an encoding line, this can be seen in the example later.
Write overwrites any file with the same name, or just creates one.
Append simply adds on to the file, these modes need not an encoding line.

### How to Read Lines and Append them
```python
openfile = open(filename, 'r', encoding='utf-8')
file = []  
for line in openfile:  
    file.append(line.strip())  
openfile.close() #good practice to close files
return file
```

### Opening Lines from the Internet
```python
import urllib.request
url = "https://www.prog.com"
web_page = urllib.request.urlopen(url)
for line in web_page:
	...
web_page.close()
```

### Writing Files
```python
outfile = open('myoutput.txt', 'w')
outfile.write(data)
outfile.close()
```