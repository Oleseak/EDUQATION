  *Классы позволяют «структурировать» объекты и группировать их по категориям. Многие современные фреймворки (React, Angular, Vue, ...) создают визуальные компоненты на основе классов*

| * объявление классов: **class Name***
| * инициализация свойств: **constructor()**, **new Name()***
| * поиск в DOM : **document.getElementById()***

---

В этом примере вы должны объявить класс с именем «Button», который позволяет создавать компоненты типа кнопки со следующими свойствами:
    * text (String) - текст, который появляется на кнопке
    * type (String) - тип кнопки, возможны только значения "success", "warning", "disabled", "danger", "default", используя условное вырожение, убедитесь в том что только возможные значения попадают в "type"
    * action (Function) - функция (callback), которая будет выполняться при нажатии кнопки
Класс также должен содержать несколько методов:
    * render( parrent_id ) - отображает HTML-представление этой кнопки ВНУТРИ элемента, идентифицируемого как "parrent_id"



## На основе фрагмента «script» в [index](./index.html) выполнить следующие пункты:
1. Заполните все места, отмеченные ** // ??? ** в классе и за его пределами, чтобы код соответствовал требованиям, изложенным выше.
2. Завершите сценарий кодом, который выполнит следующие действия:
    * создаст 2 кнопки «ОК» и «ОТМЕНА» внутри формы в «div» с id = «actions»
    * при нажатии на кнопку «ОК» скрипт должен выполнить функцию «okAction()»
    * при нажатии на кнопку «ОТМЕНА» скрипт должен выполнить функцию «cancelAction()»
    * Представление кнопок также должно соответствовать изображению [result](./result.png)