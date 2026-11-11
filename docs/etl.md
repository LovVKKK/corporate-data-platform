# ETL-процесс Corporate Data Platform

## Назначение
Apache Airflow запускает конвейер `corporate_etl`, который читает компании из PostgreSQL, считает показатели по городам и сохраняет отчёт в CSV.

## Расписание
DAG выполняется ежедневно (`schedule="@daily"`). Пропущенные запуски не догоняются: `catchup=False`.

## Последовательность задач
1. `extract_companies` — чтение таблицы `companies`.
2. `transform_companies` — группировка по городу: число компаний, сумма и среднее число сотрудников.
3. `load_report` — запись файла `/opt/airflow/output/companies_by_city.csv`.

## Источник и результат
Источник: база `corporate`, таблица `companies`.

Результат на хосте:
```
airflow/output/companies_by_city.csv
```

## Запуск
Сервис Airflow описан в `compose.yaml` и доступен по адресу http://localhost:8081.
DAG можно запустить вручную из интерфейса Airflow или командой:
```
docker compose exec airflow airflow dags trigger corporate_etl
```
