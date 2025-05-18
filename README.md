
# Ansible Playbooks Collection

Набор Ansible плейбуков для настройки и управления серверной инфраструктурой.

---

## Содержание

* `adduser-ssh.yaml` — Добавление пользователя и настройка SSH-доступа.
* `docker.yaml` — Установка и настройка Docker на сервере.
* `nginx.yaml` — Установка и базовая настройка Nginx.
* `package-update.yaml` — Обновление всех пакетов на сервере.
* `postgresql-setup.yaml` — Установка и базовая настройка PostgreSQL.
* `prometheus+grafana.yaml` — Установка и настройка Prometheus и Grafana для мониторинга.

---

## Требования

* Ansible 2.9+
* Доступ к управляемым серверам по SSH с правами sudo
* Рабочий инвентори файл Ansible с описанием серверов

---

## Использование

1. Клонируйте репозиторий с плейбуками:

```bash
git clone <repository-url>
cd <repository-folder>
```

2. Отредактируйте инвентори файл (`hosts`), указав ваши серверы.

3. Запустите нужный плейбук:

```bash
ansible-playbook -i hosts adduser-ssh.yaml
ansible-playbook -i hosts docker.yaml
ansible-playbook -i hosts nginx.yaml
ansible-playbook -i hosts package-update.yaml
ansible-playbook -i hosts postgresql-setup.yaml
ansible-playbook -i hosts prometheus+grafana.yaml
```

---

## Описание плейбуков

### adduser-ssh.yaml

* Создает нового пользователя на сервере
* Настраивает SSH доступ (копирует SSH ключи)
* Настраивает sudo права для пользователя (если необходимо)

### docker.yaml

* Устанавливает Docker Engine и Docker Compose
* Добавляет пользователя в группу docker для работы без sudo

### nginx.yaml

* Устанавливает Nginx
* Копирует конфигурационные файлы
* Запускает и включает сервис nginx

### package-update.yaml

* Обновляет все пакеты ОС до последних версий
* Выполняет очистку кеша менеджера пакетов

### postgresql-setup.yaml

* Устанавливает PostgreSQL
* Настраивает основные параметры (пользователи, базы данных)
* Запускает и включает службу PostgreSQL

### prometheus+grafana.yaml

* Устанавливает Prometheus для мониторинга
* Устанавливает Grafana для визуализации метрик
* Настраивает сервисы и базовые дашборды






