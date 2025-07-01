# Определение возраста покупателей по фотографиям

![Computer Vision](https://img.shields.io/badge/ML-Computer%20Vision-blue)
![Python](https://img.shields.io/badge/Python-3.8%2B-success)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

Проект разработан для сети супермаркетов "Хлеб-Соль" для автоматического определения возраста покупателей по фотографиям в прикассовой зоне.

## 🔍 Бизнес-задачи
- Персонализация предложений товаров по возрастным группам
- Контроль продажи алкоголя несовершеннолетним

## 🛠 Stack
`pandas` `numpy` `matplotlib`  
`ResNet50` `Sequential` `GlobalAveragePooling2D` `Dense` `Adam`

![Py3.8](https://img.shields.io/badge/Python-3.8-blue)
![TF2.6](https://img.shields.io/badge/TensorFlow-2.6-orange)


## 📊 EDA

- **Объем данных**: 7,591 фотографий
- **Качество данных**: высокое (отсутствуют пропуски и дубликаты)
- Разнообразные ракурсы съемки
- Вариативное освещение
- Присутствие артефактов на части изображений
- Различные условия съемки

## 🧠 Модель

```python
ResNet50(weights='imagenet', include_top=False) → GlobalAveragePooling2D() → Dense(1)
```

- Backbone: Предобученная ResNet50
- Pooling: Global Average Pooling
- Выход: Полносвязный слой с 1 нейроном

## 📊 Результаты обучения

| Эпоха | Train Loss | Train MAE | Val Loss | Val MAE |
|-------|-----------|----------|----------|---------|
| 1     | 253.71    | 11.38    | 1017.49  | 27.22   |
| 10    | **10.41** | **2.47** | **64.62**| **6.02**|

## 🚀 Рекомендации

### Доработка модели
- 📈 Увеличить датасет для возрастов 70+
- 🖼️ Добавить аугментации:
```python
ImageDataGenerator(rotation_range=30, brightness_range=[0.7,1.3])


