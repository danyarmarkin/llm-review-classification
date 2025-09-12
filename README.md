# Классификация отзывов с маркетплейсов

[Задание](task/README.md)

[Решение в Jypiter Notebook](./solution.ipynb)
<a target="_blank" href="https://colab.research.google.com/github/danyarmarkin/llm-review-classification/solution.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

## Этапы решения

1. **Автоматическая разметка данных**: Использована модель [Qwen2-7B-Instruct](https://huggingface.co/Qwen/Qwen2-7B-Instruct) с 4-битным квантованием для разметки 1818 отзывов из тренировочных данных.
2. **Обучение классификатора**: На размеченных данных дообучена модель [cointegrated/LaBSE-en-ru](https://huggingface.co/cointegrated/LaBSE-en-ru) с использованием `LoRA` для эффективного обучения.
3. **Оценка качества**: На валидационной выборке достигнут `Weighted F1-score = 0.869`
4. **Предсказание на тестовых данных**: Модель успешно обработала все тестовые примеры со средним временем 0.012 секунд на пример.

## Используемые модели:
- Для разметки: [Qwen2-7B-Instruct](https://huggingface.co/Qwen/Qwen2-7B-Instruct) (4-bit)
- Для классификации: [cointegrated/LaBSE-en-ru](https://huggingface.co/cointegrated/LaBSE-en-ru) + LoRA

## Результаты
- Файл с предсказаниями: [submission.csv](submission.csv)
- Обученная модель: `best_model/`
- Маппинг категорий: `label_mapping.json`

## Распределение времени предсказания на тестовых данных
