# Business Simulation Engine (DataCode)

Симулятор жизненного цикла бизнеса. Генерирует синтетические CSV-таблицы для обучения моделей и BI.

## Запуск

```bash
# 30 компаний × 60 месяцев (5 лет), seed=42
datacode busines_generater/main.dc

# свои параметры: бизнесы, месяцы, seed
datacode busines_generater/main.dc 100 120 7
```

## Модули

| Файл | Роль |
|------|------|
| `world_generator.dc` | макроэкономика (инфляция, ставка, спрос…) |
| `market_generator.dc` | отрасли и города |
| `business_generator.dc` | создание компаний |
| `event_engine.dc` | случайные события |
| `decision_engine.dc` | решения владельца |
| `simulation_engine.dc` | помесячная экономика и lifecycle |
| `dataset_exporter.dc` | экспорт CSV |
| `main.dc` | точка входа |

## Отрасли

`restaurant`, `saas`, `retail`, `production`, `autoservice`, `logistics`

## Жизненный цикл

`opening → growth → stable → scale → crisis → recovery → sold | bankrupt`

## CSV в `output/`

| Файл | Содержание |
|------|------------|
| `businesses.csv` | стартовые параметры компаний |
| `world_history.csv` | состояние мира по месяцам |
| `monthly_history.csv` | финансы каждой компании каждый месяц |
| `events_log.csv` | события |
| `decisions_log.csv` | решения владельца |
| `outcomes.csv` | итог: выжил / банкрот / продан |
