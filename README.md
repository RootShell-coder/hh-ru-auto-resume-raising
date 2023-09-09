# hh-ru-auto-resume-raising
### Описание
Программа для автоматического подъема резюме на [HeadHunter](https://hh.ru/) 
каждые 4 часа. Альтернатива платной услуге 
[Продвижение.LITE](https://hh.ru/applicant/services/payment?from=landing&package=lite) 
от HeadHunter.  
Примечание:
работает только с Unix системами, это связано с используемой функцией time.tzset() для установления часового пояса.
### Инструкция
Переименовать
```
mv .env_pub .env
```
Заполнить все данные в .env по примеру:
 - без выделения переменных кавычками!
 - в поле proxy оставить 1 из вариантов (если нет прокси, то proxy=None)

Установить зависимости
```
python3 -m pip install -r requirements.txt
```
Запустить
```
python3 bot.py
```
### Принцип работы
1) Выполнить пункты из инструкции
2) Активировать бота (если бот был активирован ввести команду /start)
3) Нажать кнопку "Авторизация" (подгрузятся токены и сохранятся в файле config/tokens.json)
4) Нажать кнопку "Обновить список резюме" (подгрузятся резюме, в ответном сообщении наименования при нажатии сохраняются в буфер обмена)
5) Нажать кнопку "Добавить/обновить" и заполнить необходимые данные (в случае если запись уже существует, то она перезапишется с новыми данными)
6) Готово!
### Дополнительно 
- При поднятии придет уведомление в виде: наименование резюме, ответ запроса, время (примеры ответов запроса в services/status_code.py)
- Кнопка "Расписание" (выведется список с динамическим расписанием, меняется в случае поднятия резюме)
- Кнопка "Список резюме" (локальный список, появляется после выполнения 4 пункта Принципа работы)
- Кнопка "Удалить" (далее ввести наименование резюме, которое нужно удалить из расписания)
- Кнопка "Профиль" (выведется список информации из файла .env)
- Кнопка "Вкл/выкл уведомления" (меняет состояние уведомлений о поднятии резюме)
### Подробнее об авторизации
- При нажатии на кнопку "Авторизоваться" токены создаются либо при их наличии обновляются.
- Если запущено расписание, то токены автоматически пересоздаются в случае разрыва сессии.
