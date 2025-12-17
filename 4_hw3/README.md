# HW3: VSSD для Computer Vision

## Описание
Реализация и тестирование VSSD (Vision Mamba with Non-Causal State Space Duality) для классификации изображений.

- `hw3_vssd.ipynb` - полный pipeline
- `vssd_comparison.png` - графики обучения
- `vssd_metrics.png` - bar chart сравнения


## Результаты

1. Конфигурация:
   - Dataset: MNIST (5000 train / 1000 test)
   - VSSD: patch_size=4, d_model=128, d_state=16, bidirectional
   - Baseline: 3-layer CNN
   - Epochs: 10, batch_size: 64

2. Финальные результаты:
   CNN Baseline:  Accuracy=0.9790, F1=0.9783
   VSSD:          Accuracy=0.4410, F1=0.4222

3. Сравнение методов:
   ✗ VSSD показал ухудшение: -0.5380 (-54.95%) по Accuracy

4. Анализ:
   - CNN: стабильная baseline с conv-pooling архитектурой
   - VSSD: non-causal bidirectional State Space Model
   - Bidirectional scan: каждый patch видит контекст с обеих сторон
   - SSM layers: моделируют long-range зависимости через hidden state

5. Итог:
   VSSD уступает CNN baseline на 54.95%,
   что может быть связано с малым размером датасета или
   необходимостью тонкой настройки гиперпараметров SSM.

