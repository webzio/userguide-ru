# Автозагрузка

Kohana предоставляет нам преимущества [автозагрузки](http://php.net/manual/language.oop5.autoload.php) в PHP. Благодаря этому, можем забыть о таких функциях, как [include](http://php.net/include) или [require](http://php.net/require).

Автозагрузка классов осуществляется с помощью метода [Kohana::auto_load], который просто преобразовывает имя  класса в имя файла:

1. Классы располагаются в категории `classes/` в [файловой системе](about.filesystem) фреймворка
2. Все нижние подчёркивания в имени класса заменяются на слеши
2. Имя файла пишется в нижнем регистре

При вызове ещё не подгружённого класса (например, `Session_Cookie`), Kohana будет искать с помощью [Kohana::find_file] файл `classes/session/cookie.php`.

## Установка автозагрузки классов

Автозагрузка системных классов устанавливается в `application/bootstrap.php`.

Автозагрузка дополнительных классов может быть установлена с помощью [spl_autoload_register](http://php.net/spl_autoload_register).
