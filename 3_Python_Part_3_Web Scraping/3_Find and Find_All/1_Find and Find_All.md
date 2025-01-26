# Find and Find_All

```python
from bs4 import BeautifulSoup
import requests

url = 'https://www.scrapethissite.com/pages/forms/'

page = requests.get(url)

soup = BeautifulSoup(page.txt, 'html')

print(soup)

soup.find('div')

soup.find_all('div')

soup.find_all('div', class_ = 'col-md-12')

soup.find_all('p')

soup.find_all('p', class_ = 'lead')

soup.find_all('p', class_ = 'lead').text # Error

soup.find('p', class_ = 'lead').text

soup.find('p', class_ = 'lead').text.strip()

soup.find_all('tr')

soup.find_all('th')

soup.find_all('td')

soup.find('th')

soup.find('th').text

soup.find('th').text.strip()
```

