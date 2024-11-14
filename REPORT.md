<h3>Отчёт по лабораторной работы №2</h3>
<h4>Выполнил: Останин А.</h4>

1) Для начала создадим 3 виртуальных машины
   <br>![image](https://github.com/user-attachments/assets/13217264-af33-4594-94a5-22d3bc7a07aa)<br>
2) После чего в настройках каждой из машин в сетевом адаптере поменяем тип подключения на сетевой мост
   <br>![image](https://github.com/user-attachments/assets/218a8ad4-3c92-4b07-b1f6-96a7f05b9efb)<br>
3) Далее с помощью команды ```ip add show``` посмотрим ip-адрес каждой из машин
   <br>![image](https://github.com/user-attachments/assets/5213a2e8-b6ff-43a6-9a20-29d7e8bae364)<br>
4) Проверим связь из машины А в машину Б с помощью команды ```ping "ip адрес машины"```
   <br>![image](https://github.com/user-attachments/assets/1536693d-cae9-4981-8f2b-d99c96daf6c0)<br>
   все работает.<br>
   Проверим также связь из машины А в машину В
   <br>![image](https://github.com/user-attachments/assets/e9b83000-830d-4359-9363-bc17bd5ef1f7)<br>
   также все работает.<br>
5) Теперь необходимо заблокировать доступ из машины Б в машину В. И для этого используем следующую команду:
```sudo iptebles -t filter -A INPUT -s 100.117.61.136 -j REJECT```, которая будет отклонять запросы с адреса, который указан,
а в данном случае ```100.117.61.136``` является ip-адресом машины Б
6) Проверим доступ из машины Б в машину В
   <br>![image](https://github.com/user-attachments/assets/4dba7de8-3a1f-40af-bdf2-83ec17a56682)<br>
   запрос отклоняется, так что все работает как нужно
7) Ну и наконец проверим доступ в интернет ```ping google.com```
   <br>![image](https://github.com/user-attachments/assets/b0bba3bf-c76b-4855-8b74-ed544499244e)<br>
   доступ в интернет имеется
8) Скриншот сразу всех трех машин
   <br>![image](https://github.com/user-attachments/assets/4c0f9329-cdd2-4f41-b1c7-abe26ba2db12)<br>
<h4>Вывод</h4>
Научились обеспечивать доступ из одной машины к другой, а также блокировать его.
