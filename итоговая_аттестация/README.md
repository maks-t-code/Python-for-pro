# 🧠 Итоговая аттестация — Классификация типа личности

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Kaggle](https://img.shields.io/badge/Kaggle-Playground-blueviolet.svg)](https://www.kaggle.com/competitions/playground-series-s5e7)

---

## 📌 О проекте

Данный проект выполнен в рамках итоговой аттестации по курсу машинного обучения. 
В основе лежит соревнование **"Playground Series - Season 5, Episode 7"** на платформе Kaggle.

**Цель** — построить модель бинарной классификации, которая на основе социально-поведенческих характеристик определяет тип личности человека:
- **Extrovert** (экстраверт)
- **Introvert** (интроверт)

---

## 📊 Описание данных

Датасет содержит **8 признаков**, включая целевую переменную:

| Признак | Описание | Диапазон |
|---------|----------|----------|
| `Time_spent_Alone` | Часы, проведённые в одиночестве в день | 0–11 |
| `Stage_fear` | Наличие страха сцены | Yes / No |
| `Social_event_attendance` | Частота посещения социальных мероприятий | 0–10 |
| `Going_outside` | Частота выходов на улицу | 0–7 |
| `Drained_after_socializing` | Чувство истощения после общения | Yes / No |
| `Friends_circle_size` | Количество близких друзей | 0–15 |
| `Post_frequency` | Частота публикаций в социальных сетях | 0–10 |
| `Personality` | **Целевая переменная** | Extrovert / Introvert |

---

## 🧠 Использованные модели

В ходе работы были обучены и протестированы **6 моделей** машинного обучения:

1. **Logistic Regression** — линейная модель-бейзлайн
2. **Decision Tree** — простое дерево решений
3. **Random Forest** — ансамбль деревьев
4. **XGBoost** — градиентный бустинг
5. **CatBoost** — бустинг с поддержкой категориальных признаков
6. **LightGBM** — быстрый градиентный бустинг

Для каждой модели проводилась **оптимизация гиперпараметров** с использованием **Optuna**.

---

## 📈 Результаты

**Лучшая модель — LightGBM**

| Метрика | Значение |
|---------|----------|
| **Accuracy** | 0.9687 |
| **Precision** | 0.9465 |
| **Recall** | 0.9437 |
| **F1-score** | 0.9451 |
| **ROC-AUC** | 0.9737 |

### Сравнение моделей

| Модель | Accuracy | ROC-AUC |
|--------|----------|---------|
| Logistic Regression | 0.9716 | 0.9607 |
| Decision Tree | 0.9709 | 0.9606 |
| Random Forest | 0.9712 | 0.9712 |
| XGBoost | 0.9709 | 0.9730 |
| CatBoost | 0.9710 | 0.9731 |
| **LightGBM** | **0.9687** | **0.9737** |

---

## 🔧 Технологический стек

```python
# Основные библиотеки
pandas, numpy          # Работа с данными
matplotlib, seaborn    # Визуализация
scikit-learn           # Модели и метрики

# Градиентный бустинг
xgboost, catboost, lightgbm

# Оптимизация
optuna

# Интерпретация
shap
```

---

## 📁 Структура репозитория

```
.
├── final_notebook.ipynb          # Основной Jupyter Notebook
├── README.md                     # Описание проекта
├── requirements.txt              # Зависимости
├── LICENSE                       # Лицензия MIT
└── .gitignore
```

---

## 🚀 Быстрый старт

### 1. Клонирование репозитория
```bash
git clone https://github.com/username/personality-classification.git
cd personality-classification
```

### 2. Установка зависимостей
```bash
pip install -r requirements.txt
```

### 3. Запуск ноутбука
```bash
jupyter notebook final_notebook.ipynb
```

---

## 📋 Этапы работы

1. **EDA (Разведочный анализ)**
   - Анализ распределения признаков
   - Поиск выбросов и пропусков
   - Корреляционный анализ

2. **Предобработка данных**
   - Обработка пропусков (SimpleImputer)
   - Кодирование категориальных признаков (TargetEncoder)
   - Стандартизация числовых признаков (StandardScaler)
   - Создание новых признаков

3. **Обучение моделей**
   - Подбор гиперпараметров через Optuna
   - Кросс-валидация (5-fold)

4. **Оценка и выбор модели**
   - Сравнение по метрикам
   - Визуализация ROC-кривых

---

## 📌 Выводы

- Все модели показали высокое качество (>96% accuracy)
- Модели на основе градиентного бустинга (XGBoost, CatBoost, LightGBM) продемонстрировали лучший ROC-AUC
- **LightGBM** показала лучший баланс между точностью и скоростью обучения
- Созданные признаки `social_activity` и `social_mobility` улучшили качество моделей

