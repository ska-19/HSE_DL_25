# HW4: DEER для Named Entity Recognition

## Описание
Реализация и тестирование DEER (Label-Guided In-Context Learning) для NER задачи.

- `hw4_deer.ipynb` - полный pipeline
- `deer_comparison.png` - графики обучения
- `deer_metrics.png` - bar chart сравнения


## Результаты
- Задача: Named Entity Recognition (NER)
- Модель: DistilBERT-cased
- Датасет: WikiANN English (800 train / 200 test)
- Entity типы: PER, ORG, LOC
- Методы:
  - Baseline: Обычный BERT-NER
  - DEER: BERT + label-guided in-context examples (k=3)
- Метрики: F1-micro, F1-macro, F1-entity


1. Baseline (без DEER):
   F1-micro: 0.8242
   F1-macro: 0.7541
   F1-entity: 0.7217

2. DEER (с label-guided examples):
   F1-micro: 0.9543
   F1-macro: 0.7550
   F1-entity: 0.7162

3. Улучшения от DEER:
   F1-micro: +0.1300 (+15.78%)
   F1-macro: +0.0008 (+0.11%)
   F1-entity: -0.0055 (-0.76%)

4. Наблюдения:
   - DEER показал сопоставимые результаты с baseline
   - На небольших данных эффект может быть менее заметен
   - Требуется больше данных для полной оценки

5. Выводы:
   - Тестировать на больших датасетах
   - Настраивать стратегию выбора примеров
   - Рассмотреть более крупные LLM для in-context learning