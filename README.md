# Иннокентий Мотрий | Python Backend Developer

### 👨‍💻 Обо мне

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=for-the-badge&logo=sqlalchemy&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Pytest](https://img.shields.io/badge/Pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

Python Backend-разработчик с 2 годами коммерческого опыта в разработке серверных приложений и автоматизации (АО «ЭлеСи») и фундаментальным 5-летним инженерным бэкграундом.

Специализируюсь на проектировании масштабируемой бэкенд-архитектуры, оптимизации баз данных, многопоточных и асинхронных сервисах на **FastAPI** и **Django**.

---

### 🛠 Технологический стек

- **Backend:** Python 3.12+, FastAPI, Django, Asyncio, Threading, aiohttp, Server-Sent Events (SSE)
- **Базы данных & ORM:** PostgreSQL, SQLAlchemy 2.0 (asyncpg), Django ORM, Alembic, SQLite
- **Архитектура & Качество:** Clean Architecture, SOLID, DRY, Pytest, pytest-django, Logging
- **Инфраструктура & DevOps:** Docker, Docker Compose, Nginx, Gunicorn, Uvicorn, Linux (Ubuntu), Git
- **Интеграция & Desktop:** REST API, PySide6 (Qt), XML-парсеры, PyModbus (Modbus TCP)

---

### 💼 Ключевые проекты

#### 🎲 [Zatusim — Социальный лаунчер для живых тусовок и игр](https://zatusim.online/)
**Современная full-stack платформа для вечеринок, командных игр и знакомств**

- **Стек:** 
  - **Backend:** Python 3.12+, FastAPI (Async/Await), SQLAlchemy 2.0 (AsyncSession + asyncpg), Pydantic v2, Alembic, PyJWT, Bcrypt.
  - **Frontend:** React Native (Expo Web), TypeScript, React 19, Axios, Context API.
  - **DevOps & Infra:** Docker Compose, Nginx Reverse Proxy (SSL/TLS Let's Encrypt), GitHub Actions (CI/CD), Pytest.

- **Архитектурные и технические решения:**
  - **Модульная архитектура (Vertical Slicing):** Разделение на независимые изолированные сервисные модули (`users`, `auth`, `friends`, `parties`, `games`) с собственными `APIRouter()`, слоем бизнес-логики (Service layer) и доменными исключениями.
  - **Асинхронный ORM & Вычисляемые поля:** SQLAlchemy 2.0 с `asyncpg`. Расчёт возраста и статуса `is_adult` на лету через Pydantic `@computed_field` на основе даты рождения (без использования cron-пересчёта и мусорных полей в БД).
  - **Гибкая система приватности:** Хранение флагов видимости полей профиля в `JSONB`-колонке PostgreSQL и динамическая фильтрация данных на уровне бэкенда при публичном запросе профиля (для гостей, всех пользователей или только друзей).
  - **Медиа-подсистема:** Асинхронная загрузка аватарок (`UploadFile` + `aiofiles`) с автоматической очисткой старых файлов, валидацией MIME-типов и монтированием Docker Volumes для сохранения файлов при перезаборке контейнеров.
  - **CI/CD & Автоматическое тестирование:** Настроен GitHub Actions workflow — автоматический запуск интеграционных тестов на `pytest` в изолированном контейнере PostgreSQL 15, проверка линтером `Ruff`, автоматическое применение миграций Alembic и zero-downtime деплой на VPS по SSH при пуше в `master`.
  - **VK-style UI/UX Layout:** Адаптивный веб-интерфейс на React Native (Expo Web) с авто-сворачиваемым сайдбаром, сокрытием защищённых роутов для гостей, модальными окнами управления аккаунтом и переключателем тусовочного статуса (`ready`, `busy`, `snooze`).

#### 🚀 [YourDev — Сервис заказа IT-разработки](https://github.com/Kentiy2717/yourdev)
**Асинхронная веб-платформа на FastAPI и Clean Architecture**
- **Clean Architecture:** Жесткое разделение слоев (Router $\rightarrow$ Service $\rightarrow$ Repository).
- **Стек:** FastAPI 0.118, SQLAlchemy 2.0 (asyncpg), Alembic, PostgreSQL.
- **Инфраструктура:** Multi-stage сборка Docker, Nginx, Uvicorn, Gunicorn.

#### 💆‍♂️ [YourProMassage — Платформа услуг с блогом](https://github.com/Kentiy2717/yourpromassage)
**Сервис с системой отзывов, премодерацией и динамическим блогом**
- **Стек:** Django 3.2, PostgreSQL, Pytest, Django Signals.
- **Архитектурные решения:** Кастомная аутентификация по Email (`AbstractUser`), мягкое удаление (`Soft Delete`), каскадная синхронизация целостности данных на сигналах с `transaction.on_commit`.
- **Тестирование:** Покрытие бизнес-логики интеграционными и модульными тестами на `pytest-django`.

#### 📚 [Биполярный Экспресс — Контентная платформа](https://github.com/Kentiy2717/bipolar-express)
**Каталог книг и веб-блог с оптимизированными запросами к БД**
- **Стек:** Django 3.2, PostgreSQL 15, Docker Compose, Nginx, Certbot.
- **Оптимизация:** Полное исключение проблемы N+1 запросов с помощью `select_related`, `prefetch_related` и агрегации `annotate`.

#### 🏭 Платформа HIL-тестирования ПЛК (АО «ЭлеСи»)
**Система параллельного запуска автотестов прошивок промышленных контроллеров**
- **Стек:** Python, Django, PostgreSQL, Threading, SSE, PyModbus.
- **Результат:** Сокращение времени регрессионного тестирования на 90% (400+ автотестов по протоколу Modbus TCP), многопоточный неблокирующий движок с передачей телеметрии в реальном времени.

---

### 📫 Контакты

- 📞 **Телефон**: +7 (923) 410-13-38
- ✉️ **Email**: 79234101338@yandex.ru
- 💬 **VK**: [vk.com/kentiy2717](https://vk.com/kentiy2717)
- 💻 **GitHub**: [github.com/Kentiy2717](https://github.com/Kentiy2717)
- 📍 **Локация**: Томск, Россия (готов к удаленной работе)
