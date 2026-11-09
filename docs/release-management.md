# Управление версиями Corporate Data Platform
## Текущая версия
2.2.0

## Git tag
v2.2.0

## Docker image
```
ghcr.io/lovvkkk/corporate-data-platform:2.2.0
```

## Процесс выпуска версии
1. Изменение исходного кода.
2. Проверка приложения.
3. Создание Git-коммита.
4. Создание Git-тега версии.
5. Публикация Git-тега.
6. Автоматическая сборка Docker-образа.
7. Публикация образа в Container Registry.
8. Изменение версии образа в Kubernetes Deployment.
9. Rolling Update.
10. Проверка работоспособности приложения.

## Восстановление предыдущей версии
Для просмотра истории Deployment:
```
kubectl rollout history deployment/corporate-data-deployment
```

Для отката:
```
kubectl rollout undo deployment/corporate-data-deployment
```
