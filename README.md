# Курсовой проект «Игра LeaveMeAlone»

Курсовой проект — компьютерная 3D игра на движке Unreal Engine. 

## Содержание

### 1. Условия:
Игра состоит из двух уровней:
1) На первом уровне игрока атакует только один тип противников.
   * Время игровой сессии на первом уровне составляет 5 мин.
2) На втором уровне игрока атакуют два типа противников.
   * Один – это противники, аналогичные неигровым персонажам первого уровня.
   * Второй – новые противники, имеющие показатель здоровье Х1.5 от показателей здоровья первых противников.
   * Также новые противники имеют больший базовый урон, базовую скорость и скорость атаки, относительно первых противников.
   * Время игровой сессии на первом уровне составляет 5 мин.

### 2. Управление:
* Герой всегда повёрнут в сторону курсора.
* Передвижение на уровне происходит при помощи WASD.
* При нажатии L Shift игрок выполняет ускорение на ограниченную дистанцию, равную количеству потраченной выносливости. После спринта необходимо время для восстановления показателей выносливости для повторного бега. По время спринта игрок не может стрелять или перезаряжать оружие.
* При клике на ПКМ — стреляет. 

#### Начало игры. 
Появляется меню, в нём 2 активных кнопки — начать игру или выйти из неё.</br>
А также дополнительный информационный пользовательский виджет – рекорд очков в игре на текущий момент.

#### Процесс игры.
Игра с видом сверху (вы можете сделать небольшой наклон камеры). На игровом поле в центре появляется герой.  
Интерфейс: отображает количество времени сессии, набранных очков, здоровья игрока и зарядов. 

Стрельба: Персонаж может стрелять как одиночными выстрелами, так и очередью. У игрока ограниченное количество патронов в обойме (25-30 шт.) и не ограниченное количество обойм. При окончании патронов в магазине происходит анимация автоматической перезарядки, во время которой игрок не может стрелять. При нажать кнопки R происходит принудительная перезарядка. Если у игрока полный магазин, перезарядка не производится.

За	пределами	экрана	через	определенные промежутки времени создаются противники из точек спауна. При этом:
* Противники появляются с прогрессией сложности. Сначала одна волна, затем две, затем три и т.д.
* При появлении, неигровые персонажи движутся в сторону игрока и при сближении атакуют противника (действуют по задачам, описанным в дереве поведения).
* После попадания противником по игроку, показатели жизней игрока понижаются и изменения отображаются в HealthBar.
* У противников имеются жизненные показатели, отражаемые в виджет HealthBar.
* После попадания игроком по противнику, показатели жизней понижаются и изменения отображаются в HealthBar.
* Противники находятся на игровом поле до момента смерти.
* Игрок не должен иметь возможности пройти к точкам спауна неигровых персонажей.

При окончании игровой сессии первого уровня - все противники, оставшиеся в живых, исчезают, без начисления дополнительных очков игроку. Запускается виджет таймера, сигнализирующий о переходе на новый уровень. При переходе на новый уровень - очки первого уровня сохраняются в соответствующем виджете. Камера и спаун противников, происходят по законам описанным выше. 

При окончании игровой сессии второго уровня - появляется пользовательский интерфейс - Time Over и предложение сыграть снова или перейти в главное меню. А также информационный виджет, сколько игрок набрал очков в текущей игровой сессии. Если количество очков превышает текущий рекорд, то результат рекорда в главном меню должен быть перезаписан новыми значениями. После подтверждения повторной попытки игра запускается на первом уровне.

При проигрыше - смерти игрока, появляется пользовательский интерфейс - Game Over и предложение сыграть снова или перейти в главное меню. А также информационный виджет, сколько игрок набрал очков в текущей игровой сессии. Если количество очков превышает текущий рекорд, то результат рекорда в главном меню должен быть перезаписан новыми значениями. После подтверждения повторной попытки игра запускается на первом уровне.

При вызове меню паузы – игра ставится на паузу,  появляется пользовательский интерфейс - Pause и предложение – вернуться в игру текущей сессии, сыграть снова или перейти в главное меню.

#### Новые механики, которые необходимо реализовать:
* Добавьте эффект screen shake — драматическую тряску камеры при понижении жизней игрока до критических значение (5-10% от максимального количества здоровья).
* Реализуйте рандомный спаун пикапа здоровья. Раз в минуту должен появляться один пикап здоровья, локация спауна должна происходить в одном из углов игрового поля. После появления, в случае, если игрок его не успел подобрать, пикап автоматически исчезает через 10 секунд.
* Второй уровень игры должен иметь минимально – незначительные графические отличия от первого уровня.
* Новый тип противника, появляющийся на втором уровне должен иметь минимально – цветовые отличия от старого типа противников.

### Технические требования
* Игра должна запускаться на платформе Windows или Mac в полноэкранном режиме.
* Размеры героя и противников примерно одинаковы.
* Код С++ должен быть чистый и читабельный, декомпозирован и инкапсулирован, а также иметь логические комментарии.
* Код Blueprints не должен иметь запутанных контактов, а также иметь логические комментарии.
* Взаимодействие между классами должно быть реализовано по принципам Gameplay Framework.

______

### Куда и как отправлять готовое задание
* После окончания работы над проектом, соберите его билд.
* Заархивируйте файлы проекта и билд в одну архивную директорию.
* Проект готового решения (архив проекта и билда) необходимо выложить в открытый доступ на облачный диск
* В личном кабинете прикрепите ссылку на проект готового решения.

Успехов в выполнении задания!
