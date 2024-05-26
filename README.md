# <img src='./static/img/mipt-icon.png' width="70" height="30">
# Задача от Beeline

**Заказчик:** Компания Beeline является одним из ведущих поставщиков телекоммуникационных услуг в России.

**Описание задачи:** Модель для бинарной классификации аудиофрагментов с целью определения качества их транскрибации. Модель должна определять, является ли транскрибация качественной, при условии, что псевдоразметка отличается от ручной разметки не более, чем на N пунктов коофициента ошибок в словах. Итоговая оценка качества модели будет проводиться с помощью метрики accuracy.

## Промежуточный результат
На текущий момент наилучший результат показал пайплайн векторизация при помощи sbert_large_mt_nlu_ru и LogisticRegression c L2 регуляризацией.

Модель находится в файле [Classic models](https://github.com/kosatchev/ClarityAnalyzer/blob/main/research/Classic%20models.ipynb).

Наибольшее влияние на результат оказывает метод векторизации, и значительно меньшее ― тип модели.

Проведенные исследования приведены в директории `research`.

## 👥 Состав команды

- **Вяткин Роман Вячеславович**

  Капитан команды/ML engineer, тестирование пайплайнов:
  - токенизация и эмбеддинг с помощью navec_hudlit_v1_12B_500K_300d_100q(проект Natasha) с моделями:
    - LogisticRegression
    - Полносвязная двухслойная нейронная сеть

- **Яськова Марина Андреевна**

  ML engineer, тестирование пайплайнов:
  - токенизация и эмбеддинг с помощью модели ai-forever/sbert_large_mt_nlu_ru с моделями:
    - PassiveAggressiveClassifier
    - VotingClassifier
    - MultinomialNB
  - исследование влияния предварительной рукописной нормализации текстовых данных на результаты классификации

- **Баймлер Ярослав Игоревич**

  ML engineer, тестирование пайплайнов:
  - токенизация и эмбеддинг с помощью модели ai-forever/sbert_large_mt_nlu_ru с моделями:
    - LinearSVC
    - DecisionTreeClassifier
    - RandomForestClassifier
    - GradientBoostingClassifier

- **Ихматуллаев Даврон Махаматкаримович**

  ML engineer, тестирование пайплайнов:
  - токенизация и эмбеддинг с помощью модели intfloat/multilingual-e5-large и классификация моделью LogisticRegression
  - токенизация и эмбеддинг с помощью модели ai-forever/sbert_large_mt_nlu_ru и классификация моделью CatBoost
  - аугментация данных при помощи модели Whisper, тестирование качества выборочных моделей после аугментации 


- **Назаров Михаил Сергеевич**

  ML engineer, тестирование пайплайнов:
  - токенизация и эмбеддинг с помощью модели ai-forever/sbert_large_mt_nlu_ru с моделями:
    - LogisticRegression
    - SGDClassifier
    - SVC
    - NuSVC
    - MLPClassifier
    - ExtraTreesClassifier
    - HistGradientBoostingClassifier
    - LightGBM
    - XGBoost
    - KNeighborsClassifier
    - RadiusNeighborsClassifier
    - GaussianNB
    - BernoulliNB
    - LinearDiscriminantAnalysis
    - QuadraticDiscriminantAnalysis

- **Новиков Валентин Владимирович**

  ML engineer, тестирование пайплайнов:
  - векторизация мешком слов с моделями семейства Naive Bayes, SVM, XGBoost, LogisticRegression;
  - TF-IDF с униграммами и биграммами с моделями семейства Naive Bayes, SVM, XGBoost, LogisticRegression.

- **Косачев Дмитрий**

  ML engineer, тестирование пайплайнов:
  - токенизация и эмбеддинг с помощью модели ai-forever/sbert_large_mt_nlu_ru с моделью AdaBoostClassifier, StackingClassifier, BaggingClassifier

## Сравнительная таблица

| Classifier                         | Val Score | Train Score | Overfitting |
|------------------------------------|-----------|-------------|-------------|
| LogisticRegression L1              | 0.78      | 0.832       | 0.052       |
| LogisticRegression L2              | 0.775     | 0.808       | 0.033       |
| LogisticRegression ElasticNet      | 0.779     | 0.841       | 0.062       |
| PassiveAggressiveClassifier        | 0.705     | 0.822       | 0.117       |
| SGDClassifier                      | 0.781     | 0.83        | 0.049       |
| SVC                                | 0.7       | 0.999       | 0.299       |
| NuSVC rbf                          | 0.776     | 1           | 0.224       |
| NuSVC poly                         | 0.78      | 0.863       |             |
| LinearSVC                          |           | 0.731       | 0.731       |
| MLPClassifier                      | 0.76      | 0.832       | 0.072       |
| DecisionTreeClassifier             |           |             | 0           |
| ExtraTreesClassifier               | 0.73      | 0.78        | 0.05        |
| AdaBoostClassifier                 | 0.612     | 0.639       | 0.027       |
| HistGradientBoostingClassifier     | 0.762     | 0.963       | 0.201       |
| BaggingClassifier                  | 0.655     | 0.916       | 0.261       |
| VotingClassifier                   | 0.782     | 0.847       | 0.065       |
| StackingClassifier                 | 0.772     | 0.861       | 0.089       |
| beelineNN                          | 0.806     | 0.812       | 0.006       |
| CatBoost                           | 0.772     |             | -0.772      |
| LightGBM                           | 0.752     | 0.834       | 0.082       |
| XGBoost                            | 0.757     | 0.87        | 0.113       |
| KNeighborsClassifier               | 0.688     | 1           | 0.312       |
| RadiusNeighborsClassifier          | 0.705     | 0.727       | 0.022       |
| GaussianNB                         | 0.722     | 0.738       | 0.016       |
| BernoulliNB                        | 0.72      | 0.743       | 0.023       |
| ComplementNB                       | 0.72      | 0.734       | 0.014       |
| MultinomialNB                      | 0.718     | 0.728       | 0.01        |
| LinearDiscriminantAnalysis         | 0.782     | 0.831       | 0.049       |
| QuadraticDiscriminantAnalysis      | 0.739     | 0.837       | 0.098       |
| GaussianProcessClassifier          | 0.775     | 0.862       | 0.087       |
| Naive Bayes (MultinomialNB())      | 0.677     | 0.766       | 0.089       |
| LogisticRegression L2              | 0.681     | 0.823       | 0.142       |
| LogisticRegression L1              | 0.669     | 0.817       | 0.148       |
| SVM                                | 0.684     | 0.962       | 0.278       |
| XGBoost                            | 0.669     | 0.803       | 0.134       |
| Naive Bayes (MultinomialNB())      | 0.684     | 0.881       | 0.197       |
| LogisticRegression L2              | 0.685     | 0.969       | 0.284       |
| LogisticRegression L1              | 0.665     | 0.708       | 0.043       |
| SVM                                | 0.687     | 0.998       | 0.311       |
| XGBoost                            | 0.66      | 0.856       | 0.196       |

<img src='./static/img/classifier_scores.png'>
