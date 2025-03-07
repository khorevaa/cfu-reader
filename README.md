# Обработка для просмотра содержимого cfu-файлов в режиме 1С: Предприятие
![Платформа 1С](https://img.shields.io/badge/1с_platform-8.3.14.1208-yellow.svg)
[![GitHub release](https://img.shields.io/github/release/vandalsvq/cfu-reader.svg)](https://github.com/vandalsvq/cfu-reader/releases)

Обработка для анализа файлов .cfu в режиме предприятия в любой конфигурации для 1С 8.3.+. Основана на разработке [CFU-reader](https://infostart.ru/public/97194/) [Андрей Д.](https://infostart.ru/profile/128365/) Многое из его обработки было использовано мною. 

Честно сказать, я бы вряд ли осилил изучать все тонкости внутреннего устройства файлов .cfu, если бы не нашел на что опереться. Отчасти поэтому, мною было решено не уделять внимание проверке на обновлениях для 1С 8.2 и ниже, поскольку считаю, что можно использовать обработку из указанной выше статьи.

## Возможности
* реализована на управляемых формах
* поддерживает все объекты платформы 8.3.+
* имеет формы просмотра макетов, справок, графических карт, картинок и текста

### Известные проблемы
* Не показывает предопределенные элементы
* В некоторых случаях, не удается выделить текст модуля формы отдельно. Происходит очень редко.

## Тестирование

Файлы CFU проверенные на обработке
* ЗУП 3.1.10.50 76Мб - положительно
* УПП 1.3.122.3 8.5Мб - положительно
* УПП 1.2.39.1 7.7Мб - положительно
* Документооборот КОРП 2.1.13.28 77.7Мб - положительно
* БухгалтерияПредприятияКОРП 3.0.71.63 58.3Мб - положительно
* БухгалтерияПредприятияКОРП 2.6.66.82 11Мб - положительно
* УТ 11.4.7.141 314 Мб - положительно

А также собственные сборки и просто тестовые экземпляры созданные на пустых конфигурациях. 
Платформа при тестировании: **8.3.18.1208**

## Дополнительная информация
Обработка версии 2.6 включает новую версию UnpackV8, который вполне успешно распаковывает большие файлы обновлений. Так что ни УТ, ни ERP теперь не страшны. Только будьте внимательны, при распаковке в каталоге %temp% создается временная папка с данными из файла обновления. А это как правило в 4 раза больший объем, чем сам .cfu. Т.е. проверяйте наличие свободного места. Ну и SSD конечно был бы крайне желателен.
### Про батарейки

В обработке используются некоторые процедуры из общих модулей БСП. В частности: ОбщегоНазначенияКлиентСервер, СтроковыеФункцииКлиентСервер. Как говорится "batteries not included", поэтому рекомендую открывать в конфигурациях, основанных на БСП.