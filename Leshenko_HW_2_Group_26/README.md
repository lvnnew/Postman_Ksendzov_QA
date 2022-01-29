## HW_2 Postman

`http://162.55.220.72:5005/first`

1. Отправить запрос.

3. Статус код 200
```js
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```

    3. Проверить, что в body приходит правильный string.
```js
pm.test("В ответ получаем верную строку", function () {
    pm.expect(pm.response.text()).to.include("This is the first responce from server!");
});
```

<hr>

`http://162.55.220.72:5005/user_info_3`

1. Отправить запрос.

3. Статус код 200
```js
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```

4. Спарсить response body в json.
```js
let jsonData = pm.response.json();
```

5. Проверить, что name в ответе равно name s request (name вбить руками.)
```js
pm.test("name = Vladimir", function () {
    pm.expect(jsonData.name).to.eql("Vladimir");
});
```
7. Проверить, что age в ответе равно age s request (age вбить руками.)
```js
pm.test("age = 30", function () {
    pm.expect(jsonData.age).to.eql("30");
});
```

9. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
```js
pm.test("salary = 1000", function () {
    pm.expect(jsonData.salary).to.eql(1000);
});
```

11. Спарсить request.
```js
let reqData = request.data;
// создадим переменную salaryInt и присвоим ей преобразованное в int значение reqData.salary 
let salaryInt = +(reqData.salary);
```

13. Проверить, что name в ответе равно name s request (name забрать из request.)
```js
pm.test("Response name = Request name", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```

15. Проверить, что age в ответе равно age s request (age забрать из request.)
```js
pm.test("Response age = Request age", function () {
    pm.expect(jsonData.age).to.eql(reqData.age);
});
```

17. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```js
pm.test("Response salary = Request salary", function () {
    pm.expect(jsonData.salary).to.eql(salaryInt);
});
```

19. Вывести в консоль параметр family из response.
```js
console.log(jsonData.family);
```

21. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```js
salaryInt = salaryInt*4;
pm.test("Response u_salary_1_5_year = salary*4", function () {
    pm.expect(jsonData.family.u_salary_1_5_year).to.eql(salaryInt);
});
```

<hr>

`http://162.55.220.72:5005/object_info_3`

1. Отправить запрос.

3. Статус код 200
```js
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```

3. Спарсить response body в json.
```js
let jsonData = pm.response.json();
```

5. Спарсить request.
```js
let reqData = pm.request.url.query.toObject();
// создадим переменную salaryInt и присвоим ей преобразованное в int значение reqData.salary 
let salaryInt = +(reqData.salary)
```

7. Проверить, что name в ответе равно name s request (name забрать из request.)
```js
pm.test("Response name = Request name", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```

9. Проверить, что age в ответе равно age s request (age забрать из request.)
```js
pm.test("Response age = Request age", function () {
    pm.expect(jsonData.age).to.eql(reqData.age);
});
```

11. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```js
pm.test("Response salary = Request salary", function () {
    pm.expect(jsonData.salary).to.eql(salaryInt);
});
```

13. Вывести в консоль параметр family из response.
```js
console.log(jsonData.family);
```

15. Проверить, что у параметра dog есть параметры name.
```js
pm.test("Dog has a name", function () {
    pm.expect(jsonData.family.pets.dog).to.have.property("name");
});
```

17. Проверить, что у параметра dog есть параметры age.
```js
pm.test("Dog has a age", function () {
    pm.expect(jsonData.family.pets.dog).to.have.property("age");
});
```

19. Проверить, что параметр name имеет значение Luky.
```js
pm.test("Dog name = Luky", function () {
    pm.expect(jsonData.family.pets.dog.name).to.eql("Luky");
});
```

21. Проверить, что параметр age имеет значение 4.
```js
pm.test("Dog age = 4", function () {
    pm.expect(jsonData.family.pets.dog.age).to.eql(4);
});
```

<hr>

`http://162.55.220.72:5005/object_info_4`

1. Отправить запрос.

3. Статус код 200
```js
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```

3. Спарсить response body в json.
```js

```

5. Спарсить request.
```js

```

7. Проверить, что name в ответе равно name s request (name забрать из request.)
```js

```

9. Проверить, что age в ответе равно age из request (age забрать из request.)
```js

```

11. Вывести в консоль параметр salary из request.
```js

```

13. Вывести в консоль параметр salary из response.
```js

```

15. Вывести в консоль 0-й элемент параметра salary из response.
```js

```

17. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
```js

```

19. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
```js

```

21. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```js

```

23. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
```js

```

25. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```js

```

27. Создать в окружении переменную name
```js

```

29. Создать в окружении переменную age
```js

```

31. Создать в окружении переменную salary
```js

```

33. Передать в окружение переменную name
```js

```

35. Передать в окружение переменную age
```js

```

37. Передать в окружение переменную salary
```js

```

39. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```js

```

<hr>

`http://162.55.220.72:5005/user_info_2`

1. Вставить параметр salary из окружения в request

3. Вставить параметр age из окружения в age

5. Вставить параметр name из окружения в name

7. Отправить запрос.

9. Статус код 200
```js
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```

6. Спарсить response body в json.
```js

```

8. Спарсить request.
```js

```

10. Проверить, что json response имеет параметр start_qa_salary
```js

```

12. Проверить, что json response имеет параметр qa_salary_after_6_months
```js

```

14. Проверить, что json response имеет параметр qa_salary_after_12_months
```js

```

16. Проверить, что json response имеет параметр qa_salary_after_1.5_year
```js

```

18. Проверить, что json response имеет параметр qa_salary_after_3.5_years
```js

```

20. Проверить, что json response имеет параметр person
```js

```

22. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
```js

```

24. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
```js

```

26. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
```js

```

28. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
```js

```

30. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
```js

```

32. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
```js

```

34. Проверить, что что параметр u_age равен age из request (age забрать из request.)
```js

```

36. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
```js

```

38. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
```js

```

