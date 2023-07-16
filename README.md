# Домашняя работа по инфраструктуре

1. Настройка линтера коммитов
   Используется `commitlint` в одной из проверок GH Actions
---
2. Проверки для пулл реквестов
   В качетсве проверок на каждый PR запускается 
   - `npm lint` - линтер кода
   - `npm ci:test:unit` - модельные тесты
   - `npm ci:test:e2e` - интеграционные тесты
   Результаты проверок отображаются на странице PR
   Мерж изменений заблокирован без прохождения тестов
---
3. Релизы
   При пуше релизного тега:
   - Создается release с версией тега
   - Создается issue (RELEASE) с информацией о релизе и changelog`ом от предыдущей версии
   - При повторном запуске с тем же тегом изменяется старый issue
   - Запускается проверки и 
   - После успешных проверок запускается деплой GH Pages
