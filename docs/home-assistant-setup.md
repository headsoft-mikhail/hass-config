# Среда Home Assistant

Снимок текущего состояния; версии проверены 2026-11-10 через HA System Health и update-сущности. Перед изменениями в новой задаче версии перепроверяются. Секреты здесь не хранятся.

## Сервер и оборудование

- Home Assistant OS на Raspberry Pi 5, архитектура aarch64.
- Корпус Argon ONE V3, внутренний NVMe, оригинальный БП 27 Вт; BLSTR DAC отсутствует.
- Скрипты управления Argon не установлены; способ управления вентилятором и состояние I2C не определены. Прошивка RPi и RP2040 корпуса — разные компоненты.
- Роутер и HA подключены к EcoFlow RIVER 3.
- Два ZBT-1: отдельные адаптеры Zigbee и Matter/Thread.
- Aqara E1 подключён к USB HA только для питания.
- Два HDD на роутере используются для DLNA; Transmission работает на роутере.

## Доступ и инструменты

- HA: http://homeassistant.local:8123, локальная сеть.
- Браузер агента использует отдельную учётную запись; управление устройствами и изменения требуют согласования по [AGENTS.md](../AGENTS.md).
- HA-MCP работает внутри Core. Общий Read Only Mode включён; Codex использует локальный Streamable HTTP порт 9584 и endpoint `/readonly`.
- Подключение Codex хранится в пользовательском `~/.codex/config.toml`; секретный URL вне Git.
- Webhook HA-MCP включён, авторизация — Home Assistant OAuth. Прямой локальный порт использует секретный путь. Стартовое уведомление отключено. File & YAML Tools не установлены.
- Скилл `home-assistant-best-practices` установлен в пользовательском каталоге Codex.
- Studio Code Server открывает `/config` в Restricted Mode.
- Advanced SSH & Web Terminal установлен; подключение с Mac не проверено.

## Конфигурация и Git

- Репозиторий сервера: `/config`; локальная копия: `/Users/mikhail_afanasiev/Dev/hass-config`.
- Ветка master; синхронизация: commit → push → pull на другой стороне. Серверный pull владелец выполняет в Studio Code Server; автоматического развёртывания нет.
- Дашборды хранятся в UI (storage); `www/dashboards` содержит ручные копии. Изменение копии в Git не изменяет активную панель.
- `.storage` напрямую не редактируется. Реестры и secrets не хранятся в Git.

## Дашборды

| Копия в Git | Активный URL |
|---|---|
| www/dashboards/home.yaml | http://homeassistant.local:8123/dashboard-home |
| www/dashboards/climate.yaml | http://homeassistant.local:8123/dashboard-climate |
| www/dashboards/systems.yaml | http://homeassistant.local:8123/dashboard-systems |

«Дом» — системная панель по умолчанию, видима в боковом меню, иконка mdi:home-assistant. Индивидуальный выбор панели в профиле может переопределять системный. Есть также «Эксперименты» и встроенные панели.

## Резервные копии

- Home Assistant Google Drive Backup: расписание каждые 3 дня.
- Восстановление: скачать бэкап, предоставить ключ из secrets, восстановить на устройстве. Ключ не переносить в документы.
- Актуальность последней успешной копии проверяется перед изменениями, требующими отката. Тестовое восстановление не проверено.

## Установленное ПО

Источник — установленный пакет по HA; версия загруженного frontend-кода может зависеть от кэша браузера.

| Компонент | Версия |
|---|---|
| Core | 2026.11.1 |
| Supervisor | 2026.10.5 |
| HAOS | 18.5 |
| Python | 3.14.10 |
| Marketplace | 2026.11.1 |

### Приложения

| Приложение | Версия | Состояние при проверке |
|---|---|---|
| Matter Server | 9.3.0 | работает |
| Home Assistant Google Drive Backup | 0.112.1 | работает |
| Mosquitto broker | 7.1.3 | работает |
| Advanced SSH & Web Terminal | 24.2.1 | работает |
| Zigbee2MQTT | 2.14.3-1 | работает |
| OpenThread Border Router | 3.4.0 | работает |
| AdGuard Home | 6.3.2 | остановлено |
| Studio Code Server | 7.2.0 | работает |
| Silicon Labs Flasher | 0.5.0 | остановлено |

### Пользовательские интеграции и карточки

| Компонент | Версия |
|---|---|
| auto-entities | v1.16.1 |
| Bar Sensor Card | 1.1.3 |
| browser_mod | v3.4.2 |
| Clock Weather Card | v3.1.0 |
| Custom Features for Home Assistant Cards | 4.11.3 |
| EcoFlowCloud | v1.7.2 |
| Gismeteo | 3.1.0 |
| HA-MCP — Manage Home Assistant with AI | v9.1.2 |
| Horizon Card | v1.5.3 |
| Hourly Weather Card | 7.2.0 |
| layout-card | v2.4.7 |
| Maintenance Supporter | v2.120.0 |
| Meross LAN | v6.0.0 |
| mini-graph-card | v0.13.0 |
| Mushroom | v5.2.3 |
| PetKit | 0.1.14 |
| Pie Chart Card | 03a951f |
| Power Flow Card Plus | v0.5.0 |
| Qingping | v.1.3.1 |
| Raspberry Pi GPIO | 2026.4.0 |
| Transmission 3.x | 876d632 |
| Transmission Card | 0.24.2 |
| Uptime Card | v0.16.0 |
| Wind Rose Card | v2.7.0 |
| Yandex Smart Home | v1.1.3 |
| Yandex.Station | v3.22.3 |

## Особенности системы

- Мониторинг интернета: Ping 8.8.8.8, count=1, штатный polling отключён; internet_ping_poll опрашивает раз в 15 секунд. binary_sensor.internet_available подтверждает on/off задержками по 17 секунд; уведомления зависят от него.
- Температура RPi: sensor.rpi_cpu_temperature. Старого управления вентилятором GPIO17 нет; этот сенсор не означает управление охлаждением Argon.
- Mobile App: передача сенсоров отключена на устройствах, оставшиеся сенсорные entity деактивированы. Приложения, устройства и push-уведомления сохраняются.
- HomeKit Device импортирует устройства Aqara; HomeKit Bridge экспортирует сущности HA в Apple Home через мосты по комнатам.
- Вентиляция Horynize CF700: контроллер GTC SYBERIA 5.0 и пульт GTC OAZIS 5.0; реализованные Modbus-регистры важнее неточной бумажной карты.

## Справочники

- [Физический смысл устройств и связи](home-assistant-system-notes.md).
- [Каталог entity](home-assistant-entities.md): датированный инвентарь, не live-реестр. Перед изменением проверять затронутые ID на сервере; отключённые entity не входят в обычный список states.
- Текущие задачи и временные диагностики находятся в игнорируемой `tmp/`.
