# HW1: Поиск информативного скрытого слоя в LLMs

## Описание
Исследование распределения информации в слоях DistilBERT для задачи sentiment classification.

- `hw1_layers.ipynb` - основной ноутбук с экспериментами
- `layer_analysis.png` - графики метрик по слоям
- `heatmap_metrics.png` - тепловая карта результатов

## Результаты
- Модель: DistilBERT (6 transformer layers)
- Датасет: IMDB sentiment (1000 train / 500 test)
- Классификатор: LogisticRegression на CLS-токенах
- Метрики: Accuracy, F1-score по каждому слою

1. Лучший слой: 6
   Test Accuracy: 0.832
   Test F1: 0.820

2. Худший слой: 0
   Test Accuracy: 0.500

3. Средняя accuracy по группам слоев:
   Начальные слои (0-2): 0.661
   Средние слои (3-5): 0.749
   Финальные слои (6): 0.832

4. Наблюдения:
   - Финальные слои лучше, модель использует всю глубину

5. Выводы:
   Для sentiment analysis на DistilBERT использовать слой 6
