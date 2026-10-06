# 🛡️ Cyberbullying Detection Using Machine Learning & DistilBERT

Автоматизированная система обнаружения кибербуллинга и токсичного контента в социальном пространстве (Twitter/X) с использованием методов машинного обучения и трансформеров (NLP).

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ВАШ_НИК/ИМЯ_РЕПОЗИТОРИЯ/blob/main/cyberbullying_detection.ipynb)

---

## 📌 Описание проекта
Проект предназначен для классификации сообщений из социальных сетей и выявления различных типов кибербуллинга. В ходе работы были построены и сравнены две модели: бейзлайн на основе TF-IDF + Logistic Regression и современная нейросетевая модель DistilBERT Transformer.

### 📂 Датасет
- **Размер:** 47,000 твитов.
- **Баланс классов:** Сбалансированный датасет (~8,000 примеров на каждый класс).
- **Классы (6 категорий):**
  1. `age` (буллинг по возрасту)
  2. `ethnicity` (расизм / этнический буллинг)
  3. `gender` (сексизм / буллинг по полу)
  4. `religion` (религиозная ненависть)
  5. `other_cyberbullying` (другие виды буллинга)
  6. `not_cyberbullying` (нейтральные сообщения)

---

## 🔄 Пайплайн обработки (Pipeline)
`Data Collection` ➔ `Text Preprocessing` ➔ `Baseline Model` ➔ `Model Training (DistilBERT)` ➔ `Evaluation & Testing`

### Предобработка текста (NLP Preprocessing):
- Удаление повторов букв (например, `moveeeee` → `move`).
- Приведение текста к нижнему регистру.
- Удаление URL-ссылок и упоминаний пользователей (`@username`).
- Очистка от хэштегов `#` (с сохранением самого слова) и удаление спецсимволов/эмодзи.

---

## 📊 Результаты и сравнение моделей

| Модель | Overall Accuracy | Особенности |
| :--- | :---: | :--- |
| **TF-IDF + Logistic Regression** (Baseline) | **82.02%** | Быстрое обучение, высокая интерпретируемость. |
| **DistilBERT Transformer** | **86.43%** | Лучшее качество и точный учет контекста. |

### Метрики по классам (DistilBERT):
- **Age:** Precision: 0.99 | Recall: 0.98 | F1: 0.98
- **Ethnicity:** Precision: 0.99 | Recall: 0.97 | F1: 0.98
- **Religion:** Precision: 0.96 | Recall: 0.96 | F1: 0.96
- **Gender:** Precision: 0.90 | Recall: 0.89 | F1: 0.89
- **Other Cyberbullying:** Precision: 0.65 | Recall: 0.81 | F1: 0.72
- **Not Cyberbullying:** Precision: 0.72 | Recall: 0.56 | F1: 0.63

---

## 🛠 Технологический стек
- **Язык:** Python 3.x
- **NLP & ML:** PyTorch, HuggingFace Transformers (`DistilBERT`), Scikit-learn (TF-IDF, Logistic Regression)
- **Анализ и визуализация:** Pandas, NumPy, Matplotlib, Seaborn (Confusion Matrix)

---

## ⚠️ Ограничения и этика (Ethical Considerations)
- **Сарказм и косвенная агрессия:** Модели пока трудно распознавать пассивную агрессию или сарказм без явных ключевых слов.
- **Ложные срабатывания:** Риск избыточной цензуры (False Positives) или пропуска скрытого буллинга (False Negatives).
- **Назначение:** Система предназначена для помощи модераторам-людям, а не для полной автоматической блокировки.

---

## 🔮 Планы по развитию (Future Work)
- Улучшение очистки текста и обработка эмодзи.
- Поддержка других языков (включая русский и казахский).
- Тестирование алгоритмов детоксикации текста (Text Detoxification).

---

## 👨‍💻 Авторы проекта
- **Aisaule Zaneshova**
- **Yedil Koldasbek**
