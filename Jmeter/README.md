# Jmeter Homeworks 1,2,3
## Homework_1: Отправка запросов на семь эндпоинтов.
## Homework_2: Извлечение, установка и передача переменных в окружение. Проверка статус кода и значений переменных. 
### `JSON Extractor, BeanShell Assetion, BeanShell PreProcessor, Response Assertion.`
## EX_1:
URL: http://162.55.220.72:5005/user_info

Method: POST

Request (RAW JSON):
```sh
age: int
salary: int
name: str
auth_token: str
```

Response:
```sh
{'start_qa_salary':salary,
 'qa_salary_after_6_months': salary * 2,
 'qa_salary_after_12_months': salary * 2.9,
 'person': {'u_name':[user_name, salary, age],
                                'u_age':age,
                                'u_salary_1.5_year': salary * 4}
                                }
```
## Task:
- Достать Respose значение auth_token из http://162.55.220.72:5005/login, установить его в окружение и использовать в этом запросе;
- Достать из Respose значение из поля 'qa_salary_after_6_months' и передать в поле salary запроса http://162.55.220.72:5005/new_data.
***
## EX_2:
URL: http://162.55.220.72:5005/new_data

Method: POST

Request form data:
```sh
age: int
salary: int
name: str
auth_token
```
Response:
```sh
{'name':name,
  'age': int(age),
  'salary': [salary, str(salary*2), str(salary*3)]}
```
## Task:
- Достать из Respose значение из поля 'name' и передать в поле name запроса http://162.55.220.72:5005/test_pets_info.
***
## EX_3:
URL: http://162.55.220.72:5005/test_pet_info

Method: POST

Request form data:
```sh
age: int
weight: int
name: str
auth_token
```
Response:
```sh
{'name': name,
 'age': age,
 'daily_food':weight * 0.012,
 'daily_sleep': weight * 2.5}
```
## Task:
- Достать из Respose значение из поля age и передать в поле age запроса http://162.55.220.72:5005/get_test_user.
***
Задание ***
- Изучить как работают Response Assertion;
- Сделать Assertion на провекрку статус код 200;
- Сделать Assertion на провекрку 'daily_food':weight * 0.012.
***
URL: http://162.55.220.72:5005/get_test_user
 
Method: POST

Request form data:
```sh
age: int
salary: int
name: str
auth_token
```
Response
```sh
{'name': name,
 'age':age,
 'salary': salary,
 'family':{'children':[['Alex', 24],['Kate', 12]],
 'u_salary_1.5_year': salary * 4}
  }
```
## Task:
Задание ***
- Сделать Assertion на провекрку статус код 200;
- Сделать Assertion на провекрку 'salary': salary.
***
## Homework_3: Нагрузочное тестирование сайта iHerb по Smoke сценариям.
### `HTTP(S) Test Script Recorder, Test Fragment, Recording Controller, Transaction Controller.`
