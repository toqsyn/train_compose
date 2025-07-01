# TRAIN_COMPOSE

Проект для сбора данных о цене BTC/USDT с Binance, сохранения в MongoDB и визуализации через Flask.

---

## 📦 Структура проекта
```
TRAIN_COMPOSE/
├── docker-compose.yaml
├── checker/
│ ├── app.py
│ ├── Dockerfile
│ └── requirements.txt
├── plot/
│ ├── app.py
│ ├── Dockerfile
│ ├── requirements.txt
│ └── templates/
│ └── index.html
├──readme.md
```
---

## 🚀 Запуск проекта

```bash
docker-compose up --build -d
```
После запуска открой в браузере:

http://localhost:5000 — визуализация данных (plot)

http://localhost:8081 — Mongo Express интерфейс

⚙ Сервисы
| Сервис        | Назначение                                     | Порт  |
| ------------- | ---------------------------------------------- | ----- |
| plot          | Flask-приложение для визуализации данных       | 5000  |
| checker       | Сбор цен BTC/USDT с Binance и запись в MongoDB | 5001  |
| mongo         | База данных MongoDB                            | 27017 |
| mongo-express | Веб-интерфейс для работы с MongoDB             | 8081  |


💡 Полезные команды

Логи сервиса:

```bash
docker-compose logs checker
docker-compose logs plot
```
Остановить и удалить контейнеры:
```bash

docker-compose down
docker-compose down -v 
```

📝 Примечания
MongoDB создаёт БД crypto_database и коллекцию btc_usdt_prices.

Данные обновляются каждые 5 секунд.

Строка подключения к MongoDB в коде:
```bash

mongodb://admin:admin@mongo:27017
```

👤 Автор: Arsen

