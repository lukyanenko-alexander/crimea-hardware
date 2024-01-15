## Требования к выгрузке

#### Свойства товаров:
* ID товара (Артикул?)
* Артикул (если он отличен от id, чтобы найти картинку)
* Название товара
* ID категории
* Описание
* Цена
* Мера (шт, мл, г)
* Количество (2 <шт>, 500 <мл или г>) меру в скобка передавать не нужно, передавать только число, написано для примера 


#### Свойства категорий:
Если категории могут быть вложенными, то:
* ID категори
* Название
* ID родительской категории

Если вложенности в категориях не требуется, то можно вместо id категории в фалйе с товаром передавать название категории этого товара, а сам файл с категориями не выгружать.
Клиентские приложения КЕ поддерживают только два уровня вложенности

#### Остатки:
* ID товара (Артикул?)
* Количество

#### Итого
На сервер N должно быть выгружено 2 или 3 файла, в зависимотси от вложенности категорий, по каждой точке, которую необходимо импортировать.
в названии файла должен быть id точки из вашей системы, например:

* <id точки>_services.xml
* <id точки>_categories.xml
* <id точки>_stocks.xml

Также на сервер N в папку N должны быть выгружены файлы картинок. Название файла с изображением должно содержать артикул или id товара из файла <id точки>_services.xml,
также в название картинки добавить какой нибудь хэш или версию (1, 2, 3), необходимо в случае, если само изображение изменится, так система поймет, что нужно обновить картинку в карточке товара. Пример именования:
* <id товара>_<hash>.jpeg
* <Артикул>_<version>.jpeg
