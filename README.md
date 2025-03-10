Роль для разворачивания Prometheus<br>
<li>Установка Prometheus
<li>Добавление systemd service файла для его запуска
<li>Создание нужных пользователей и директорий с нужными правами и владельцами
<li>Добавление конфигурации с прописанным таргетом для мониторинга самого Prometheus
<li>Запуск и релоад сервиса при изменении глобальных параметров конфигурации
  
Роль для разворачивания Node Exporter
<li>Установка Node Exporter
<li>Добавление systemd service файла для его запуска
<li>Создание нужных пользователей и директорий с нужными правами и владельцами
<li>Добавление в конфигурацию Prometheus нового хоста через https://prometheus.io/docs/prometheus/latest/configuration/configuration/#static_config
<li>Запуск сервиса Node Exporter и релоад сервиса Prometheus при добавлении нового хоста в конфигурацию

Роль для разворачивания ElasticSearch и Kibana
<li>Установка ElasticSearch и Kibana
<li>Добавление systemd service файла для запуска обоих
<li>Создание нужных пользователей и директорий с нужными правами и владельцами
<li>Запуск сервисов

5. Роль для разворачивания FluentBit
<li>Установка FluentBit
<li>Добавление systemd service файла для его запуска
<li>Создание нужных пользователей и директорий с нужными правами и владельцами
<li>Добавление конфигурации со сбором логов из journald и пересылкой их в установленный ElasticSearch.
<li>Запуск сервиса

для запуска стека:
ansible-playbook -i inventory/hosts.yml site.yml
