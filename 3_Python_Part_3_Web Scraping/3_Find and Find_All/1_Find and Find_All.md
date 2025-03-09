# Find and Find_All

```python
from bs4 import BeautifulSoup
import requests

url = 'https://www.scrapethissite.com/pages/forms'

page = requests.get(url)

soup = BeautifulSoup(page.text, 'html')

# print(soup)  

#print(soup.prettify())

#soup.find('div') # display the fisrt <div>

#soup.find_all('div') # display all the <div>

#soup.find_all('div', class_ = 'col-md-12') # display all the <div> who have the class named 'col-md-12' 

#soup.find_all('div', class_ = 'col-md-12')[4]

#soup.find_all('p')

#soup.find_all('p', class_= 'lead')

#soup.find_all('p', class_= 'lead').text # AttributeError: ResultSet object has no attribute 'text'. You're probably treating a list of elements like a single element. Did you call find_all() when you meant to call find()?

#soup.find('p', class_ = 'lead').text

#soup.find('p', class_ = 'lead').text.strip()

#soup.find_all('tr')

#soup.find_all('th')

#soup.find_all('td')

#soup.find('th')

#soup.find('th').text

soup.find('th').text.strip()

```

