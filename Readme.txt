Проект: Разработка решения по персонализации предложений постоянным клиентам интернет-магазина.
Цель проекта: удержать активность постоянных клиентов магазина при помощи персонализированных предложений.
Задача: разработать решение, которое позволит персонализировать предложения постоянным клиентам, чтобы увеличить их покупательскую активность.
Используемые модели:
- KNeighborsClassifier()
- DecisionTreeClassifier()
- SVC()
- LogisticRegression()

Метод подбора лучшей модели: RandomizedSearchCV()
Лучшая модель в проекте: 
LogisticRegression(C=2, l1_ratio=0.5, penalty='elasticnet', random_state=42, solver='saga')

Метрика лучшей модели по кросс-валидации: 0.8983
Метрика ROC-AUC на тестовой выборке: 0.9244

Изменения версии 2:
Изменены гиперпараметры моделей:
- 'models': [KNeighborsClassifier()],'models__n_neighbors': range(1, 8)
- 'models': [DecisionTreeClassifier(random_state=RANDOM_STATE)],
        'models__max_depth': range(2, 4),
        'models__min_samples_split': range(1, 4),
        'models__min_samples_leaf': range(1, 3)

Лучшая модель версии 2: 
SVC(degree=2, kernel='linear', probability=True, random_state=42)
Метрика лучшей модели по кросс-валидации: 0.8941
Метрика ROC-AUC на тестовой выборке: 0.9263

Изменения версии 3:
- Из пайплайна удалена модель DecisionTreeClassifier()
- Изменен гиперпараметр модели SVC - 'models__degree': range(1, 4)
- Изменен гиперпараметр модели LogisticRegression - 'models__C': range(1, 8)

Лучшая модель версии 3:
SVC(degree=1, probability=True, random_state=42)
Метрика лучшей модели по кросс-валидации: 0.9011
Метрика ROC-AUC на тестовой выборке: 0.9201

Изменения версии 4:
- Изменен гиперпараметр модели SVC - 'models__degree': range(1, 2)

Лучшая модель версии 4:
LogisticRegression(C=1, l1_ratio=0.5, penalty='elasticnet', random_state=42, solver='saga')
Метрика лучшей модели по кросс-валидации: 0.8993
Метрика ROC-AUC на тестовой выборке: 0.925