# python-flask-docker
Итоговый проект курса "Машинное обучение в бизнесе"

Стек:

ML: sklearn, pandas, numpy
API: flask
Данные: .\app\models\train.csv

Задача: предсказать по тексту комментария является ли он токсичным или нет (англоязычный текст). Бинарная классификация

Используемые признаки:

- comment_text (text, en)

Преобразования признаков: tfidf

Модель: logreg

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/kartseves/GB_MLinBsns_CoursePrj.git
$ cd GB_MLinBsns_CoursePrj
$ docker build -t kartseves/gb_mlinbsns_courseprj .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/app/app/models kartseves/gb_mlinbsns_courseprj
```

### Переходим на localhost:8181
