## Проект "Определение стоимости автомобилей"
Данная работа является учебным проектом и выполняется по завершении спринта _"Численные методы"_ на курсе _"Специалист по Data Science"_ образовательной платформы _Яндекс.Практикум_.  
### Задача:
Построить модель, определяющую рыночную стоимость своего автомобиля для сервиса по продаже автомобилей с пробегом. При её создании учесть не только качество прогноза, но и скорость предсказания, а также время на её обучения.
### Данные:
В наличии имеются данные с техническими характеристиками, комплектацией и ценами автомобилей, а также данные по самим объявлениям об их продаже:  
- _Дата скачивания анкеты из базы_
- _Тип автомобильного кузова_
- _Год регистрации автомобиля_
- _Тип коробки передач_
- _Мощность (л.с.)_
- _Модель автомобиля_
- _Пробег (км)_
- _Месяц регистрации автомобиля_
- _Тип топлива_
- _Марка автомобиля_
- _Была машина в ремонте или нет_
- _Дата создания анкеты_
- _Количество фотографий автомобиля_
- _Почтовый индекс владельца анкеты (пользователя)_
- _Дата последней активности пользователя_
- _Цена (евро)_

Источник: [Яндекс.Практикум](https://practicum.yandex.ru/data-scientist/)
### Используемые библиотеки:
*Pandas, NumPy, Phik, Scikit-learn, Category Encoders, Optuna, LightGBM*
### Сделано:
При работе над проектом начальные данные подверглись значительной коррекции. В категориальных признаках обнаружены и заполнены многочисленные пропуски. Часть неинформативных признаков была удалена. Были созданы новые признаки, учитывающие некоторые временные параметры.  
Чтобы избежать увеличения признакового пространства после _one-hot-кодирования_ категориальных признаков с большим количеством уникальных значений, были предложены рациональные альтернативы этому. Был использован кодировщик типа _Target-based Coding_ из библиотеки _Category Encoders_.  
Были проверены несколько алгоритмов машинного обучния. Для подбора гиперпараметров использовалась библиотека оптимизации _Optuna_. Для оценки качества моделей написана функция записи необходимых характеристик.  
В качестве базовой модели проекта был выбран бустинговый _LGBMRegressor_, показавший и хорошее качество прогноза и достойную скорость обучения. 