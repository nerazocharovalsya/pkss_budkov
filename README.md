# pkss_budkov

Mindmap (Ментальная карта) cтруктурирует ключевые аспекты проектирования системы.
В клиент-серверной системе ателье карта охватывает архитектуру (клиент, сервер, базы данных), задачи проектирования (масштабируемость, безопасность) и примеры использования (оформление заказов, управление услугами, отчетность).
Используется для обсуждения требований и планирования разработки.
```mermaid
mindmap
Система ателье (оформление заказов)
  Архитектура
    Многоуровневая
      Клиент
        Веб-приложение
      Сервер
        API
          REST API
        Сервисы
          AuthService
          OrderService
          ClientService
          WorkerService
          TaskService
          NotificationService
      Базы данных
        PostgreSQL
  Задачи проектирования
    Оптимизация
      Масштабируемость
      Балансировка нагрузки
    Безопасность
      Аутентификация
      Авторизация
      Защита от DDoS
      Шифрование
    Моделирование
      UML
      C4
      BPMN
  Примеры использования
    Оформление заказов
    Управление задачами сотрудников
    Уведомления клиентов
    Отслеживание статуса заказов
```
Journey Map (Карта пользовательского пути)
Показывает пошаговый процесс взаимодействия пользователя с системой.
Например, пользователь входит в систему, выбирает услуги, создает заказ, подтверждает его, получает уведомления и завершает сеанс.
Помогает понять, как пользователи будут использовать систему и где могут возникнуть сложности.
```mermaid
journey
    title Пользовательское путешествие в клиент-серверной системе ателье (оформление заказов)
    section Вход в систему
      Пользователь открывает приложение или веб-сайт ателье: 5: Пользователь
      Клиент отправляет запрос на загрузку страницы: 5: Клиент
      Сервер возвращает страницу входа: 5: Сервер
      Пользователь вводит логин и пароль: 5: Пользователь
      Клиент отправляет данные для аутентификации: 5: Клиент
      Сервер проверяет данные пользователя: 5: Сервер
      Сервер возвращает сообщение об успешном входе: 5: Сервер
      Клиент отображает главную страницу системы: 5: Клиент
    section Выбор услуги
      Пользователь выбирает раздел "Оформление заказов": 5: Пользователь
      Клиент отправляет запрос на загрузку интерфейса оформления заказа: 5: Клиент
      Сервер возвращает данные о доступных услугах и мастерах: 5: Сервер
      Клиент отображает интерфейс оформления заказа: 5: Клиент
      Пользователь выбирает услугу и мастера: 5: Пользователь
      Клиент отправляет данные о выбранной услуге: 5: Клиент
    section Оформление заказа
      Пользователь вводит детали заказа (описание, дата, предпочтения): 5: Пользователь
      Клиент отправляет данные заказа на сервер: 5: Клиент
      Сервер сохраняет данные заказа в базе данных: 5: Сервер
      Сервер подтверждает успешное создание заказа: 5: Сервер
      Клиент отображает подтверждение и номер заказа: 5: Клиент
    section Отслеживание заказа
      Пользователь открывает раздел "Мои заказы": 5: Пользователь
      Клиент отправляет запрос на получение данных о заказах: 5: Клиент
      Сервер возвращает информацию о текущих заказах пользователя: 5: Сервер
      Клиент отображает список заказов и их статус: 5: Клиент
    section Завершение сессии
      Пользователь завершает работу в системе: 5: Пользователь
      Клиент отправляет запрос на завершение сессии: 5: Клиент
      Сервер завершает сеанс и обновляет данные: 5: Сервер
      Клиент отображает сообщение о выходе: 5: Клиент
```
Quadrant Chart (Диаграмма приоритетов)
Представляет функции системы по их приоритету и сложности реализации.
Высокий приоритет имеют задачи, такие как создание заказов и интеграция с платежными системами.
Помогает расставить приоритеты в разработке и сосредоточиться на наиболее важных функциях.
```mermaid
quadrantChart
  title Приоритет разработки функций системы ателье
  x-axis "Низкий приоритет" --> "Высокий приоритет"
  y-axis "Низкая сложность" --> "Высокая сложность"

  "Авторизация и аутентификация": [0.7, 0.5]
  "Просмотр доступных услуг": [0.5, 0.3]
  "Оформление заказа": [0.8, 0.6]
  "Управление клиентами и работниками": [0.9, 0.7]
  "Поиск мастеров по навыкам": [0.6, 0.2]
  "Отправка уведомлений о статусе заказа": [0.3, 0.1]
  "Отмена или изменение заказа": [0.7, 0.75]
  "Интеграция с платежными системами": [0.9, 0.8]
  "Генерация отчетов по заказам": [0.8, 0.9]
```
GitGraph (Диаграмма веток Git)
Отображает историю разработки системы, включая ветки, коммиты и слияния.
Например, ветка feature/order_management охватывает создание модели заказов, добавление услуг в заказ и подтверждение заказа.
Используется для управления версионностью и контроля разработки.
```mermaid
gitGraph
   commit id: "Initial commit"
   branch feature/auth
   checkout feature/auth
   commit id: "Добавление формы входа"
   commit id: "Реализация проверки данных пользователя"
   branch feature/ui_improvements
   checkout feature/ui_improvements
   commit id: "Улучшение интерфейса входа"
   commit id: "Адаптивный дизайн страницы входа"
   checkout feature/auth
   commit id: "Добавление JWT для авторизации"
   checkout feature/ui_improvements
   merge feature/auth id: "Слияние авторизации"
   checkout main
   branch feature/service_management
   checkout feature/service_management
   commit id: "Создание модели услуги"
   commit id: "Добавление интерфейса выбора услуг"
   branch feature/data_caching
   checkout feature/data_caching
   commit id: "Кэширование данных услуг"
   commit id: "Обновление кэша при изменении услуг"
   checkout feature/service_management
   commit id: "Фильтрация услуг по категориям"
   checkout feature/data_caching
   merge feature/service_management id: "Слияние управления услугами"
   checkout main
   branch feature/order_management
   checkout feature/order_management
   commit id: "Создание модели заказа"
   commit id: "Добавление услуг в заказ"
   commit id: "Обработка подтверждения заказа"
   branch feature/notification_system
   checkout feature/notification_system
   commit id: "Реализация отправки уведомлений о статусе заказа"
   commit id: "Настройка шаблонов уведомлений"
   checkout feature/order_management
   merge feature/notification_system id: "Слияние с системой уведомлений"
   checkout main
   branch feature/payment_integration
   checkout feature/payment_integration
   commit id: "Интеграция с платежными системами"
   commit id: "Поддержка различных методов оплаты"
   checkout feature/order_management
   merge feature/payment_integration id: "Слияние с управлением платежами"
   checkout main
   merge feature/ui_improvements id: "Мерж улучшений интерфейса"
   merge feature/data_caching id: "Мерж кэширования данных"
   merge feature/order_management id: "Мерж управления заказами"
```
