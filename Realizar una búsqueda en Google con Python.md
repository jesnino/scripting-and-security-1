# Realizar una búsqueda en Google con Python
## Python 
### URL: https://www.jesusninoc.com/2016/04/25/realizar-una-busqueda-en-google-con-python/
```Python
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
browser = webdriver.Firefox()
browser.get('https://www.google.es')
findElem = browser.find_element_by_id('lst-ib')
findElem.send_keys('Python')
findElem.send_keys(Keys.RETURN)

```
