# Analytics Dashboard

Высокопроизводительный веб-дашборд реального времени для визуализации аналитики и мониторинга продуктовых метрик. Реализует непрерывную потоковую передачу данных через Server-Sent Events (SSE) и реляционную модель на PostgreSQL с Prisma ORM.

**Автор:** Дима Евгеньев ([@walsik111](https://github.com/walsik111))

---

## Стек технологий

- **Next.js & React** — полнофункциональный стек веб-приложения и SSR
- **TypeScript** — строгая статическая типизация
- **Tailwind CSS & shadcn/ui** — адаптивный тёмный интерфейс и компоненты на базе Radix UI
- **Prisma ORM** — типизированный доступ к данным и аналитические агрегации
- **PostgreSQL** — реляционная база данных для хранения метрик и сессий
- **Server-Sent Events (SSE)** — передача данных в реальном времени без постоянного опроса
- **Docker** — контейнеризация базы данных для локального запуска

---

## Локальный запуск

### 1. Клонирование репозитория

```bash
git clone https://github.com/walsik111/analytics-dashboard.git
cd analytics-dashboard
```

### 2. Установка зависимостей

```bash
npm install
```

### 3. Настройка переменных окружения

Скопируйте пример файла конфигурации:

```bash
cp .env.example .env
```

Убедитесь, что строка подключения к базе данных указана корректно:

```env
DATABASE_URL="postgresql://postgres:mysecretpassword@localhost:5432/mydb"
```

### 4. Запуск PostgreSQL через Docker

```bash
docker run --name postgres_container \
  -e POSTGRES_PASSWORD=mysecretpassword \
  -e POSTGRES_DB=mydb \
  -d -p 5432:5432 \
  -v postgres_data:/var/lib/postgresql/data \
  postgres
```

### 5. Применение миграций и запуск

```bash
npx prisma migrate deploy
npm run dev
```

Приложение будет доступно по адресу: [http://localhost:3000](http://localhost:3000).
