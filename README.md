# _Каверзин Алексей Сергеевич_
**Senior Java Engineer | AI Agent Systems Architect**

## Profile
Инженер с более 5-ю годами в финтехе (Альфа-Банк) и практикой проектирования автономных мультиагентных систем. Сочетаю enterprise-экспертизу с R&D в LLM-агентах и ML-валидации. Автор двух проектов: мультиагентной кодогенерации и симулятора медицинских рисков с полным ML-пайплайном. Прошёл роли разработчика, системного аналитика и Scrum-мастера — вижу систему от контрактов до delivery-процессов.

---

## R&D: Multi-Agent Autonomous Coding System
**ai-supervisor** - оркестратор LLM-агентов (java spring-ai), реализует выполнение задачи "под ключ", начиная от бизнес требований в задаче task tracker и заканчивая инкриментом проекта.

Архитектура реализует принципы Claude Code / Codex CLI: полный контекст, итеративное планирование, самокоррекция.

*   **Analyser Agent + State Machine** (IDLE → ANALYSING → DECOMPOSING → SPAWNING → DONE): LLM-декомпозиция с JSON Schema-валидацией, построение графа зависимостей с детекцией циклов.
*   **Layered Spawning:** параллельный запуск Dev-агентов (UI/API/QA) слоями с учётом зависимостей — корректное исполнение без deadlocks.
*   **Self-Correction Loop:** Reviewer-агенты (UI/API/QA) возвращают замечания Dev-агентам на итеративную доработку.
*   **Event-Driven Orchestration:** Supervisor координирует пул, `--resume` из snapshot при сбоях.
*   **Observability:** Prometheus-метрики на всех уровнях — `agent_execution_duration_seconds`, `layer_agents_spawned{layer=N}`, `dependency_cycles_detected`.
*   **Runtime:** CLI (CI/CD) и WEB (REST + Actuator).

*Стек:* Java 25, Gradle 9.5, PostgreSQL 16, Event-Driven, State Machine, LLM API, MCP, Docker, Prometheus.

---

## R&D: SyntheticHealthSimulator
**Генератор медицинских данных с ML-пайплайном оценки рисков**

*   Траектории здоровья 5000 пациентов на 20 лет по эпидемиологическим моделям (SCORE2, FINDRISC-like).
*   Полный ML-цикл: статистическая валидация (Brier score, E/O ratio, calibration slope) → обучение ансамблей (AUC-ROC до 0.65) → sensitivity analysis устойчивости моделей.

*Стек:* Python, scikit-learn, pandas, Jupyter.

*Опыт валидации вероятностных выходов и risk-scoring — фундамент для агентного риск-менеджмента.*

---

## Профессиональный опыт

**Альфа-Банк** · Senior Java Developer
*Март 2021 — настоящее время · 5 лет 3 месяца · Fintech, зарплатные проекты*

Backend высоконагруженных микросервисов в домене, критичном к операционным рискам.

*   **Единая точка входа:** спроектировал кастомный OAuth2-маршрутизатор за пределами Spring Cloud Gateway с интеграцией банковского IdP.
*   **Автоматизация risk-чувствительных операций:** сервис массового открытия счетов (парсинг Excel, валидация, REST/Kafka к ядру банка).
*   **Risk-aware логика:** переработка алгоритма каналов доставки карт с учётом резидентности и комплаенс-правил.
*   **Legacy-трансформация:** рефакторинг, рост тестового покрытия, code review, миграция более 10-ти сервисов на Spring Boot 3.
*   **Observability:** Kubernetes/Helm (dev/int/prod), Prometheus/Grafana, Jenkins-пайплайны.

**Смежные роли:**
*   **System Analyst (1 год):** проектирование API-контрактов с архитектором, проработка техрешений.
*   **Scrum Master (1 год):** фасилитация daily/ретро/планирований, устранение блокеров.

---

## Technical Stack

*   **Languages:** Java 8–25, Python
*   **AI & Agents:** Multi-Agent Orchestration, State Machines, LLM API, Tool Use (MCP), Prompt Engineering
*   **ML & Stats:** scikit-learn, pandas, numpy, matplotlib, AUC-ROC, Brier score, calibration slope, sensitivity analysis, градиентный бустинг, ансамбли моделей, A/B-тестирование
*   **Frameworks:** Spring Boot 2/3, Security, Cloud, Data, Hibernate
*   **Messaging:** Apache Kafka, REST, SOAP
*   **Databases:** PostgreSQL, MySQL, MongoDB, Redis
*   **DevOps:** Kubernetes, ArgoRollout, Helm, Docker, Jenkins
*   **Observability:** Prometheus, Grafana, Actuator
*   **Practices:** Microservices, Event-Driven, CI/CD, Agile/Scrum, System Analysis

---

## Education & Continuous Learning

**OTUS** — Machine Learning Professional (в процессе, старт 2026)
*   Продвинутые методы ML: градиентный бустинг, SVM, кластеризация (K-means, DBSCAN), алгоритмы на графах
*   Deep Learning: PyTorch, CNN, RNN/LSTM/GRU, backpropagation, оптимизация нейросетей
*   NLP: трансформеры, BERT, NER, тематическое моделирование, векторные представления слов
*   Временные ряды: ARIMA, feature engineering, кластеризация временных рядов
*   Рекомендательные системы: коллаборативная фильтрация, матричная факторизация, Apache Spark

**OTUS** — Machine Learning Basic (завершён, 2025–2026)
*   Python для ML: pandas, numpy, matplotlib, seaborn, scipy, sklearn
*   Классические модели: линейная/логистическая регрессия, деревья решений, ансамбли, метод ближайших соседей
*   Математический фундамент: линейная алгебра, оптимизация, теория вероятностей, математическая статистика
*   A/B-тестирование, проверка гипотез, исследование зависимостей
*   Выпускной проект: ML-модель на реальных данных с полным циклом от EDA до продакшена

---

## Краткий профиль работы

1.  **Мультиагентность:** собственный проект с оркестрацией, layered spawning, self-correction, state machine.
2.  **Риск-менеджмент:** 5 лет в финтехе на критичных системах (OAuth2, комплаенс) + ML-валидация risk-моделей.
3.  **Product ownership:** опыт System Analyst и Scrum Master, готовность развивать решение до открытой платформы.
