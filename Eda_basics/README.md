# Анализ и визуализация данных на Python (NumPy, Pandas, Matplotlib, Seaborn)

Репозиторий содержит практические решения задач по базовому анализу данных и построению графиков с использованием популярных библиотек экосистемы Python.

---

## ✨ Функционал проекта

### 1. Статистический анализ данных (NumPy)
* Расчет ключевых метрик оценок студентов по предметам (Math, Physics, Informatics).
* Вычисление среднего балла (`np.mean`), медианы (`np.median`) и стандартного отклонения (`np.std`).
* Автоматическое определение дисциплины с наилучшей успеваемостью с помощью функции `np.argmax`.

### 2. Анализ динамики продаж (Pandas & Matplotlib)
* Агрегация и расчет годовых показателей продаж.
* Определение лучшего и худшего месяца по объему выручки с использованием методов `.idxmax()` и `.idxmin()`.
* Построение линейного графика тренда изменения продаж по месяцам.

### 3. Исследовательский анализ и визуализация (Seaborn)
* Загрузка и исследование встроенного датасета `tips` (данные о чаевых в ресторане).
* Построение четырех видов информативных графиков:
  * **Линейный график** (`sns.lineplot`) для оценки зависимости времени прихода посетителей от дня недели.
  * **Столбчатый график** (`sns.barplot`) для сравнения среднего чека в курящем и некурящем залах.
  * **Гистограмма** (`sns.histplot`) со стеком и оценкой плотности распределения (KDE) чаевых.
  * **Диаграмма рассеяния** (`sns.scatterplot`) для демонстрации зависимости размера чаевых от общего счета.

---

## 🛠 Требования

Для запуска кода вам потребуется Python 3.x и следующие библиотеки:
*   `numpy`
*   `pandas`
*   `matplotlib`
*   `seaborn`

Вы можете установить все зависимости одной командой:
```bash
pip install numpy pandas matplotlib seaborn
```

---

## 🚀 Примеры использования и результаты кода

### Анализ успеваемости студентов (NumPy)
```python
import numpy as np

# Вычисление средних оценок, медианы и стандартного отклонения
average = np.mean(grades_array, axis=1)
median = np.median(grades_array, axis=1)
std_deviation = np.std(grades_array, axis=1)

# Определение предмета с самым высоким средним баллом
most_grade_subject = subjects_array[np.argmax(average)]
print(f'Предмет с самой высокой средней оценкой: {most_grade_subject}')
# Вывод: informatics
```

### Анализ продаж (Pandas)
```python
import pandas as pd

df_sales_data = pd.DataFrame(sales_data)

# Поиск месяцев-экстремумов
max_sales_month = df_sales_data.loc[df_sales_data['Sales'].idxmax(), 'Month'] # December
min_sales_month = df_sales_data.loc[df_sales_data['Sales'].idxmin(), 'Month'] # May
```

### Визуализация зависимостей (Seaborn)
```python
import seaborn as sns
import matplotlib.pyplot as plt

df = sns.load_dataset('tips')

# Построение диаграммы рассеяния
plt.figure(figsize=(8, 6))
sns.scatterplot(data=df, x='total_bill', y='tip')
plt.title('Зависимость чаевых от общего счета')
plt.show()
```
