Doika - модуль, які дапамагае прымаць ахвяраванні з дапамогай банкаўскіх картак і наладзіць новы падыход у фандрэйзінгу беларускіх некамерцыйных грамадскіх арганізацый на сваіх сайтах

## Бягучыя задачы праекта

1. Рэфактарынг кода iтэрацыi 1.2 для пераносу на бягучую (1.3) iтэрацыю. Перанос фронтэнда на vue.js
2. Дэталізуем (абмяркоўваем) задачы па [накірункам](https://github.com/diglabby/doika/milestones)
3. Вывучаем API BePaid [рэкурэнтные плацяжы](https://docs.bepaid.by/ru/subscriptions/intro)

## Як працуе Doika?
![image](https://trello-attachments.s3.amazonaws.com/5afee29cdc7e2f274f42491b/5bb66bb619b45a5e5bf3f89a/1667f21546988191810730b1579c02cb/doika_end_gif.gif)

## Усталёўка
* **З арганізацыйнага боку**: Арганізацыя павінна мець афіцыйную дзяржаўную рэгістрацыю, некамерцыйны статус (арт. 553 Грамадзянскага кодэкса РБ: ахвяраванні могуць прымаць толькі некамерцыйныя арганізацыі ) і рахунак у любым беларускім банку. Збор сродкаў ад фізічных асобаў можа ажыцяўляцца на любую мэту, якая не супярэчыць статутнай мэце некамерцыйнай арганізацыі.
* **З юрыдычнага боку**: Дамен грамадскай арганізацыі павінен быць абавязкова зарэгістраваны на юрыдычную асобу і прайсці рэгістрацыю ў БЕЛДІЭ – дзяржаўнай інспекцыі Рэспублікі Беларусь па электрасувязі Міністэрства сувязі і інфарматызацыі Рэспублікі Беларусь. Галоўная ўмова рэгістрацыі: размяшчэнне сайта на хостынгу на тэрыторыі Беларусі.
* **З тэхнічнага боку**: Для забеспячення бяспекі плацежных дадзенных на Вашай старонцы з модулем мы рэкамендуем выкарыстоўваць пратакол https. Апошняя версія і падрабязная інструкцыя па ўсталёўцы Doika_1.2 знаходзіцца [тут](https://github.com/diglabby/doika_1.2/wiki/Устаноўка-модуля-на-хостынг).


## Распрацоўшчыку - як запусціць праект?

1. Заходзім у рэпазіторый https://github.com/diglabby/doika.git і ствараем для сябе fork
2. Дадаем змесціва fork рэпазіторыя ў корань вашага сайта з дапамогай git clone. Пераключаемся на  dev branch, з дапамогай git checkout (напрыклад, git checkout dev)
3. Неабходна вызначыць групу і карыстальніка для ўсіх файлаў модуля камандай: "sudo chown -R www-data:www-data ."
4. Імпартуем файл doika.sql у базу дадзеных, пры з'яўленні памылак звяртаем ўвагу на версію MySQL.
5. Рыхтуем канфіг файл. Для гэтага ў тэчцы doika ствараем копію файла .env.example і надаем яму імя .env
6. Дадаем у файл .env свае дадзеныя DB_DATABASE={your_database} DB_USERNAME={your_username} DB_PASSWORD={your_password}
7. Генерым ключ для laravel: зайсцi у папку doika праз i выканаць php artisan key:generate
8. Усталяваная версія павінна запускацца на Вашым лакальным хасце са шляхам doika/admin/login
9. Выкарыстоўваеце дадзеныя для ўвахода Лагін: demo@example.com , Пароль: demo


## Распрацоўшчыку - як запусціць праект пры дапамозе Open Server https://ospanel.io/download/?

налада:
1. Адкрыць налады Open Server, ўкладка дамены, ручное кіраванне, напісаць імя дамена, на прыклад doika, папка дамена выбраць localhost
2. Адкрыць ўкладку модулі, выбраць Apache 7.2, php 7.2, mySQL 5.7, захоўваем, запускаем сервер
3. Заходзім у рэпазіторый https://github.com/diglabby/doika.git і націскаем clone or download і капіруем адрас
4. Заходзім у тэчку localhost і клонируем туды праект пры дапамозе git clone https://github.com/diglabby/doika.git
5. Заходзім у doika і пры дапамозе гіт пераключаемся на dev branch (git checkout dev)
6. Имортуем файл doika.sql ў базу дадзеных (адкрываем дадаткова, PhpMyAdmin, ствараем новую БД, ўваходзім у яе, націскаем імпарт і выбіраем файл doika.sql)
7. Змяняем конфіг файла. Меняем назву файла .env.example на .env і заходзім у яго. DB_DATABASE = doika, DB_USERNAME = root (калі не мянялі) DB_PASSWORD = (пуста калі не устонауливали пароль), мяняем радок APP_KEY = на APP_KEY = base64:8ObMpr3jB1o5SQ3az2pqXo9tSPGAZOponr4eHBoDs9Y =
8. Пішам ў браўзэры http: // doika / doika / admin ўводзім demo@example.com demo


[Як зрабіць свой унёсак](CONTRIBUTING.md)

## Структура праекта

для чаго патрэбны ключавыя файлы (канфіг файл, файл інсталятар, дзе ляжыць фронт, дзе бэк, якія заўвагі па шляхах

## Патрабаванні да распрацоўкі
Для распрацоўшчыкаў:
* Apache
* MySQL >= 5.7
* PHP >= 7.1.3
* OpenSSL PHP Extension, PDO PHP Extension, Mbstring PHP Extension, Tokenizer PHP Extension, XML PHP Extension, Ctype PHP Extension, JSON PHP Extension пашырэнне для PHP
* На базе фрэймворка Laravel 5.6 (для усталёўкі патрэбны Composer)
* [Кодынг-стандарт](https://github.com/diglabby/doika_1.2/wiki/%D0%9A%D0%BE%D0%B4%D1%8B%D0%BD%D0%B3-%D1%81%D1%82%D0%B0%D0%BD%D0%B4%D0%B0%D1%80%D1%82) 
* [Прыклад афармлення бага](https://github.com/diglabby/doika_1.2/wiki/%D0%9F%D1%80%D1%8B%D0%BA%D0%BB%D0%B0%D0%B4-%D0%B0%D1%84%D0%B0%D1%80%D0%BC%D0%BB%D0%B5%D0%BD%D0%BD%D1%8F-%D0%B1%D0%B0%D0%B3%D0%B0)
* як працем з рэквэстамі..

## Што трэба каб паставіць модуль?
* З арганізацыйнага боку: Арганізацыя павінна мець афіцыйную дзяржаўную рэгістрацыю, некамерцыйны статус (арт. 553 Грамадзянскага кодэкса РБ: ахвяраванні могуць прымаць толькі некамерцыйныя арганізацыі ) і рахунак у любым беларускім банку. Збор сродкаў ад фізічных асобаў можа ажыцяўляцца на любую мэту, якая не супярэчыць статутнай мэце некамерцыйнай арганізацыі.
* З юрыдычнага боку: Дамен грамадскай арганізацыі павінен быць абавязкова зарэгістраваны на юрыдычную асобу і прайсці рэгістрацыю ў БЕЛДІЭ – дзяржаўнай інспекцыі Рэспублікі Беларусь па электрасувязі Міністэрства сувязі і інфарматызацыі Рэспублікі Беларусь. Галоўная ўмова рэгістрацыі: размяшчэнне сайта на хостынгу на тэрыторыі Беларусі.
* З тэхнічнага боку: Для забеспячення бяспекі плацежных дадзенных на Вашай старонцы з модулем мы рэкамендуем выкарыстоўваць пратакол https. Сэрверны асяродак: apache, php, mysql.

## Як паставіць модуль?
Апошняя версія і падрабязная інструкцыя па ўсталёўцы Doika_1.2 знаходзіцца [тут](https://github.com/diglabby/doika_1.2/wiki/%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D1%9E%D0%BA%D0%B0-%D0%BC%D0%BE%D0%B4%D1%83%D0%BB%D1%8F-%D0%BD%D0%B0-%D1%85%D0%BE%D1%81%D1%82%D1%8B%D0%BD%D0%B3). 

## Як пачаць распрацоўку?
1. Праглядзець статус і роадмэп распрацоукi праекта на старонцы [milestones](https://github.com/diglabby/doika/milestones?direction=asc&sort=due_date&state=open).
2. Як разгарнуць лакальны асяродак для распрацоўкі [інструкцыя] (TODO).
3. Праглядзець [дакументацыю](https://realtimeboard.com/app/board/o9J_k0X88dM=/). 
- [Архiтэктура файлаў i базы](https://realtimeboard.com/app/board/o9J_k0X88dM=/?moveToWidget=3074457346027045333)
- [Блок-схемы](https://realtimeboard.com/app/board/o9J_k0X88dM=/?moveToWidget=3074457346144718504)
- [Спiс класаў](https://realtimeboard.com/app/board/o9J_k0X88dM=/?moveToWidget=3074457346135802429)
- [Вiкi](https://github.com/diglabby/doika/wiki/) Частка "для распрацоўшчыкаў".
- Пры з'яўленні пытанняў і цяжкасцей запытаць у Slack бягучых удзельнікаў каманды: @fr0zen, @tyuba4, @Сёмка, @SvetaN (інвайт у канал Slack магчыма атрымаць звярнуўшыся да нас праз [форму](https://docs.google.com/forms/d/e/1FAIpQLSf3q7HMtfJly4wCrRyIlHDdAzFExSjw2vqbA62XFJHofjMqjg/viewform)).
- Увага! Робім пул рэквэсты ў галіну dev.

## У мяне засталіся пытанні...
Заходзьце на старонку з найбольш частымі пытаннямі па праэкту Doika [FAQ](https://github.com/diglabby/doika/wiki/FAQ)


## Ліцэнзіі і абмежаванні
Выкарыстоўваем наступныя ліцэнзіі:
* [GNU GPL 3.0](https://www.gnu.org/licenses/gpl-3.0.en.html) - для напісанага ў праекце кода
* [Creative Commons Attribution Share-Alike](https://choosealicense.com/licenses/cc-by-sa-4.0/) - для ўсяго кантэнта у тым ліку выяваў, тэхнічнай дакументацыі

Прадукт распаўсюджваецца "як ёсць". Гэта значыць, любыя мадыфікацыі вы робіце самастойна або дамаўляецеся з камандай распрацоўшчыкаў на пэўны кошт (falanster.by@gmail.com).

## Карысныя спасылкі
* [Прэзентацыйная ўэб-старонка](https://doika.falanster.by/)
* [Прэзентацыя у паўэрпоінт](https://docs.google.com/presentation/d/144zEv4DyBoa0jDKwee30Rip0oKZ8QzkeUKaNCRWy1qY/edit#slide=id.g42bd4a5055_0_28)

