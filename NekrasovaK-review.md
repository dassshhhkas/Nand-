##  Игровой опыт 

* Игра запускается и в приложении и на сайте, плюс для лучшего опыта использования прилагается понятное, подробное объяснение и запуска самой игры, и используемых клавиш. 
* Возможно, стоило использовать общепринятые клавиши WASD для движения и E для стрельбы, поскольку находжение этих кнопок рядом делает игровой процесс легче и быстрее, но это вкусовщина. Сами клавиши не мешают игровому процессу после адаптации, да и указаны в правилах, как было отмечено выше.
* Игра с одной стороны хороша тем, что по сути бесконечна (играешь, пока не умираешь от столкновения), но можно было бы рассмотреть систему с несколькими уровнями, где для прохождения надо набрать определенное количество очков и на следующих менять либо темп игры/либо карту/либо добавлять усложения. В рамках бесконечного формата игры было бы приятно добавить не только текущий счет, но и лучший среди игр на экране запуска, потому что добавляется соревновательный элемент

Из некоторых ошибок:
* пули из прошлой игры, остаются, если достаточно быстро нажать перезапуск и бывает, что если пуль много, то они начинают самопроизвольно дублироваться на экране
* нельзя запускать пули во время движения, что несколько мешает процессу, потому что "противники" перемещаются достаточно быстро и иногда рандомно возникают уже близко к концу экрана.
* кнопка перезапуска игры R, но только большая и только на английской раскладке, что... (возможно особенность языка), но так как она нигде не указана, то вызывает недоумение, почему при либо нажатии клавиши R без шифта, либо на русской раскладке клавиатуры, ничего не происходит
* экран перезагрузки смещен влево относительно центра, никак игре не мешает, но визуально портит кадр
* на начальном экране отрисовывается "чтовы начать" вместо "чтобы начать"
* ошибка в прорисовке счета, десятки в позиции правее единиц

## Комментарии по коду
Хорошие детали:
* В целом хорошо организован код, понятен для понимания за счет большого количества комментариев и осмысленных названий файлов.
* Функция рандома хорошо работает, хотя и заметен паттерн прорисовки кораблей попеременно в левой, потом в правой части экрана.
Не очень хорошие детали:
* По коду видно, что существует система уровней, но сама механика и заданные временные промежутки, не позволяют убить всех пришельцев одновременно, чтобы их не осталось на поле
* Файлы Game и MainMenu идентичны кроме задаваемого размера букв в DrawGameOver, поэтому в целом непонятно наличие их двух и что из них конкретно используется
* возможно отрисовку цифр и букв можно было выделить в отдельный файл, поскольку они синтаксически достаточно похожи между собой
* Файл MainGame разбит на методы, но они включают в себя как игровой процесс, так и отрисовку дополнительной страницы (перезагрузки), которую по смыслу можно и убрать в другой файл. 
Вкусовщина:
* Из-за механики можно зажимать клавиши лево/право для движения и они будут работать, но если зажать пробел, то пули не будут выпускаться "постоянно", потому что пуля отрисовывается после каждого нажатия. НУ не ошибка, но хотелось бы стрелять очередью
* Искусственное ограничение на 10 пуль на экране мешает, если пытаешься стрелять постоянно, так как создает slow down, но в маштабах игры не особо критично, если не пытаться провернуть это специально 
