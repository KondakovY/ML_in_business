Итоговый проект курса "Машинное обучение в бизнесе"
Стек:
- ML: sklearn, pandas, numpy
- API: flask
- Данные: Kaggle - https://www.kaggle.com/arashnic/hr-analytics-job-change-of-data-scientists

Задача: Предсказать риск возможной смены работы, исходя из персональных характеристик работника. Бинарная классификация

Используемые признаки:
- city_development_index (float)
- training_hours (int)
- gender (text)
- education_level (text)
- enrolled_university (text)
- major_discipline (text)
- experience (text)
- relevent_experience (text)
- last_new_job (text)
- company_size (text)
- company_type (text)
- city (text)

Преобразования признаков: OneHotEncoder, CatBoostEncoder

Модель: CatBoost

Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/KondakovY/ML_in_business.git
$ cd ../ML_project
$ docker-compose up -d
```

Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/ML_in_business/lesson_9/ML_project/app/models
### Можно отправить POST-запрос на 127.0.0.1:8180/predict c полями, указанными в "Признаках"
