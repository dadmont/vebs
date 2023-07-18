<h1 align="center"> МИНИСТЕРСТВО НАУКИ И ВЫСШЕГО ОБРАЗОВАНИЯ РОССИЙСКОЙ ФЕДЕРАЦИИ ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ БЮДЖЕТНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ ВЫСШЕГО ОБРАЗОВАНИЯ «САХАЛИНСКИЙ ГОСУДАРСТВЕННЫЙ УНИВЕРСИТЕТ»</h1>

<p align="center">Лабораторная работа №13 <br> "PHP" </p>

<p align="right">Выполнил: Шевцов В. С.</p>


<p align="center">г. Южно-Сахалинск <br> 2023 год</p>

<h2 align="center">Введение</h2>
<p align="justify">Работа с формами через PHP.</p>

<h2 align="center">Цели и задачи</h2>

1.	Спросите город пользователя с помощью формы. Результат запишите в переменную `$city`. Выведите на экран фразу 'Ваш город: %Город%'.
2.	Решите предыдущую задачу так, чтобы пользователь не мог вводить теги и сломать сайт.
3.	Сделайте так, чтобы форма после отправки скрывалась.
4.	Спросите имя пользователя с помощью формы. Результат запишите в переменную `$name`. Выведите на экран фразу 'Привет, %Имя%'.
5.	Спросите у пользователя имя, возраст, а также попросите его ввести сообщение (его сделайте в textarea). Выведите эти данные на экран в формате, приведенном под данной задачей. Позаботьтесь о том, чтобы пользователь не мог вводить теги (просто удаляйте их) и таким образом сломать сайт.
6.	Спросите возраст пользователя. Если форма была отправлена и введен возраст, то выведите его на экран, а форму уберите. Если же форма не была отправлена (это будет при первом заходе на страницу) - просто покажите ее.
7.	Спросите у пользователя логин и пароль (в браузере должен быть звездочками). Сравните их с логином `$login` и паролем `$pass`, хранящихся в файле. Если все верно - выведите 'Доступ разрешен!', в противном случае - 'Доступ запрещен!'. Сделайте так, чтобы скрипт обрезал концевые пробелы в строках, которые ввел пользователь.
8.	Спросите имя пользователя с помощью формы. Результат запишите в переменную `$name`. Сделайте так, чтобы после отправки формы значения ее полей не пропадали.
9.	Спросите у пользователя имя, а также попросите его ввести сообщение (textarea). Сделайте так, чтобы после отправки формы значения его полей не пропадали.
10.	Дана строка 'ahb acb aeb aeeb adcb axeb'. Напишите регулярку, которая найдет строки ahb, acb, aeb по шаблону: буква 'a', любой символ, буква 'b'.
11.	Дана строка 'aba aca aea abba adca abea'. Напишите регулярку, которая найдет строки abba adca abea по шаблону: буква 'a', 2 любых символа, буква 'a'.
12.	Дана строка 'aba aca aea abba adca abea'. Напишите регулярку, которая найдет строки abba и abea, не захватив adca. 
13. Дана строка 'aa aba abba abbba abca abea'. Напишите регулярку, которая найдет строки aba, abba, abbba по шаблону: буква 'a', буква 'b' любое количество раз, буква 'a'. 
14.	 Дана строка 'aa aba abba abbba abca abea'. Напишите регулярку, которая найдет строки aa, aba, abba, abbba по шаблону: буква 'a', буква 'b' любое количество раз (в том числе ниодного раза), буква 'a'. 
15.	 Дана строка 'aa aba abba abbba abca abea'. Напишите регулярку, которая найдет строки aa, aba по шаблону: буква 'a', буква 'b' один раз или ниодного, буква 'a'. 
16.	Дана строка 'ab abab abab abababab abea'. Напишите регулярку, которая найдет строки по шаблону: строка 'ab' повторяется 1 или более раз. 
17.	Дана строка 'a.a aba aea'. Напишите регулярку, которая найдет строку a.a, не захватив остальные. 
18.	 Дана строка '2+3 223 2223'. Напишите регулярку, которая найдет строку 2+3, не захватив остальные. 
19.	 Дана строка '23 2+3 2++3 2+++3 345 567'. Напишите регулярку, которая найдет строки 2+3, 2++3, 2+++3, не захватив остальные (+ может быть любое количество). 
20.	 Дана строка '23 2+3 2++3 2+++3 445 677'. Напишите регулярку, которая найдет строки 23, 2+3, 2++3, 2+++3, не захватив остальные. 
21.	 Дана строка '*+ *q+ *qq+ *qqq+ *qqq qqq+'. Напишите регулярку, которая найдет строки *q+, *qq+, *qqq+, не захватив остальные. 
22.	 Дана строка '*+ *q+ *qq+ *qqq+ *qqq qqq+'. Напишите регулярку, которая найдет строки *+, *q+, *qq+, *qqq+, не захватив остальные. 
23.	Дана строка 'aba accca azzza wwwwa'. Напишите регулярку, которая найдет все строки по краям которых стоят буквы 'a', и заменит каждую из них на '!'. Между буквами a может быть любой символ (кроме a). 

<h2 align="center">Решение задач</h2>

### 1-3. 

```php
<!DOCTYPE HTML>
<html> 
<head>
    <title>1-3</title>
</head> 
<body>


<?php
    if(empty($_POST["city"]))
    {
    ?>
        <form action="" method="POST">
            Город: <input name="city" type="text"> <br>
            <input type="submit">
        </form>
    <?php
    }
?>


<?php
    $city = '';
    if(!empty($_POST["city"]))
    {
        $city = strip_tags($_POST["city"]);
        echo "Ваш город: ".$city;
    }
?>
</body>
</html>
```

### 4-5

```php
<!DOCTYPE HTML>
<html> 
<head>
    <title>4-5</title>
</head> 
<body>

<form action="" method="post">
    <p>Имя: <input type="text" name = "name"></p>
    <p>Возраст: <input type="text" name = "age"></p>
    <p>Сообщение: <textarea name = "message" ></textarea></p>
    <p><input type="submit" ></p>
</form>


<?php
    if(!empty($_POST["name"]) && !empty($_POST["age"]))
    { ?>
       <p> Ваше имя <?php echo strip_tags($_POST["name"]); ?></p>
       <p> Ваш возраст <?php echo strip_tags($_POST["age"]); ?></p>
       <p> Ваще сообщение <?php echo strip_tags($_POST["message"]); ?></p>
    <?php
    }
?>
</body>
</html>
```

### 6

```php
<!DOCTYPE HTML>
<html> 
<head>
    <title>6</title>
</head> 
<body>

<?php
    if(empty($_POST["age"]))
    {
    ?>
        <form action="" method="POST">
            <p>Возраст: <input name="age" type="text"></p>
            <input type="submit">
        </form>
    <?php
    }
?>

<?php
    if(!empty($_POST["age"]))
    {
        echo "Ваш возраст: ". strip_tags($_POST["age"]);
    }
?>
</body>
</html>
```

### 7

```php
<!DOCTYPE HTML>
<html> 
<head>
    <title>7</title>
</head> 
<body>

<form action="" method="post">
    <p>Логин <input type="text" name = "login"></p>
    <p>Пароль <input type="password" name = "pass"></p>
    <input type="submit">
</form>

<?php
    $LOGIN = "admin";
    $PASS = "durak";

    if(!empty($_POST["login"]))
    {
        $inputLogin = trim(strip_tags($_POST["login"]));
        $inputPass = trim(strip_tags($_POST["pass"]));
        if($LOGIN == $inputLogin && $PASS == $inputPass)
        {
            echo "Доступ разрешен.";
        } else {
            echo "Доступ запрещен.";
        }
    }
?>

</body>
</html>
```

### 8

```php
<!DOCTYPE HTML>
<html> 
<head>
    <title>8</title>
</head> 
<body>

<form action="" method="post">
    <p>Имя <input type="text" name = "name" value="<?php
        if(!empty($_POST['name'])) echo $_POST['name']; ?>"></p>
    <input type="submit">
</form>
<?php
    if(!empty($_POST["name"]))
        echo "Ваше имя ".$_POST["name"];
?>
</body>
</html>
```

### 9

```php
<!DOCTYPE HTML>
<html> 
<head>
    <title>9</title>
</head> 
<body>

<form action="" method="post">
    <p>Имя <input type="text" name = "name" value="<?php
        if(!empty($_POST[`name`])) echo $_POST[`name`];
    ?>"></p>
    <p><textarea name = "message"><?php 
            if(!empty($_POST['message'])) echo $_POST['message']; 
        ?>
    </textarea></p>
    <input type="submit">
</form>
<?php
    if(!empty($_POST["name"]))
    {
        echo strip_tags($_POST["name"]);
    }
?>
</body>
</html>
```

### 10-23
Задачи 10-23 являются аналогичными по отношению к друг другу. Отличие состоит лишь в регулярных выражениях содержащихся в переменной `$regexp`.

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>10-23</title>
</head>
<body>
    <p>Задание 10</p>
    <?php
        $str = 'ahb acb aeb aeeb adcb axeb';
        $regexp = '/a[a-z]b/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>

    <p>Задание 11</p>
    <?php
        $str = 'aba aca aea abba adca abea';
        $regexp = '/a..a/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>

    <p>Задание 12</p>
    <?php
        $str = 'aba aca aea abba adca abea';
        $regexp = '/a.[^c]a/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>

    <p>Задание 13</p>
    <?php
        $str = 'aa aba abba abbba abca' ;
        $regexp = '/ab+a/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>

    <p>Задание 14</p>
    <?php
        $str = 'aa aba abba abbba abca' ;
        $regexp = '/ab*a/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>

    <p>Задание 15</p>
    <?php
        $str = 'aa aba abba abbba abca abea' ;
        $regexp = '/ab?a/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>
    
    <p>Задание 16</p>
    <?php
        $str = 'ab abab abab abababab abea' ;
        $regexp = '/(ab)+/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>
    
    <p>Задание 17</p>
    <?php
        $str = 'a.a aba aea' ;
        $regexp = '/a\.a/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>
    
    <p>Задание 18</p>
    <?php
        $str = '2+3 223 2223' ;
        $regexp = '/2\+3/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>
    <p>Задание 19</p>
    <?php
        $str = '23 2+3 2++3 2+++3 345 567' ;
        $regexp = '/2\++3/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>
    
    <p>Задание 20</p>
    <?php
        $str = '23 2+3 2++3 2+++3 445 677' ;
        $regexp = '/2\+*3/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>
    <p>Задание 21</p>
    <?php
        $str = '*+ *q+ *qq+ *qqq+ *qqq qqq+' ;
        $regexp = '/\*q*\+/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>
    
    <p>Задание 22</p>
    <?php
        $str = '*+ *q+ *qq+ *qqq+ *qqq qqq+' ;
        $regexp = '/\*q*\+/';
        preg_match_all($regexp, $str, $result);
        print_r($result[0]);
    ?>
    
    <p>Задание 23</p>
    <?php
        $str = 'aba accca azzza wwwwa';
        $regexp = '/a[^a]+a/';
        echo preg_replace($regexp, '!', $str);
    ?>
</body>
</html>
```


<h2 align="center">Вывод</h2>
В этой лабораторной работе я научился работать с формами, узнал, чем отличаются глобальные переменные $_POST и $_GET, а также научился пользоваться регулярными выражениями. 