# Реализация оценки дефолта заемщика

1. Поднимаем контейнер с помощью docker и команды **docker-compose up**
2. Запускаем сначала DataPreparing
3. И обучаем модель в GBT, при первом запуске расскоментить два блока, где проходит агрегация

Для исследования был использован данный [датасет](https://ods.ai/competitions/dl-fintech-bki/data).

## Модели

[Gradient Boost Tree](notebooks/GBT.ipynb) - [Документация Spark](https://spark.apache.org/docs/latest/api/python/reference/api/pyspark.ml.classification.GBTClassifier.html)
[Random Forest](notebooks/RF.ipynb) - [Документация Spark](https://spark.apache.org/docs/latest/api/python/reference/api/pyspark.ml.classification.RandomForestClassifier.html)
[LogisticRegression](notebooks/LR.ipynb) - [Документация Spark](https://spark.apache.org/docs/latest/ml-classification-regression.html)

### Сравнение моделей по метрикам:

Модель | AUC | Лучший threshold | TPR (Recall) | FPR
-|-|-|-|-
GBT | 0.7119 |0.5194 | 0.6513 | 0.3417
RF | 0.6981 | 0.5035 | 0.6572 | 0.3693
LR | 0.7026 | 0.5067 | 0.6699 | 0.3677