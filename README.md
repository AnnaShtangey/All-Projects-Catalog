# Список проектов

***

# NLP: Токсичность комментариев
[nlp_toxicity_of_comments.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/NLP-Toxicity-of-Comments/blob/main/nlp_toxicity_of_comments.ipynb)

Задача: классифицировать комментарии на позитивные и негативные для целей модерации.

Для получения эмбеддингов используется 2 модели Bert и модель tf-idf.
Затем обучаются регрессионные модели, выбираются наилучшие. Искомая метрика f1.
Лучшие значения метрики для моделей bert дает логистическая регрессия, для моделей tf-idf - градиентный бустинг и случайный лес.
Составлен ансамбль из трех лучших моделей. Произведено тестирование.
Библиотеки torch, transformers, pymystem3, nltk, sklearn, lightgbm.


***

# ML: Анализ оттока клиентов банка
[ml-churn-rate-in-bank.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/ML-Churn-Rate-in-Bank/blob/main/ml-churn-rate-in-bank.ipynb)

Задача: предоставлены исторические данные о поведении клиентов и расторжении договоров с банком. Спрогнозировать, уйдёт клиент из банка в ближайшее время или нет.

[Dataset](https://www.kaggle.com/barelydedicated/bank-customer-churn-modeling)

Были изучены данные, построены различные модели машинного обучения: логистическая регрессия, дерево решений, случайный лес и градиентный бустинг.
Использовались метрики качества F1-мера и площадь под ROC-кривой — AUCROC.
Исследования моделей проводились с учетом дисбаланса классов.
Наилучшие значения метрики F1 дает модель градиентного бустинга со специально подобранными параметрами.
Наилучшую метрику качества F1 получили при использовании метода upsample.
Построена ROC-кривую для нашей лучшей модели.
Была использована библиотека sklearn.

***

# ML: Тарифы связи
[ml_cell_phone_plans.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/ML-Cell-Phone-Plans/blob/main/ml_cell_phone_plans.ipynb)

Задача: необходимо понять, какой тариф выгоднее предложить клиенту.

Были рассмотрены статистики всех признаков, гистограммы распределения всех признаков в разрезе тарифов, корреляции всех признаков с тарифом, построена диаграмма отношений между всеми парами признаков.
Была поставлена задача классификации. рассмотрены решения с помощью разных моделей, всем моделям предложены разные параметры и выбраны наилучшие.
Были исследованы модели дерева решений, случайного леса, логистической регрессии, K ближайших соседей, наивная байесовская модель и модель градиентного бустинга.
Все модели были исследованы двумя способами: были выбраны наилучшие параметры с помощью функции GridSearchCV и с помощью ручного перебора параметров в циклах.
Все полученные на валидации данные записаны в таблицу.
результаты работы моделей сравнены с помощью метрики accuracy_score.
Лучший результат на валидационной выборке показывают модель случайного леса (где параметры подобраны с помощью перебора в циклах) и модель градиентного бустинга (где параметры подобраны с помощью перебора в циклах).
Все полученные данные на тестовой выборке записаны в таблицу.
Результаты на тесте немного отличаются от результатов на валидации. Лучший результат дает модель градиентного бустинга (где параметры подобраны с помощью перебора в циклах) и модель случайного леса (где параметры подобраны с помощью перебора в циклах).
Качество исследованных моделей сравнено с качеством "простой" модели DummyClassifier().
Использована библиотека sklearn.

***

# ML: Предсказание цены авто
[ml_auto_price_prediction.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/ML-Auto-Price-Prediction/blob/main/ml_auto_price_prediction.ipynb)

Цель данного проекта - создание модели для определения рыночной стоимости автомобиля. Нас будет интересовать качество предсказания и время предсказания.

Проведено исследование данных.
Исследованы модели линейной регрессии, случайного леса,  ближайших соседей, градиентного бустинга LGBMRegressor и градиентого бустинга CatBoostRegressor с параметрами по умолчанию и измененными параметрами.
Наилучшее значение метрики rmse дает модель градиентного бустинга CatBoost. Лучшее время предсказания у случайного леса. 
Важность факторов для всех построенных моделей: первые 3 места занимают время регистрации автомобиля, мощность двигателя и пробег автомобиля.
Использованы библиотеки sklearn, lightgbm, catboost.

***

# Продажа квартир (исследовательский анализ данных EDA)
[Sale_of_Apartments_EDA.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/EDA-Sale-of-Apartments/blob/main/Sale_of_Apartments_EDA.ipynb)

Предоставлен архив объявлений о продаже квартир в Санкт-Петербурге и соседних населённых пунктах. 
Задача: определить, от чего зависит рыночная стоимость квартир.


Изучены следующие параметры: площадь, цена, число комнат, высота потолков. Построены гистограммы для каждого параметра.
Создан портрет самой типичной квартиры - двухкомнатной квартиры в пятиэтажке.
Изучено время продажи квартиры. 
Ответ на вопрос: какие факторы больше всего влияют на стоимость квартиры?
Изучено, зависит ли цена от площади, числа комнат, удалённости от центра. 
Изучена зависимость цены от даты размещения: дня недели, месяца и года. 
Выяснено, в каких районах самая высокая и низкая стоимость жилья.
Выделен сегмент квартир в центре. Проанализирована эта территория и изучен ряд параметров. 

***

# ML Time Series: Такси сервис
[ml_time_series_taxi_service.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/ML-Time-Series-Taxi-Service/blob/main/ml_time_series_taxi_service.ipynb)

В нашем распоряжении данные о заказах такси в аэропортах. Задача: спрогнозировать количество заказов такси.

Данные загружены и ресемплированы.
Построен график числа заказов в зависимости от даты/времени. Произведено сравнение с графиком со скользящим средним.
Временной ряд разложен на тренд, сезонность и остаток. 
Создана и применена функция, которая создает дополнительные признаки в таблице, состоящие из элементов даты/времени по отдельности, скользящего среднего с параметром rolling_mean_size и сдвигов на шаг от 1 до max_lag. 
Построена диаграмма отношений между всеми парами признаков. 
Построена функцию для отображения рейтинга и рассмотрена корреляция целевого признака с прочими признаками.
Построена автокорреляционная функция и частичная автокорреляционная функция, их графики.
Данные полготовлены.
Построены модели линейной регрессии, случайного леса, ближайших соседей, наивная байесовская модель, градиентного бустинга CatBoost, ARIMA. Подобрали гиперпараметры. Искомая метрика - rsme.
Лучшая модель - случайный лес с подобранными гиперпараметрами.
Сделали предсказание.
Нашли rmse на тестовой выборке и построили рейтинг важности признаков.
Для сравнения нашли искомую метрику для константной модели, построенной из медианы тренировочной выборки. 

***

# ML: Обнаружение звуковых событий
[m_audio_tagging.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/ML-Audio-Tagging/blob/main/m_audio_tagging.ipynb)

Задача: научиться "размечать" аудио события. 

[Dataset](https://www.kaggle.com/c/freesound-audio-tagging-2019) 

Данные загружены и исследованы.
Применена One-hot-encoding для тегов.
Анализ аудио производится при помощи PCEN-коэффициентов (per-channel energy normalization - PCEN), которые добавляются в таблицу.
Обучена модель градиентного бустинга CatBoostRegressor (берем регрессионную модель, т.к. для нее возможен рассчет мультитаргета, как в нашем случае). 
В качестве функции потерь использовалась MultiRMSE.
Модель протестирована. Исследованы звуки из других источников.
Использованы библиотеки librosa, catboost.

***

# ML Audio: Классификация музыкальных жанров
[ml_audio_music_genre_classification.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/ML-Audio-Music-Genre-Classification/blob/main/ml_audio_music_genre_classification.ipynb)

Задача: определить музыкальный жанр, анализируя аудио. 

[Dataset](https://www.kaggle.com/andradaolteanu/gtzan-dataset-music-genre-classification) 

Датасет представляет собой аудиофайлы, изображения мел-спектрограмм, 2 таблицы (для 3 сек. и 30 сек.) со ссылками на аудио-файлы и рассчитанными характеристиками звука.  
 
Данные загружены, характеристики звука в таблице исследованы, построены графические отображения ряда характеристик.
Построена модель Keras (MPL).
Использованы данные таблицы с разбивкой по 3 сек., обучена и протестирована модель. Выведено значение accuracy для модели и для каждого жанра.
Затем данные таблицы дополнены значениями 64-х коэффициентов PCEN (per-channel energy normalization), модель повторно обучена и протестирована. 

Использованы библиотеки librosa, Кeras.

***

# DL Audio: Определение гендера по речи

[d_audio_classification_of_Gender_by_speech.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/DL-Audio-Classification-of-Gender-by-Speech/blob/main/d_audio_classification_of_Gender_by_speech.ipynb)

Задача: создать классификатор биологического гендера спикера.
Данные звукового сигнала переводятся в мел-спектрограммы, а затем обрабатываются изображения мел-спектрограмм с помощью модели с архитектурой VGG16 и torch.
Использованы библиотеки librosa, torch.

***

# ML: Понравится ли музыка Spotify?
[ml_spotify_like_prediction.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/ML-Spotify-Like-Prediction/blob/main/ml_spotify_like_prediction.ipynb)

Задача: Дана база прослушанных композиций с сервиса Spotify с оценкой автора датасета (понравилась, не понравилась). 
Необходимо определить, понравится ли автору датасета та или иная музыкальная композиция. 

[Dataset](https://www.kaggle.com/geomack/spotifyclassification)

Данные загружены и исследованы.
Признаки закодированы при помощи One-hot-encoder.
Применены следующие алгоритмы машинного обучения: логистическая регрессия, градиентный бустинг, ансамбль из предыдущих моделей (метамодель - логистическая регрессия).
Найдены лучшие параметры моделей. 
В качестве основной метрики используется roc_auc, в качестве дополнительной - accuracy.
Выбрана лучшая модель - ансамбль, ее работа проверена на тестовых данных. 
Результаты сравнены с константной моделью. 
Построена для лучшей и константной модели ROC-кривая, отображены разные значения порогов.
Найдено оптимальное значение порога, найдена метрика accuracy для оптимального значения порога и для порога 0.25.
Использована библиотека sklearn.

***

# Игры: выявление закономерностей
[Games-Identifying-Patterns/blob/main/games_identifying_patterns.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/Games-Identifying-Patterns/blob/main/games_identifying_patterns.ipynb)

Задача: выявить закономерности, определяющие успешность компьютерной игры.

Рассмотрено, сколько игр выпускалось в разные годы. 
Выбраны платформы с наибольшими суммарными продажами и выведено по ним распределение количества выпущенных игр по годам.
Ответ на вопрос: какие платформы лидируют по продажам, растут или падают для разных лет. 
Построен график «ящик с усами» по глобальным продажам игр в разбивке по платформам. 
Рассмотрено, как влияют на продажи внутри одной популярной платформы отзывы пользователей и критиков. Построены диаграммы рассеяния и посчитана корреляция между отзывами и продажами. 
Рассмотрено общее распределение игр по жанрам. 
Определены для пользователя каждого региона самые популярные платформы (топ-5). 
Определены для пользователя каждого региона самые популярные жанры (топ-5). 
Ответ на вопрос: влияет ли рейтинг ESRB на продажи в отдельном регионе?
Составлены портреты типичных пользователей из разных регионов.
Проверена гипотеза: средние пользовательские рейтинги платформ Xbox One и PC одинаковые. Она подтверждена.
Проверена гипотеза: cредние пользовательские рейтинги жанров Action и Sports разные. Она не подтверждена.
Использована библиотека pandas.

***

# DL: Детектор одежды

[Fashion_Detection_DeepFashion2_Detectron2.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/Fashion-Detection-DeepFashion2-Detectron2-Flask/blob/master/Fashion_Detection_DeepFashion2_Detectron2.ipynb)

[Fashion-Detection-DeepFashion2-Detectron2-Flask](https://github.com/AnnaShtangey/Fashion-Detection-DeepFashion2-Detectron2-Flask)

Создание детектора одежды.
Был использован датасет DeepFashion2 и фреймворки Detectron2. 
Данные передавались в формате Coco json.
Была получена модель, детектирующая одежду на изображениях.
Модель была передана в Flask и адаптирована для работы на сайте. 

***

# DL: Сегментация МРТ
[Brain_MRI_segmentation_Detectron2.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/Brain-MRI-Segmentation-Detectron2/blob/master/Brain_MRI_segmentation_Detectron2.ipynb)

Сегментация МРТ с помощью фреймворка Detectron2. Определение глиомы.

[Dataset](https://www.kaggle.com/mateuszbuda/lgg-mri-segmentation/)

Датасет представляет собой изображения с масками в формате .tiff, маски отмечают области обнаружения глиомы.
Был создан файл COCO-format .json для загрузки данных в фреймворк.
Создана модель сегментации, обучена на датасете.  


# DL: Классификация камней
[Gemstones_Classification_Torch.ipynb](https://nbviewer.jupyter.org/github/AnnaShtangey/Gemstones-Classification-Torch-Flask/blob/master/Gemstones_Classification_Torch.ipynb)

[Gemstones-Classification-Torch-Flask](https://github.com/AnnaShtangey/Gemstones-Classification-Torch-Flask)

[Dataset](https://www.kaggle.com/lsind18/gemstones-images)

Датасет представляет из себя изображения камней, лежащие в папках с названиями пород. Всего 87 наименований.
Классификация камней выполнена на базе фреймворка Torch, затем создано веб-приложение с помощью Flask.
Были использованы претренированные модели inception_v3 и resnet50.
Модели были исследованы отдельно, а также построен ансамбль из двух моделей.
Была выведена метрика accuracy, в целом для моделей и для каждого предсказанного класса.

***