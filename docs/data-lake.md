# Data Lake Corporate Data Platform
## Объектное хранилище
В проекте используется RustFS.
- S3 API:
```
http://localhost:9000
```
- Web Console:
```
http://localhost:9001
```
## Структура Data Lake
Используются две зоны:
- RAW – исходные данные.
- PROCESSED – обработанные данные.
## RAW
Bucket:
```
corporate-raw
```
Object:
```
companies/companies.csv
```
Источник:
```
PostgreSQL, таблица companies.
```
## PROCESSED
Bucket:
```
corporate-processed
```
Object:
```
reports/companies_by_city.csv
```
Данные формируются ETL-конвейером Apache Airflow.

## Поток данных
PostgreSQL → Extract → Transform → Load → RustFS → corporate-processed
