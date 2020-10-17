# По итогам лекции Нагрузочное тестирование

## План 

На нашем отчете по моделям http://test.piao.fm.epbs.ru/static-report/web/report-desktop-war.html?reportId=38b211ab-b98d-4e1a-a4a6-5bfbfdd4a6ed&version=01.10.2020%2005.58.12.098&device=Desktop провести пример нагрузочного тестирования.

* Тестирование с использованием Apache JMeter

* Тестирование с использованием Gatling

## Apache JMeter

### JMeter - быстрое создание проекта 
Чтобы не заполнять вручную проект можно сделать
* В Firefox выполнить необходимые пользовательские действия с открытой консолью разработчика F12
* Сохранить в HarArchive.
* В JMeter создать проект на основе шаблона HTTP Test Script Recorder, например на порт 9999
* Импортировать сессию в Fiddler из сохраннного Har файла
* Настроить Gateway Manual Proxy http=localhost:9999;https=localhost:9999 на перенаправление вызовов
* На необходимых запросах нажимать Replay (R)
* После этого все запросы с параметрами попадут в JMeter

### В каталоге JmeterProject пример загрузки одного отчета

### В каталоге JMeterMVN пример mvn-проекта для запуска теста на максимальную производительность и тест стабильности
Более подробная информация в readme в подпапке

## Выводы по JMeter

* Есть GUI
* Есть HTTP Test Script Recorder, можно быстро создать проект с необходимыми запросами
* Есть View Result Tree, можно быстро посмотреть результаты выполнения
* Есть модульность
* Несмотря на наличие модульности, все переменные глобальные, есть риск переопределения
* Вроде как тормознутый
* Ограничение по настройке профилей нагрузки имеющимся GUI
* Есть настроенные доски в графане

Подойдет для небольших проектов без сложной логики

## Полезные ссылки

* https://training.ragozin.info/collateral/loadlab/bom.pdf
