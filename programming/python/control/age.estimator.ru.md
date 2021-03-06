# Управление

> **if/else** представляет собой одну из конструкций (структур), используемых для контроля выполнения в зависимости от определенных условий

* Если нам нужно протестировать одно условие, в котором будет выполняться код, то чаще всего используется формула:
    ```python
    if condition:
        code_to_execute
    ```

* Если мы должны проверить одно условие, в котором будет выполняться код, а в противном случае другой код:
    ```python
    if condition:
        code_to_execute
    else:
        code_to_execute    
    ```

* Если нам нужно проверить некоторые вставленные условия, которые являются взаимоисключающими, мы можем прибегнуть к формуле:
 
    ```python
    if condition1:
        code_to_execute
    elif condition2:
        code_to_execute    
    elif condition3:
        code_to_execute    
    ...    
    elif conditionn:
        code_to_execute    
    else:
        code_to_execute    
    ```
---

* Написать программу, которая считывает с клавиатуры год рождения человека, указанный в 4-х цифрах (напр - 1990), и выполняет следующее:
  1.  Убедитесь, что введенное значение соответствует требуемому диапазону (допускаются только значения, начинающиеся с 1900 года и заканчивающиеся текущим годом). Если значение выходит за пределы диапазона - появляется сообщение об ошибке, в противном случае мы продолжаем с пункта 2
  2.  Вычисляет возраст в годах и выводит
  3.  Оцениваем возраст словами и отображает сообщение о возрасте например таким образом (в соответствие с диапазоном лет):
      1.  1-3 года - "baby"
      2.  4-9 лет - "kid"
      3.  10-15 лет - "teen"
      4.  16-18 лет - "young" 
      5.  19-50 лет - "adult"
      6.  51+   лет - "old"     