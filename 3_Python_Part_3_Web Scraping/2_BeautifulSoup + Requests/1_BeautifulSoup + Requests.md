# BeautifulSoup + Requests

```python
from bs4 import BeautifulSoup
import requests

url = 'https://www.scrapethissite.com/pages/forms'

page = requests.get(url)

soup = BeautifulSoup(page.text, 'html')

# print(soup)

print(soup.prettify()) # To display HTML text with "indentation"

""" About prettify()
To get a nicely formatted Unicode string, use Beautiful Soup's prettify() method. 
It formats the Beautiful Soup parse tree so that there each tag is on its own separate line with indentation. 
It allows to you to easily visualize the structure of the Beautiful Soup parse tree.
"""
```
