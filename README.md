Лабораторная работа №19 по курсу Linux Pro.

Задание:
 - В теоретической части требуется: 
     Найти свободные подсети
     Посчитать количество узлов в каждой подсети, включая свободные
     Указать Broadcast-адрес для каждой подсети
     Проверить, нет ли ошибок при разбиении

 - В практической части требуется: 
     Соединить офисы в сеть согласно логической схеме и настроить роутинг
     Интернет-трафик со всех серверов должен ходить через inetRouter
     Все сервера должны видеть друг друга (должен проходить ping)
     У всех новых серверов отключить дефолт на NAT (eth0), который vagrant поднимает для связи
     Добавить дополнительные сетевые интерфейсы, если потребуется



Решение:

Теоретическая часть:

	Даны сети:

		Сеть office1
		- 192.168.2.0/26      - dev
		- 192.168.2.64/26     - test servers
		- 192.168.2.128/26    - managers
		- 192.168.2.192/26    - office hardware

		Сеть office2
		- 192.168.1.0/25      - dev
		- 192.168.1.128/26    - test servers
		- 192.168.1.192/26    - office hardware

		Сеть central
		- 192.168.0.0/28     - directors
		- 192.168.0.32/28    - office hardware
		- 192.168.0.64/26    - wifi

Сеть 192.168.2.0/26:
 - Количество узлов - 62
 - Broadcast-адрес - 192.168.2.63

Сеть 192.168.2.64/26:
 - Количество узлов - 62
 - Broadcast-адрес - 192.168.2.127

Сеть 192.168.2.128/26:
 - Количество узлов - 62
 - Broadcast-адрес - 192.168.2.191

Сеть 192.168.2.192/26:
 - Количество узлов - 62
 - Broadcast-адрес - 192.168.2.255

Сеть 192.168.1.0/25:
 - Количество узлов - 126
 - Broadcast-адрес - 192.168.1.127

Сеть 192.168.1.128/26:
 - Количество узлов - 62
 - Broadcast-адрес - 192.168.1.191

Сеть 192.168.1.192/26:
 - Количество узлов - 62
 - Broadcast-адрес - 192.168.1.255

Сеть 192.168.0.0/28:
 - Количество узлов - 14
 - Broadcast-адрес - 192.168.0.15

Сеть 192.168.0.32/28:
 - Количество узлов - 14
 - Broadcast-адрес - 192.168.0.47

Сеть 192.168.0.64/26:
 - Количество узлов - 62
 - Broadcast-адрес - 192.168.0.127

Свободные сети:
192.168.0.16/28, 192.168.0.48/28, 192.168.0.128/25

Практическая часть:

Схема сети изображена на рисунке.
Разворачивание ВМ и их настройка с помощью vagrant и ansible.