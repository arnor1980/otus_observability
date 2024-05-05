# ДЗ-1: Prometheus - Exporters, Service Discovery

## Установленное ПО
- Nnginx
- MySQL
- PHP-FPM
- Joomla CMS

## Конфигурация Prometheus
 Конфигурация выполнена с использованием контенеров
 - Базовые компоненты
   - Prometheus
        ```sh
        ./prometheus/prometheus.yml  
        ```
   - Alermanager
        ```sh
        ./alertmanager/comfig.yml  
        ```

 - Экспортеры для Prometheus
   - Node - сбор метрик базовых метрик узла: CPU, RAM, Disk и т.п.
   - Nginx - сбор метрик веб сервера nginx
   - PHP-FPM - сбор метрик FastCGI Process Manager
   - Mysql - сбор метрик сервера СУБД Mysql
   - Blackbox - сбор внешних метрик, доступность сайта, срок действия сертификата, и т.п.
        ```sh
        ./exporters/blackbox/blackbox.yml  
        ```
## Настройка экспортеров в Prometheus
- Для каждого из экспортеров настроены пороги оповещений для некоторых метрик в файле: 
    ```sh
     ./prometheus/rules.yml  
    ```

## AlertManager
- Создана конфигурация для отправки оповещений в  Telegram.
    ```sh
     ./alertmanager/config.yml  
    ```
