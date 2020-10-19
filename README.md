# По итогам лекции Нагрузочное тестирование

## План 

На нашем отчете по моделям http://localhost:8080/static-report/web/report-desktop-war.html?reportId=38b211ab-b98d-4e1a-a4a6-5bfbfdd4a6ed&version=01.10.2020%2005.58.12.098&device=Desktop провести пример нагрузочного тестирования.

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
* Низкая производительность: начинает работать нестабильно если подключений > 100
* Ограничение по настройке профилей нагрузки имеющимся GUI
* Есть настроенные доски в графане

Подойдет для небольших проектов без сложной логики

## Gatling

* Более серьезный инструмент, в котором отсутствует GUI, зато есть DSL scala.
* Очень много возможностей по настройке профилей нагрузки
* Нормально реализована модульность, контекст выполнения
* Высокая производительность, которая позволяет нагрузить систему даже с одной машины. Но если этого не хватит вроде как можно настроить кластер
* Все надо писать вручную на java/scala
* В Scala DSL все является выражением, поэтому идея ошибки в этом коде не подсвечивает
* Доски в Grafana входят в платную часть, зато есть доски от преподавателей курса
* Техплатформа вроде как рассматриавает его как замену HP LoadRunner, по крайней мере смотрит
* Есть пример проекта консолидации на gatling

Подойдет для крупных проектов, таких как Консолидвция, на хабре инструмент продвигает Тинькофф

## А что дальше

Проект нагрузочного тестированич на чем бы он не был реализован необходимо встроить в свой CI.
Запускать тесты на стабильность необходимо регулярно, например каждую ночь.
Результаты можно не мониторить пока все ОК.
Если что-то случается с сервером, то по логам тестирования можно будет понять, в какой момент что-то пошло не так.

## Полезные ссылки

* https://training.ragozin.info/collateral/loadlab/bom.pdf
* https://github.com/aragozin
* https://github.com/polarnik/
* https://gatling.io/docs/current/cheat-sheet/
* https://training.ragozin.info/loadlab-krista.pdf
