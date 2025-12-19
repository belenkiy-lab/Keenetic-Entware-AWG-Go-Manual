$\textcolor{green}{\text{v2025-12-19}}$
# Подготовка
Для собственного удобства я буду использовать редактор [Notepad++](https://github.com/notepad-plus-plus/notepad-plus-plus).  

#### Обратите внимание, что ***все*** файлы должны быть с обозначением конца строки в файле в Unix (LF):  
![Unix (LF)](!img/00__Unix-LF.png)  
***


## 1) Подготовка нативного/оригинального файла AWG (conf-файла)
Получить файл можно в приложении AmneziaVPN. Как именно - Вы можете посмотреть в [документации](https://storage.googleapis.com/amnezia/docs?m-path=/ru/documentation/instructions/share-connection).  
Пример внутренней структуры conf-файла:  
![AWG 1.0 conf-file example](!img/01__awg0.png)  

Нам требуется добавить в conf-файл параметры пакетов имитации *i1...i5*.  
В качестве примера возьмём [готовые параметры пакетов *i1...i5*](https://voidwaifu.github.io/Special-Junk-Packet-List/):  
![voidwaifu](!img/02__SpecialJunk.png)  

В результате у нас должен получиться файл со следующей структурой:
![AWG 1.5\2.0 conf-file example](!img/03__awg0_with_SpecialJunk.png)  


## 2) Проверка conf-файла с параметрами пакетов имитации *i1...i5*.  
Для проверки conf-файл достаточно загрузить в AmneziaVPN версии не ниже 4.8.8.3.   
А лучше всего в самую [актуальную версию](https://github.com/amnezia-vpn/amnezia-client/releases). На момент написания данной статьи это [версия 4.8.11.4](https://github.com/amnezia-vpn/amnezia-client/releases/tag/4.8.11.4).

Для проверки используйте устройство, подключенное к той же сети, что и роутер.  
Подключитесь через загруженный в приложение conf-файл.  
Проверьте, что IP поменялся с помощью любого сервиса, например [2ip.io](https://2ip.io/).  
Если IP отображаемый сервисом совпадает с IP Endpoint - значит всё прошло успешно.  
### Если что-то пошло не так, например, ничего не открывается - пробуйте использовать другие параметры пакетов имитации *i1...i5* в conf-файле.


## 3) Резервное копирование роутера
Перед любыми изменениями в роутере **настоятельно** рекомендую иметь резервную копию как минимум файла конфигурации самого роутера *startup-config*.  
![KeenOS backup](!img/05__KeenOS_backup.png)  


## 4) Установка компонентов прошивки KeenOS
Для работы нам понадобится как минимум следующий набор компонентов KeenOS:  
![KeenOS components 1](!img/06__System-Componenets_1.png)  

![KeenOS components 2](!img/06__System-Componenets_2.png)  


## 5) Включение SMB для удобного доступа к файловой системе внешнего носителя
Название самого диска и какое оно будет в расшаренном виде, разумеется, Вы выбираете сами.
![KeenOS SMB](!img/07__SMB-server.png)  


## 6) Установка Entware
[Инструкция по установке EntWare на сайте Keenetic](https://help.keenetic.com/hc/ru/articles/360021214160).  

При установке Entware в логах роутера может быть такая ошибка:  
![KeenOS entware install invalid initrc](!img/08__Entware_install_err.png)  
Это нормально, т.к. это новая установка и скрипта инициализации логично нет на флешке.  

Дожидаемся окончания установки:  
![KeenOS entware install DONE](!img/09__Entware_install_DONE.png)  
***
***
### [Установка модуля AWG-Go для Entware >>](/../../blob/main/blob/01__Entware_AWG-Go_Install/Entware_AWG-Go_Install.md)
# [<< На главную](/../../../)