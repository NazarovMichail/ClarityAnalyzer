# <img src='./static/img/mipt-icon.png' width="70" height="30"> 
# Задача от Beeline

**Заказчик:** Компания Beeline является одним из ведущих поставщиков телекоммуникационных услуг в России.

**Описание задачи:** Модель для бинарной классификации аудиофрагментов с целью определения качества их транскрибации. Модель должна определять, является ли транскрибация качественной, при условии, что псевдоразметка отличается от ручной разметки не более, чем на N пунктов коофициента ошибок в словах. Итоговая оценка качества модели будет проводиться с помощью метрики accuracy.

## 👥 Состав команды

- Вяткин Роман Вячеславович 
  Капитан команды/ML engineer, тестирование пайплайнов:
  - токенизация и эмбеддинг с помощью navec_hudlit_v1_12B_500K_300d_100q(проект Natasha) с моделями:
    - LogisticRegression
    - Полносвязная двухслойная нейронная сеть

- Яськова Марина Андреевна
  ML engineer, тестирование пайплайнов: 
  - токенизация и эмбеддинг с помощью модели ai-forever/sbert_large_mt_nlu_ru с моделями:
    - PassiveAggressiveClassifier 
    - VotingClassifier
    - MultinomialNB
  - исследование влияния предварительной рукописной нормализации текстовых данных на результаты классификации

- Баймлер Ярослав Игоревич
  ML engineer, тестирование пайплайнов: 
  - токенизация и эмбеддинг с помощью модели ai-forever/sbert_large_mt_nlu_ru с моделями:
    - LinearSVC
    - DecisionTreeClassifier
    - RandomForestClassifier
    - GradientBoostingClassifier
 
- Ихматуллаев Даврон Махаматкаримович
  ML engineer, тестирование пайплайнов: 
  - токенизация и эмбеддинг с помощью модели intfloat/multilingual-e5-large и классификация моделью LogisticRegression
  - токенизация и эмбеддинг с помощью модели ai-forever/sbert_large_mt_nlu_ru и классификация моделью CatBoost

- Назаров Михаил Сергеевич
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

- Новиков Валентин Владимирович
  ML engineer, тестирование пайплайнов: 
  - векторизация мешком слов с моделями семейства Naive Bayes, SVM, XGBoost, LogisticRegression;
  - TF-IDF с униграммами и биграммами с моделями семейства Naive Bayes, SVM, XGBoost, LogisticRegression.

- Косачев Дмитрий
  ML engineer, тестирование пайплайнов: 
  - токенизация и эмбеддинг с помощью модели ai-forever/sbert_large_mt_nlu_ru с моделью AdaBoostClassifier, StackingClassifier, BaggingClassifier

