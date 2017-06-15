# Yii2-morpher

Installation
------------

[![Latest Stable Version](https://poser.pugx.org/slawap/yii2-morpher/version)](https://packagist.org/packages/slawap/yii2-morpher)
[![Total Downloads](https://poser.pugx.org/slawap/yii2-morpher/downloads)](https://packagist.org/packages/slawap/yii2-morpher)
[![Latest Unstable Version](https://poser.pugx.org/slawap/yii2-morpher/v/unstable)](//packagist.org/packages/slawap/yii2-morpher)
[![License](https://poser.pugx.org/slawap/yii2-morpher/license)](https://packagist.org/packages/slawap/yii2-morpher)
[![composer.lock available](https://poser.pugx.org/slawap/yii2-morpher/composerlock)](https://packagist.org/packages/slawap/yii2-morpher)

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
composer require --prefer-dist slawap/yii2-morpher
```

or add

```json
"slawap/yii2-morpher": "*"
```

to the `require` section of your composer.json.

 ## Usage
 
```php
'components' => [
   // ...
    'morpher' => [
        'class' => 'slawap\morpher\Morpher'
    ]
    // ...
 ]
 ```

Get all case; 
```php
    Yii::$app->morpher
        ->setQuery('Санкт-Петербург')
    ->getData();

     /*result 
     Array
     (
         [Р] => Санкт-Петербурга
         [Д] => Санкт-Петербургу
         [В] => Санкт-Петербург
         [Т] => Санкт-Петербургом
         [П] => Санкт-Петербурге
         [множественное] => Array
             (
                 [И] => Санкт-Петербурги
                 [Р] => Санкт-Петербургов
                 [Д] => Санкт-Петербургам
                 [В] => Санкт-Петербурги
                 [Т] => Санкт-Петербургами
                 [П] => Санкт-Петербургах
             )
     
     ); */
 ```
 
Get case; 
```php
    echo Yii::$app->morpher
        ->setQuery('Санкт-Петербург')
        ->setCase(Morpher::PREPOSITIONAL)
    ->getData();
    //result 'Санкт-Петербурге'
 ```

Get plural case; 
```php
    echo Yii::$app->morpher
        ->setQuery('Санкт-Петербург')
        ->setCase(Morpher::PREPOSITIONAL)
        ->setPlural()
    ->getData();
    
    //result Санкт-Петербургах
 ```


