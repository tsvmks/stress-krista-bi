# По итогам ликции Нагрузочное тестирование

## План 

* Тестирование с использованием Apache JMeter

* Тестирование с использованием Gatling

### JMeter - быстрое создание проекта 
Чтобы не заполнять вручную проект можно сделать
* В Firefox выполнить необходимые пользовательские действия с открытой консолью разработчика F12
* Сохранить в HarArchive.
* В JMeter создать проект на основе шаблона HTTP Test Script Recorder, например на порт 9999
* Импортировать сессию в Fiddler из сохраннного Har файла
* Настроить Gateway Manual Proxy http=localhost:9999;https=localhost:9999 на перенаправление вызовов
* На необходимых запросах нажимать Replay (R)
* После этого все запросы с параметрами попадут в JMeter
