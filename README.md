# Проект YaMDb
![yamdb_workflow](https://github.com/Xaviespb/yamdb_final/workflows/yamdb_workflow/badge.svg)
#### Проект YaMDb собирает отзывы (Review) пользователей на произведения (Titles). Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий (Category) может быть расширен администратором (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»).

#### Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

#### В каждой категории есть произведения: книги, фильмы или музыка. Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Насекомые» и вторая сюита Баха.

#### Произведению может быть присвоен жанр (Genre) из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»). Новые жанры может создавать только администратор.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Xaviespb/yamdb_final.git
```

```
cd yamdb_final
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Перейти в папку с файлом docker-compose.yaml и
собрать контейнеры (infra_db_1, infra_web_1, infra_nginx_1):

```
docker-compose up -d --build
```

Выполнить миграции:

```
docker-compose exec web python manage.py migrate
```

Србрать статику:

```
docker-compose exec web python manage.py collectstatic --no-input
```

Остановка контейнера:

```
docker-compose down -v
```
