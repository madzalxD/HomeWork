# Библиотека для работы с HTTP-запросами
import requests
 
# Пакет для удобной работы с данными в формате json
import json

# Для того чтобы выкинуть окончания
from pymystem3 import Mystem

# Модуль для работы со значением времени
from datetime import datetime
 
  
def getPage(page = 0):

    
    # Справочник для параметров GET-запроса
    params = {
       'page': page, # Индекс страницы поиска на HH
        'per_page': 100, # Кол-во вакансий на 1 странице
        'time': datetime.now().date()
    }
     
    req = requests.get('https://api.hh.ru/vacancies', params) # Посылаем запрос к API
    data = req.content.decode()
    req.close()
    return data

# Считываем первые 2000 вакансий
for page in range(0, 20):
     
    y = json.loads(getPage(page))
    print(y['items'])
     

print('Старницы поиска собраны')
