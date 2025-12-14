# HW2: Использование NeuralNDCG

## Описание
Сравнение влияния NeuralNDCG как дополнительной функции потерь на качество классификации.

- `hw2_neuralndcg.ipynb` - полный pipeline эксперимента
- `comparison.png` - графики обучения и метрик
- `metrics_comparison.png` - bar chart сравнения

## Результаты
Сравнение показывает влияние NeuralNDCG на оптимизацию ранжирования классов и улучшение NDCG метрики.

- Модель: DistilBERT + Linear Classifier
- Датасет: AG News (4 класса новостей, 2000 train / 800 test)
- Loss функции:
  - Baseline: CrossEntropy Loss
  - Experimental: 0.7 * CE + 0.3 * NeuralNDCG
- Метрики: Accuracy, F1-score, NDCG@k

1. Базовая модель (CE Loss):
   Test Accuracy: 0.8900
   Test F1: 0.8851
   Test NDCG: 0.9569

2. Модель с NeuralNDCG (CE + NeuralNDCG):
   Test Accuracy: 0.8975
   Test F1: 0.8931
   Test NDCG: 0.9592

3. Улучшения от добавления NeuralNDCG:
   Accuracy: +0.0075 (+0.84%)
   F1 Score: +0.0080 (+0.91%)
   NDCG: +0.0024 (+0.25%)

4. Наблюдения:
   - NeuralNDCG улучшает ранжирование предсказаний
   - Модель лучше расставляет приоритеты между классами
   - Подтверждается гипотеза о пользе оптимизации top-k

5. Выводы:
   - Для простых задач классификации достаточно CE Loss
   - NeuralNDCG более полезен в задачах с большим числом классов