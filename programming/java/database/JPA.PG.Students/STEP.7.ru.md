## Имплементирование на уровне JPA используя Hibernate ORM

> Работа в JPA с набором аннотаций @Embeddable / @Embedded 

### Четвертая ЧАСТЬ

* При необходимости включить (вложить) объект одной сущности в  объект другой ( используя композицию ) в JPA можно пользоваться "связями" типа **embeddable**. При этом и та и другая сущность хранятся в одной и той же таблице по умолчанию. При этом встраиваемый объект не может быть использован сам по себе, он бессмысленный без того объекта которому принадлежит. 

* Представим себе что от нас требуется "апдейтить" структуру сущности **Student** добавив в нее связь с сущностью типа успеваемость - **Performance**. Каждый студент будет иметь личную уникальную копию успеваемости - потому мы ее не можем объявить как независимую часть. Чтобы было понятно - если студента удалили из ДБ - нет смысла оставлять информацию об его успеваемости. 

* Добавляем новый класс в **entities**
  ```java
   @Embeddable
   public class Performance {

      public static enum Behaviour {
         EXCELLENT
         GOOD,
         AVERAGE,
         BAD,
         WORST
      }

      private float averageMark;
      private int hoursOfTheory;
      private int hoursOfPractice;
      // ??? - annotation missing
      private Behaviour behaviour;
   }
  ``` 
  Обратите внимание на аннотацию которая дает понять о том что это встраиваемая сущность **@Embeddable**, так же обратите внимание на вложенный статичный класс перечисляющий уровни "поведения".

  ВОПРОС - чему будет равняться  Behaviour.AVERAGE ?

  Каждая сущность **Performance** состоит из:
   - averageMark - средней оценики
   - hoursOfTheory - кол-во часов теории которую посетил ученик
   - hoursOfPractice - кол-во часов практики которую прошел ученик
   - behaviour - уровень поведения в школе
  
* Добавить конструкторы и сет/гет + в стриг - методы
* ВНИМАНИЕ! над полем **behaviour** для того чтобы JPA принял такой тип поля необходимо добавить аннотацию - какую?

* Возвращаемся в класс сущности студента и добавляем такую строку / поле 
  ``` java

  ...
  @Embedded
  private Performance performance;
  ... 

  ```
  как вы видите мы добавляем связь в новой сущностью. Обратите внимание на аннотацию **@Embedded** что говорит о том что это поле встроенно.

* Дайте JPA обновить структуру таблиц.
* Проверить что произошло со структурой таблицы студентов.
* Произведите CRUD со студентом учитывая его новое поле!
