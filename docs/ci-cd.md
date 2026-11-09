# CI/CD проекта Corporate Data Platform
## Система автоматизации
Для автоматической проверки и сборки проекта используется GitHub Actions.

Workflow:
```
.github/workflows/build.yml
```

## События запуска
Workflow запускается при публикации изменений в настроенных ветках, при создании pull request в main и вручную.

## Выполняемые операции
1. Получение исходного кода.
2. Проверка синтаксиса Python.
3. Подготовка Docker Buildx.
4. Сборка Docker-образа.
5. Авторизация в GitHub Container Registry.
6. Публикация Docker-образа.

## Container Registry
Образы публикуются в GitHub Container Registry:
```
ghcr.io/lovvkkk/corporate-data-platform
```
Используются теги:
```
latest
Git commit SHA
```
