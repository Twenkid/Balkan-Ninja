# Balkan Ninja ? (по-широкообхватно)  
## Bulgarian Ninja - Българска Нинджа: Mission: Plovdiv - Мисия Пловдив (първо заглавие)
* Plovdiv Kombat, Пловдивска нинджа / Пловдивска битка
* Пловдивски бойци, Пловдивски бой, Пловдивска схватка, Plovdiv Kombat, Plovdiv Fighters and Lovers ... (работни заглавия)
* Балканска нинджа?

<img src="https://github.com/Twenkid/Plovdiv-Kombat/blob/main/geroi/bulgarian-ninja-1650.jpg">

Кратко обяснение в "скрийнкаст": https://youtu.be/NipnKTLq0pw

Първи прототип в развитие (проби със спрайтове автоматично извлечени от атласи на "МК3"):

Http://twenkid.com/video/ninja2.mp4

Http://twenkid.com/video/ninja3.mp4

* Проект за видео игра, вдъхновена от MK3 Ултимат, "Уличен боец", "Кадилаци и динозаври" и от въображението - 2D двубои с хумор, по-малко жестокост; с елементи и на други жанрове, преход между арените, вмъкнати сцени ("cut"-сцени) с героите, разнообразяване на гледната точка към битките с общи планове и др.
* Предложени платформи и библиотеки за разработка: OpenCV (Python & C++), PyGame, [<a href="https://github.com/pyglet/pyglet">pyglet</a>, <a href="https://github.com/ubuntunux/PyEngine3D">PyEngine3D</a>?], SDL, Godot, Unity, <a href="https://pypi.org/project/PyOpenAL">PyOpenAl</a>, OpenAl (звук) ...? В зависимост от разработчиците, може и няколко варианта.
* 27.10.2021: Или може би Rust, WGL, Bevy ...? + WebAssembly?
* Поредица: Пловдив, София, Търново, Варна, Бургас, Планини и др. (И други балкански страни: Гърция, Сърбия, Турция; Скопие ... )
* Възможни герои, които са налице с подходящи костюми и външен вид: <b>Нууб Сайбот, Смъртобот, Тоши и Ли, Контра, Червената шапчица и др.: виж <a href="#geroi">СНИМКИ</a> по-долу</b>
* Гръцки, турски и пр. герои
* Предложения, сътрудничество - пишете в <a href="https://github.com/Twenkid/Plovdiv-Kombat/issues">Issues</a> или се свържете с мен
* Потенциален екип и герои за сега: Тош, Ал, Кало, Валя, Деси

# План за реализация на начална версия

* Търсене на сътрудници и симпатизанти: разработчици, дизайнери, актьори, фотографи и видеографи, домакини на места, с които да се обсъждат идеи и да се започне реализация.
* Опитна разработка на технологията: (Редът може да варира или да е успореден)

1. Заснемане на определен фон, отбелязване на осветлението, което евентуално после да се моделира при рисуване на героите (избирателно да се осветяват). 
 "Оживяване" с детайли - спрайтове/анимации, хора влизащи в кадър.
1. Заснемане на един или двама герои на "зелен екран", извличане на кадри. 
 1. Или за начало, при липса на условия, ръчно изрязване на кадри от обикновено видео или рисуване, намиране на спрайтове от готови игри:
<a href="https://www.spriters-resource.com/snes/ultmortalkombat3/">Спрайтове на героите от МК3 Ултимат за SNES</a>, <a href="https://www.spriters-resource.com/snes/ultmortalkombat3/sheet/92665/">Спрайтове за Cyrax</a>, <a href="https://www.spriters-resource.com/playstation/mkmsz/sheet/37161/"> Спрайтове за PlayStation</a><br>
Извличане: чрез OpenCV (findContours) или по равния цвят на фона/прозрачност и копиране на правоъгълни обхващащи области, намиране на център и краища др. Включване в поредици/машина с мрежа от състояния и задаване на времеви белези - продължителността на движението. Това е необходимо за съвместяване/синхронизиране на записи, направени с различен каданс и пр.
Този прототип вече е в развитие: https://youtu.be/B_lVimRpsDQ
![image](/proto/ninja-19-11-2020.png)
![image](/proto/ninja2.jpg)

1. Разработка или внедряване на анимирана система/краен автомат (finite state machine) за герой и проба с анимация с модел, може и нарисуван, впоследствие сниман, с ограничен набор от движения: бойна стойка, приклякане, прав удар с юмрук, средно висок удар с крак и т.н. Извличане или използване на кадрите като маски при ударите.
1. Пробни звуци на герой, опити.
1. Налагане на други лица върху герой.
1. Допълнително изпъване на краката за високи ритници и др. ефекти.

**Желателни или за пробване:**
1. Скелет, добавени ръчно ключови точки или полуавтоматично с маркери - глава, връх на крайници, център на тежестта. Може би ще се опита също с автоматично разпознаване на позата за пораждане на скелета или приблизителното положение. Опити с: <a href="https://www.learnopencv.com/deep-learning-based-human-pose-estimation-using-opencv-cpp-python/">Deep Learning based Human Pose Estimation</a> - но не винаги е надеждно. Може да се доуточнява с Motion Tracking. Ръчното маркиране - движението на спрайта върви като видео на забавен кадър или ръчно сменяне на кадрите, посочване с мишката и пр. - също е решение.
 1. Налагане на образа като текстура върху мрежа (меш, mesh) и добавяне на изкуствено частично трето измерение, което да позволява частично завъртане, усукване.
 1. Размазване на местата с бързи движения за повече реализъм (Motion Blur) - маркиране на края на юмрука, ходилото, коляното и пр. или автоматично откриване по маската. 
 1. Физика - "rag doll" и пр. - така че силата, мястото на ударите, момента и др. да указват влияние върху позицията на героя - да го избутват, усукват и пр., и взаимодействието да не бъде еднообразно налагане на картинката на нападащия върху получаващия ударите.
1. Публика на някои арени и други герои с лица, породени чрез _GAN_ и може би раздвижени чрез _"Deep Fake"_: актьор изпълнява ролята им, след това изпълнението му се нанася върху синтезираните образи. Други участващи технологии: <a href="https://www.google.com/search?client=firefox-b-d&sxsrf=ALeKk03gWyNpIgDRMzIpfJroy2GL9ygP2g%3A1605545546066&ei=Sq6yX5XIA7mbjLsP87ifkAM&q=%22Facial+Landmarks%22+Dlib+C%2B%2B&oq=%22Facial+Landmarks%22+Dlib+C%2B%2B&gs_lcp=CgZwc3ktYWIQAzIGCAAQFhAeOgUIABDLAToICAAQFhAKEB5QvP4CWLKEA2CZhgNoAHAAeACAAboBiAH7BZIBAzAuNZgBAKABAaoBB2d3cy13aXrAAQE&sclient=psy-ab&ved=0ahUKEwiVlcafw4ftAhW5DWMBHXPcBzIQ4dUDCAw&uact=5">_"Facial Landmarks"_</a> напр. чрез библиотеката <a href="https://www.pyimagesearch.com/2017/04/03/facial-landmarks-dlib-opencv-python/">_Dlib_</a>:
1. Автоматични герои, NPC (Non-Playbale Characters), които имат реплики - чрез готови, записани актьорски изпълнения, както и чрез пораждане на текст и синтез на реч (Natural Language Generation, Text To Speech Synthesis). Технологии: _GPT?_ или др. по-прости (пораждане на текст), синтезаторът _"Тошко 2"_ с подобрение или други, и невронни синтезатори? като:  ако могат да се внедрят практически (или чрез сървър, към който да се свързва клиентското игрово приложение?).

## Допълнителни идеи за геймплея и особености:

1. Финтове - играчите да могат да настройват положението си наляво-надясно, така понякога да избягват удар, но също и да пропускат да уцелят.
1. Преминаване между различните арени, взимане на кръв (не само да намалява)<br>
  1. Начини за зареждане на кръвта:
    1. Целуване на момиче/момче от публиката/гостите, но да има определен начин, в определени случаи момичето също да започва да се бие - удря коляно, залепва плесница; идва гаджето й и се включва в боя.
    1. Поръчка на питие.
1. Влизане в битката на трети (или дори четвърт) герой, играч или компютърен герой (NPC)<br>
  1. Новият герой да пречи на биещите се или да започва да се бие с тях, като поводът за влизане да бъде според арената - ако е до бара в "Кулдаун" - отива да си вземе игра; ако е на центъра или на тепе, може да е агент от общинска охрана: "Какво се биете тука бе!" и пр. Някъде може котки да нападат или пък да трябва да се галят.<br>
1. Възможен равен резултат?
1. Героите или някои от тях имат домакински арени. Например за Нууб Сайбот и Смъртобот - "Кулдаун" и Джендем тепе ("адския" хълм). За Контра - "Хакафе". За фрийрънъри - характерни места, на които тренират, "рейлове", Небет тепе. За лостаджии - лостове; за Тоши/Ли - на тепе/навън и пр.

<a name="geroi">
# Герои

## Нууб Сайбот и Смъртобот

![image](/geroi/Noob_Smurtobot_1600.jpg)
![image](/geroi/Smurtobot_x600.jpg)

## Тоши, Ли, Българска нинджа

Гол до кръста, релефни мускули. Два образа: Ли - китаец, Тоши - японец. 
Ли - "Брус Ли", кунг фу, писъци, реплики на китайски.
Тоши - японец, японски реплики; каратист, кариока/лента на челото, колан
+ Смислено е някой от героите да бъде "Българската нинджа" (подобно на "Американската нинджа" Майкъл Дудиков) - може би вместо китаеца или японеца, или пък същия (подобен) образ, но говорещ на български и с някой български удари като ръченица и чапраз. :)

![image](/geroi/Leex327.jpg)

## Контра / Емил Юнаков

![image](/geroi/contra1.jpg)

Военна униформа/зелени дрехи, шапка ("фуражка"), значки-ордени с игри, тениска с игри, черни очила, оръжия - контролери от видеоигри. Хакер и геймър. Живее в хакерспейс. Виж видеоклипа "Контра в Хакафе" и проекта "Затворник в хакерпейса" (още е скрит). 

## Страйкър
Синьо-бяла тениска/сини дрехи, полицейска палка, пистолет, шапка с козирка [работно име]
![image](/geroi/Striker700.jpg)

## Стоичко Христов (?)

Футболист - ритници, "магии" с футболна топка, финтове, удари с ляв крак

# Търсят се още герои

## Жени
Съблазнителни, фатални - М.А.?; миловидни - Червената шапчица? Д.? ... Спортистки?

## Червената шапчица
![image](/geroi/red600.jpg)

Особености: кошница, от която хвърля яйца? Съблазнява - привлича, приканва с пръст, - целува и хапе за врата? (като вампир)? Лицето й се превръща на вълче (или куче?) и тогава хапе - чрез Дийпфейк или кадри, извлечени от приложения тип "Снапчат" и наложени върху триизмерен обект?

## Здравеняк
Мускулест, големи ръце, гол до кръста или с потник; ~ стила на Джакс и др. К.?

## Фрийрънъри
Бързи, акробатични движения, скокове, стъпване на стена: мъж, жена. В.Л.?

## Лостаджии

## Капоейрa 
Движения от капоейра, премятания, танцова стъпка.

## Каратист

## Каубой/Кунг Лао
Каубойска шапка [работно име], револвер

## Скорпион?

## Други ...

# Предложения за места за снимки на арените<br>
## CoolDown
* Преддверието на входа
* Преддверието на долния етаж до релефите
* Барът за игри
* Основната зала, малката стая 

## Хакафе
* Помещенията на ул. "Опълченска"</b> по стари кадри и снимки, виж напр. косплей филмчето "Контра в Хакафе": https://youtu.be/IIGxYJXPeWw и др. непубликувани кадри.

## Навън
* Небет тепе - гледка към другите хълмове
* Парапети на Джендем тепе и на върха
* Върха на Альоша до паметника
* Пред паметника на Мильо и по Главната
* Джумаята
* Антични руини
* Братската могила 
* Гребната база ... 
* Котешки леговища (котки за фон, смалени герои?) ... 
* Из Джендема или Бунарджика 
* Сахат тепе/гледка към Пловдив
* Лостове, спортни площадки

## Други
 
## Снимки
Тош<br>
Елеонора: "изпушилия" Смъртобот; (ретуш: Тош)<br>

## Модели
Тош, Ал (Нууб), Деси

## Автор
Тош
