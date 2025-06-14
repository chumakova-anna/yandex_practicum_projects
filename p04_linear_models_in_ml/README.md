# Прогнозирование продуктивности коров с помощью линейных моделей

## Описание проекта
Молочная ферма хочет расширить поголовье, отбирая коров по двум ключевым критериям:
1. Годовой удой ≥ 6000 кг
2. Производство вкусного молока

## Цели проекта
Разработать две модели машинного обучения:
1. **Прогнозирование годового удоя** (линейная регрессия)
2. **Классификация вкуса молока** (логистическая регрессия)

## Результаты

### Предобработка данных
- Исправлены некорректные типы данных
- Удалены дубликаты (5 строк в основном датасете)
- Выявлены особенности распределения:
  - Бимодальность данных
  - Асимметрия признаков СПО и жирности

### Анализ данных
- Сильные корреляции:
  - Удой ↔ ЭКЕ (0.72)
  - Удой ↔ СПО (0.66)
  - Удой ↔ возраст (0.998)
- Мультиколлинеарность не обнаружена

### Эффективность моделей

| Модель | Метрика | Значение |
|--------|---------|----------|
| Линейная регрессия | R² | 0.825 |
| | RMSE | 188.875 |
| Логистическая регрессия | Precision | 1.0 |

### Выводы по отбору коров
⚠ Среди 20 рассматриваемых коров:
- **Ни одна** не соответствует обоим требованиям

## Рекомендации
1. Пересмотреть критерии отбора
2. Рассмотреть других кандидатов
3. Учесть нелинейные зависимости (ЭКЕ², категоризация СПО)

## Стек технологий 
- Python
- Pandas
- Scikit-learn
- Matplotlib/Seaborn
