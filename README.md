[Русский](#русский) | [English](#english)

---


[![Latest Stable Version](https://img.shields.io/packagist/v/rosgear/rg-wd-articles.svg)](https://packagist.org/packages/rosgear/rg-wd-articles)
[![Total Downloads](https://img.shields.io/packagist/dt/rosgear/rg-wd-articles.svg)](https://packagist.org/packages/rosgear/rg-wd-articles)
[![Author](https://img.shields.io/badge/author-anton.tivonenko@gmail.com-blue.svg)](mailto:anton.tivonenko@gmail)
[![Source Code](https://img.shields.io/badge/source-rosgear/rg--wd--articles-blue.svg)](https://github.com/rosgear/rg-wd-articles)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](https://github.com/rosgear/rg-wd-articles/blob/main/LICENSE)
![Component type: widget](https://img.shields.io/badge/component%20type-widget-green.svg)
![Component ID: rg-wd-articles](https://img.shields.io/badge/component%20id-rg.wd.articles-green.svg)
![php 8.2+](https://img.shields.io/badge/php-min%208.2-red.svg)

<a name="русский"></a>
## <img src="https://raw.githubusercontent.com/rosgear/rg-wd-articles/refs/heads/main/assets/images/icon.svg" width="64px" height="64px" align="absmiddle"> Виджет «Список материалов»

Виджет предназначен для формирования и вывода списка материалов (статей) из базы данных с учётом заданных параметров фильтрации и сортировки.

### Пример применения
#### с менеджером виджетов:
```
$list = Ge::$app->widgets->get('rg.wd.articles',  ['sort' => 'date', limit' => 10]);
$list->run();
```
#### в шаблоне:
```
$this->widget('rg.wd.articles', [
    'mode'       => 'list',
    'sort'       => ['default' => 'date,a'],
    'pagination' => ['defaultLimit' => 20],
    'itemsView'  => '/blog/blog-items',
    'pager'      => [
        'itemTpl'       => '<li>{link}</li>',
        'activeItemTpl' => '<li class="active">{link}</li>',
        'options'       => ['class' => 'justify-content-center']
    ]
]);
```
#### с namespace:
```
use Rg\Widget\Articles\Widget as List;
echo List::widget(['mode' => 'list', pagination' => ['limit' => 20]]);
```
если namespace ранее не добавлен в PSR, необходимо выполнить:
```
Ge::$loader->addPsr4('Rg\Widget\Articles\\', Ge::$app->modulePath . '/rg/rg.wd.articles/src');
```

### Установка

Для добавления виджета в ваш проект, вы можете просто выполнить команду ниже:

```
$ composer require rosgear/rg-wd-articles
```

или добавить в файл composer.json вашего проекта:
```
"require": {
    "rosgear/rg-wd-articles": "*"
}
```
или скачать архив на [странице виджета](https://rosgear.ru/component/rg-wd-articles/) в каталоге приложений RosGear.

После добавления виджета в проект выполните его установку в редакцию веб‑приложения с помощью Панели управления GePanel.

<a name="english"></a>
## <img src="https://raw.githubusercontent.com/rosgear/rg-wd-articles/refs/heads/main/assets/images/icon.svg" width="64px" height="64px" align="absmiddle"> Widget «List of articles»

The widget is designed to generate and display a list of materials (articles) from the database, taking into account the specified filtering and sorting parameters.

### Installation

To add the widget to your project, you can simply run the command below:

```
$ composer require rosgear/rg-wd-articles
```

or add to your project's composer.json file:
```
"require": {
    "rosgear/rg-wd-articles": "*"
}
```
or download the archive from the [widget page](https://rosgear.ru/component/rg-wd-articles/) in the RosGear application catalog.

After adding the widget to the project, install it into the web application edition using the GePanel Control Panel.