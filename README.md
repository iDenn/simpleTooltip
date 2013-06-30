simpleTooltip
=============

**simpleTooltip** - аналог или lite-вариант [Tipsy Tooltip](https://github.com/jaz303/tipsy).

Большая часть реализована на чистом CSS, но контролером выступает небольшой jQuery плагин.

Название
-------
Почему **simpleTooltip**?
- всего 3 Кб исчерпывающего кода;
- работа во всех браузерах;
- простота в использовании;
- компактный и гармоничный внешний вид;
- простые текстовые подскаки без доп. функционала.

Думается мне, эти пункты вполне раскрывают основную идею разработки - простоту.

Использование
-------
Использование подсказок возможно на любом HTML элементе. Для этого необходимо присвоить ему пару атрибутов: 
*data-tooltip* и *title*. Значением первого может быть одно из предопределенных слов и влияет оно на позиционирование 
подсказки относительно элемента которому она дана. Контекст второго атрибута - текст подсказки без какого-либо 
форматирования (text/plain).

Возможные значения для атрибута **data-tooltip** и их влияние на смещение:
- **nw** - северо-западное;
- **north** - северное;
- **ne** - северо-восточное;
- **west** - западное;
- **east** - восточное;
- **sw** - юго-западное;
- **south** - южное;
- **se** - юго-восточное.

Помимо этих опций есть возможность указать максимальную ширину подсказки в пикселях. Для этого, в файле 
**simpleTooltip.js**, функции-обработчику неообходимо присвоить числовой аргумент, например:

```
$.simpleTooltip(400); // теперь макс. ширина тултипа равна 400px.
```

Зачем JavaScript?
-------
Функции jQuery плагина не многочислены. Изначально он проверяет позиционирование всех элементов которым установлена
подсказка - оно не должно быть статическим. По-этому, все несоответствующие элементы стают относительными.

Далее, при наведении мыши на элемент с подсказкой, расчитывается его ширина и, если она не привышает максимальную и
смещение не направлено на юг или север, работа плагина прекращается. В противных случаях работа будет продолжена 
еще на одно или два действия:
- ширина больше максимальной - тултип получает ширину со значением максимальной и особое форматирование текста.
- южное или северное направление - подсказка выравнивается по центру элемента которому она присвоена.

Кроссбраузерность
-------
- IE9+
- Chrome 2.0+
- Opera 9.0+
- Safari 3.1+
- Firefox 1.0+
- Android 1.0+
- iOS 1.0+

Changelog
-------
**Версия [1.0](https://github.com/BR0kEN-/simpleTooltip/tree/v1.0)**:
- дебютная версия с поддержкой IE8.

**Версия [1.0.1](https://github.com/BR0kEN-/simpleTooltip/tree/v1.0.1)**:
- убрана поддержка IE8;
- проведен рефакторинг кода;
- добавлены минифицированные CSS и JS;
- отказ от атрибута *data-title* в пользу более семантичного *title*;

Демонстрация
-------
http://firstvector.org/simpleTooltip
