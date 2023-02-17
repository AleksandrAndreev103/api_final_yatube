## Оглавление
<ul>
 <li><a href="#Описание">Описание</a> </li>
 
 <li>
   <a href="#Как запустить проект">Как запустить проект</a>
   <ul>
     <li><a href="#Windows">Windows</a></li>
     <li><a href="#MAC OS/Linux(Ubuntu)">MAC OS/Linux(Ubuntu)</a></li>
     <li><a href="#Recommendation-System-Models">Recommendation System Models</a></li>
   </ul>
 </li>
 <li>

# Описание:


*API на Python для блога с комментариями. Можно регистрироваться, подписываться на понравившихся писателей, обсуждать написанное в комментариях.*



# Как запустить проект:

  
# Windows
Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/infinitum6666/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python -m venv env
```

```
source venv/Scripts/activate
```

Установить зависимости из файла requirements.txt:

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```

Запустить проект:

```
python manage.py runserver
```
<p align="right">(<a href="#top">Наверх</a>)</p>

# MAC OS/Linux(Ubuntu)
Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/infinitum6666/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source venv/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip3 install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

<p align="right">(<a href="#top">Наверх</a>)</p>


# Примеры
## Получение публикаций
## Получить список всех публикаций. При указании параметров limit и offset выдача должна работать с пагинацией.

### QUERY PARAMETERS
```
limit[^1].	

offset[^2].

  [^1]: integer
Количество публикаций на страницу
  [^2]: integer
Номер страницы после которой начинать выдачу
```

### Responses
- 200 Удачное выполнение запроса без пагинации


## Получить JWT-токен
## Получение JWT-токена.

### REQUEST BODY SCHEMA: 

```
username [^1].
password [^2].

  [^1]: required
string
  [^2]: required
string

```
### Responses

- 200 Удачное выполнение запроса
- 400 Отсутствует обязательное поле в теле запроса
- 401 Переданная учетная запись не существует

## Создание публикации
## Добавление новой публикации в коллекцию публикаций. Анонимные запросы запрещены.

### REQUEST BODY SCHEMA: 

```
text[^1].
image [^2].
group [^3].

  [^1]: required
string (текст публикации)
  [^2]: string or null <binary>
  [^3]: integer or null (id сообщества)
```

### Responses

- 201 Удачное выполнение запроса
- 400 Отсутствует обязательное поле в теле запроса
- 401 Запрос от имени анонимного пользователя


<p align="right">(<a href="#top">Наверх</a>)</p>
