## Проект ["Оптимизация процесса выплавки стали"](https://github.com/maresin/yandex_practicum/blob/main/Melt%20of%20Steel/steel_notebook.ipynb)
Данная работа является дипломным проектом курса _"Специалист по Data Science"_ образовательной платформы _Яндекс.Практикум_.   
### Задача:
Построить модель, которая предскажет температуру выплавки стали. Это необходимо для оптимизации производственных расходов металлургического комбината. Качество предсказания по целевой метрике _MAE_ должно быть ниже 6.8.
### Данные:
Данные описывают различные характеристики оборудования и физических параметров используемого сырья, и состоят из файлов, полученных из разных источников. Это:  
- _данные об электродах_
- _данные о подаче сыпучих материалов (объём)_
- _данные о подаче сыпучих материалов (время)_
- _данные о продувке сплава газом_
- _результаты измерения температуры_
- _данные о проволочных материалах (объём)_
- _данные о проволочных материалах (время)_

Источник: [Яндекс.Практикум](https://practicum.yandex.ru/data-scientist/)
### Используемые библиотеки:  
*Pandas, Scikit-learn, Optuna, LightGBM, Plotly*
### Сделано:
![preprocessing](https://img.shields.io/badge/-preprocessing-D0F4F6?style=flat) ![EDA](https://img.shields.io/badge/-EDA-F8FBAC?style=flat) ![feature engineering](https://img.shields.io/badge/-feature--engineering-C5D8F1?style=flat) ![ML](https://img.shields.io/badge/-ML-F19CBB?style=flat) ![pipeline](https://img.shields.io/badge/-pipeline-FEEFE1?style=flat) ![visualization](https://img.shields.io/badge/-visualization-FDC4C4?style=flat)   
Первичный анализ признаков в датесетов был проведен с помощью профайлера _YData Profiling_, на основе сгенерированных им отчетов.  
Для уточнения характера технологического процесса, на примере одной из партий была сделана диаграмма Ганта.  
Основной частью предобработки данных стало формирование единого датасета и создание ряда новых признаков. Это потребовало написания достаточно сложного алгоритма отбора значений исходных признаков.  
Исследование корреляции сформированных признаков показало их сильную линейную зависимость друг с другом, и для повышения устойчивости прогнозов решено было подвергнуть их ортогонализации с помощью метода _PCA_. Асимметрию данных было решено исправить с помощью _QuantileTransformer_. В результате на нормально распределённых и линейно-независимых признаках была обучена модель _LGBMRegressor_, преодолевшая необходимый порог точности по целевой метрике _MAE_< 6.8.  
Основную трудность в проекте представлял выбор объектов исследования и разработка подхода по сбору признаков для них. При обработке партий невозможно было выделить четко обозначенные технологические этапы, так что признаки пришлось формировать временными границами. В результате чего сводную таблицу признаков пришлось создавать построчно.  
В дополнении к проекту был также рассмотрен вариант с моделью линейной регрессии без трансформации признаков. Она показала близкое к выбранной модели качество прогноза. Её обученные веса были использованы при демонстрации возможного способа оптимизации энергозатрат предприятия.  

⚠ _Внимание:_ Так как на платформе GitHub существуют ограничения на размер отображаемого файла и запрет использования JavaScript, то просмотр полной версии проекта с Plotly-визуализацией и выводом профайлера возможен лишь локально через скачивание  архива с файлом `steel_page.html`.
