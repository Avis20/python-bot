## Тестовые боты для heroku

Все боты в бренчах
* v1-telebot = бот на python с либой telebot. Корявый слегка
* v2-aiogram = бот на python с либой aiogram. Пока только через pulling

## Запуск в heroku

- Если нет heroku-cli

```
curl https://cli-assets.heroku.com/install.sh | sh
```

- Клоним пустую репу

```
sudo git clone https://github.com/Avis20/python3-test.git
git add -A
git ci "test"
git push origin master
```

- На локальной тачке

```
heroku login
```

```
heroku create
```

```
git push heroku master
```

```
heroku ps:scale web=1
Scaling dynos... done, now running web at 1:Free
```

Последняя строка хз че значит, хотя и без нее норм

