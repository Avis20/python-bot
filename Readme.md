## Тестовые боты для heroku

Все боты в бренчах
* v1-telebot = бот на python с либой telebot. Корявый слегка
* v2-aiogram = бот на python с либой aiogram. Пока только через pulling

## Запуск в heroku

- Если нет heroku-cli

```
curl https://cli-assets.heroku.com/install.sh | sh
```


- Клоним репу

```
git clone https://github.com/Avis20/python-bot.git
```


- Если что-то поменяли, то комитим и пушим
```
git add -A
git ci "test"
git push origin v2-aiogram
```

Важный момент! в heroku по какой-то причине сборка контейнера происходит только из веток master или main...
Если пушиш другую ветку, то она просто там создается

https://devcenter.heroku.com/articles/git#deploying-code

Поэтому прежде чем пушить в heroku нужно слить в main, переключиться и раскатать

```
git co -b main
git pull origin v2-aiogram
git push origin main
```


- Пушим все в heroku

```
heroku login
```

```
heroku create
```

```
git push heroku main
```
Если пишет ошибку типа контейнера нету, то удаляем в `.git/config` упоминание о heroku

```
heroku ps:scale web=1
Scaling dynos... done, now running web at 1:Free
```

Последняя строка хз че значит, хотя и без нее норм.
Скорее всего сколько приложений можно одновременно запустить, по умолчанию 1 шт, так что можно просто запушить и успокоиться

