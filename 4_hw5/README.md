# HW5: TAM для Test-Time Adaptation

## Описание
Проверка метода TAM (Test-Time Adaptation with Margin) на MNIST с Gaussian noise.

- `hw5_tam.ipynb` - полный pipeline
- `tam_results.png` - сравнение методов


## Результаты
Проверка эффективности TAM на corrupted MNIST.

1. Baseline (clean): 0.9720
2. Baseline (corrupted): 0.6410
3. TAM (corrupted): 0.8230

4. Улучшение: +0.1820 (+28.39%)

5. TAM ХОРОШО работает:
   - Значительное улучшение на corrupted
   - Margin loss эффективен

6. Особенности TAM:
   - Адаптирует только BatchNorm
   - Entropy + margin loss
   - Per-sample (медленно)
   - Для domain shift > noise

7. Итог для задачи:
   TAM показал улучшение на 28.4%
