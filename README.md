1. Роль для разворачивания Prometheus
Установка Prometheus
Добавление systemd service файла для его запуска
Создание нужных пользователей и директорий с нужными правами и владельцами
Добавление конфигурации с прописанным таргетом для мониторинга самого Prometheus (см. https://prometheus.io/docs/prometheus/latest/getting_started/#configuring-prometheus-to-monitor-itself)
Запуск и релоад сервиса при изменении глобальных параметров конфигурации (не забудьте вынести эти параметры в defaults)

3. Роль для разворачивания Node Exporter
Установка Node Exporter
Добавление systemd service файла для его запуска
Создание нужных пользователей и директорий с нужными правами и владельцами
Добавление в конфигурацию Prometheus нового хоста через https://prometheus.io/docs/prometheus/latest/configuration/configuration/#static_config (не забудьте что сервер с Prometheusом может находиться не локально, вам нужно уметь добавлять конфигурацию и на удаленный сервер). Учтите, что у вас не должно возникать конфликтов в конфигурации при запуске роли Node Exporter и роли Prometheus, несмотря на то, что обе роли вносят изменения в конфиг.
Запуск сервиса Node Exporter и релоад сервиса Prometheus при добавлении нового хоста в конфигурацию

4. Роль для разворачивания ElasticSearch и Kibana
Установка ElasticSearch
Установка Kibana
Добавление systemd service файла для запуска обоих
Создание нужных пользователей и директорий с нужными правами и владельцами
Запуск сервисов

5. Роль для разворачивания FluentBit
Установка FluentBit
Добавление systemd service файла для его запуска
Создание нужных пользователей и директорий с нужными правами и владельцами
Добавление конфигурации со сбором логов из journald и пересылкой их в установленный ElasticSearch.
Запуск сервиса

для запуска стека:
ansible-playbook -i inventory/hosts.yml site.yml
