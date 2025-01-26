# BeautifulSoup + Requests

```python
from bs4 import BeautifulSoup
import requests

url = 'https://www.scrapethissite.com/pages/forms/'

page = requests.get(url)

soup = BeatifulSoup(page.text, 'html')

print(soup)

print(soup.prettify()) # display html text with "indentation"
```
