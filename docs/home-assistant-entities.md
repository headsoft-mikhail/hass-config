# Инвентарь устройств и entity Home Assistant

Снимок 2026-11-09. Прочитаны полные действующие реестры устройств, сущностей и комнат через Studio Code Server без изменения файлов. Удалённые записи deleted_entities/deleted_devices не включены. Имена загруженных entity дополнены читающим шаблоном HA. Значения состояний, секреты, MAC, серийные номера, токены и исходные служебные файлы сюда не перенесены.

- 180 записей устройств (физические, служебные и программные).
- 1350 зарегистрированных entity.
- 353 отключённые entity, 12 скрытых (признаки могут пересекаться).
- 1007 загруженных entity: 997 из реестра и 10 без регистрации.
- 1360 уникальных entity_id в объединённом каталоге.

Физическое назначение и известные нюансы: [system-notes](home-assistant-system-notes.md). Перед изменением перепроверять затронутые entity на сервере: это датированный снимок, не гарантия неизменности. «Нет в states» не равнозначно unavailable; отключённая entity не загружена. Названия/модели Maintenance Supporter описывают обслуживание, а HACS/Supervisor — программные компоненты, не дополнительные физические приборы.

## Сводка по интеграциям

| Интеграция | Entity в реестре | Отключено |
| --- | ---: | ---: |
| androidtv_remote | 2 | 0 |
| automation | 38 | 0 |
| backup | 5 | 0 |
| command_line | 5 | 0 |
| derivative | 1 | 0 |
| ecoflow_cloud | 55 | 25 |
| esphome | 3 | 0 |
| filter | 4 | 0 |
| generic_thermostat | 2 | 0 |
| gismeteo | 21 | 10 |
| hacs | 52 | 25 |
| hassio | 79 | 38 |
| homeassistant | 7 | 0 |
| homeassistant_sky_connect | 4 | 2 |
| homekit_controller | 148 | 54 |
| input_boolean | 4 | 0 |
| input_button | 1 | 0 |
| input_datetime | 2 | 0 |
| input_number | 4 | 0 |
| input_select | 4 | 0 |
| integration | 6 | 0 |
| maintenance_supporter | 148 | 50 |
| matter | 25 | 8 |
| meross_lan | 12 | 10 |
| mobile_app | 87 | 41 |
| modbus | 5 | 0 |
| moon | 1 | 0 |
| mqtt | 389 | 60 |
| person | 2 | 0 |
| petkit | 49 | 6 |
| ping | 16 | 13 |
| qingping_cgs1 | 22 | 0 |
| raspberry_pi | 1 | 0 |
| rpi_gpio | 1 | 0 |
| rpi_power | 1 | 0 |
| script | 5 | 0 |
| snmp | 2 | 0 |
| sql | 1 | 0 |
| sun | 9 | 3 |
| template | 47 | 0 |
| timer | 1 | 0 |
| transmission3 | 17 | 0 |
| tuya | 11 | 0 |
| utility_meter | 23 | 0 |
| yandex_station | 28 | 8 |

## Гостиная

### IR Remote Control

- Производитель: Tuya.
- Модель: Universal smart IR remote control.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.ir_remote_control_switch_learn_ir_code` | IR Remote Control Learn ir code | загружена | — |
| `infrared.ir_remote_control_ir_emitter` | IR Remote Control Ir emitter | загружена | emitter |
| `infrared.ir_remote_control_learned_ir_timings` | IR Remote Control Learned ir timings | загружена | receiver |
| `sensor.ik_pult_battery` | Батарея | отключена: user; нет в states | % / battery |
| `sensor.ik_pult_voltage` | Напряжение | отключена: integration; нет в states | mV / voltage |
| `sensor.ir_remote_control_learned_ir_code` | IR Remote Control Learned ir code | загружена | — |
| `sensor.ir_remote_control_linkquality` | IR Remote Control Linkquality | загружена | lqi |
| `text.ir_remote_control_ir_code_to_send` | IR Remote Control Ir code to send | загружена | — |
### Living Room Behind Sofa Socket

- Производитель: BSEED.
- Модель: Wall-mounted electrical EU/FR/UK socket with power monitoring.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.living_room_behind_sofa_socket_identify` | Living Room Behind Sofa Socket Идентификация | загружена | identify |
| `number.living_room_behind_sofa_socket_countdown` | Living Room Behind Sofa Socket Countdown | загружена | s |
| `select.living_room_behind_sofa_socket_indicator_mode` | Living Room Behind Sofa Socket Indicator mode | загружена | — |
| `select.living_room_behind_sofa_socket_power_outage_memory` | Living Room Behind Sofa Socket Power outage memory | загружена | — |
| `select.living_room_behind_sofa_socket_switch_type_button` | Living Room Behind Sofa Socket Switch type button | загружена | — |
| `sensor.living_room_behind_sofa_socket_current` | Living Room Behind Sofa Socket Ток | загружена | A / current |
| `sensor.living_room_behind_sofa_socket_energy` | Living Room Behind Sofa Socket Энергия | загружена | kWh / energy |
| `sensor.living_room_behind_sofa_socket_linkquality` | Living Room Behind Sofa Socket Linkquality | загружена | lqi |
| `sensor.living_room_behind_sofa_socket_power` | Living Room Behind Sofa Socket Мощность | загружена | W / power |
| `sensor.living_room_behind_sofa_socket_voltage` | Living Room Behind Sofa Socket Напряжение | загружена | V / voltage |
| `switch.living_room_behind_sofa_socket` | Розетка за диваном | загружена | — |
| `switch.living_room_behind_sofa_socket_child_lock` | Living Room Behind Sofa Socket Child lock | загружена | — |
| `update.living_room_behind_sofa_socket` | Living Room Behind Sofa Socket | загружена | firmware |
### Living Room Curtain

- Производитель: Aqara.
- Модель: AM001.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 36.
- Аппаратная версия: 17.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.curtain_identify_2` | Curtain Identify | отключена: user; нет в states | identify |
| `cover.living_room_curtain` | Шторы в гостиной | загружена | — |
### Living Room Luminance Sensor

- Производитель: Moes.
- Модель: Light sensor.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.living_room_luminance_sensor_battery` | Living Room Luminance Sensor Батарея | загружена | % / battery |
| `sensor.living_room_luminance_sensor_illuminance` | Освещенность | загружена | lx / illuminance |
| `sensor.living_room_luminance_sensor_linkquality` | Living Room Luminance Sensor Linkquality | загружена | lqi |
### Living Room Radiator Thermostat

- Производитель: Aqara.
- Модель: AA006.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1030.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.gostinaia_living_room_radiator_thermostat_smart_radiator_thermostat_e1_problem` | Living Room Radiator Thermostat Smart Radiator Thermostat E1 Problem | загружена | problem |
| `button.smart_radiator_thermostat_e1_identify` | Smart Radiator Thermostat E1 Identify | отключена: user; нет в states | identify |
| `climate.living_room_radiator_thermostat` | Батарея в гостиной | загружена | — |
| `sensor.living_room_radiator_thermostat_battery` | Батарея термостата | загружена | % / battery |
| `sensor.living_room_radiator_thermostat_current_temperature` | Living Room Radiator Thermostat Current Temperature | загружена | °C / temperature |
### Living Room Roll Curtains

- Производитель: Aqara.
- Модель: AM003.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 33.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.curtain_identify_4` | Curtain Identify | отключена: user; нет в states | identify |
| `cover.living_room_roll_curtain` | Ролл-шторы в гостиной | загружена | — |
### Living Room Track

- Производитель: Aqara.
- Модель: AK073.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_9` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.living_room_track` | Трек в гостиной | загружена | — |
### ping Xgimi

- Производитель: Ping.
- Модель: —.
- Интеграции: ping.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.ping_xgimi` | ping Xgimi | загружена | connectivity |
| `device_tracker.192_168_1_106` | Ping Xgimi | отключена: integration; нет в states | — |
| `sensor.gostinaia_ping_xgimi_jitter` | Джиттер | отключена: integration; нет в states | ms / duration |
| `sensor.gostinaia_ping_xgimi_packet_loss` | Packet loss | отключена: integration; нет в states | % |
| `sensor.gostinaia_ping_xgimi_round_trip_time_average` | Среднее время в пути туда и обратно | отключена: integration; нет в states | ms / duration |
| `sensor.gostinaia_ping_xgimi_round_trip_time_maximum` | Максимальное время в пути туда и обратно | отключена: integration; нет в states | ms / duration |
| `sensor.gostinaia_ping_xgimi_round_trip_time_minimum` | Минимальное время в пути туда и обратно | отключена: integration; нет в states | ms / duration |
### XGIMI Horizon Ultra

- Производитель: XGIMI.
- Модель: XK03H.
- Интеграции: androidtv_remote.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `media_player.xgimi_horizon_ultra` | Проектор | загружена | tv |
| `remote.xgimi_horizon_ultra_switch_off` | XGIMI Horizon Ultra | загружена | — |
### Кондиционер

- Производитель: HAIER.
- Модель: AS25S2SF2FA-B.
- Интеграции: yandex_station.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `climate.gostinaia_haier_black` | Кондиционер УДЯ - Гостиная | загружена | — |
| `number.gostinaia_haier_black_temperatura` | Кондиционер Температура | загружена | °C |
| `select.gostinaia_haier_black_napravlenie_vozdukha` | Кондиционер Направление воздуха | загружена | — |
| `select.gostinaia_haier_black_skorost_ventiliatsii` | Кондиционер Скорость вентиляции | загружена | — |
| `select.gostinaia_haier_black_termostat` | Кондиционер Термостат | загружена | — |
| `switch.gostinaia_haier_black_podsvetka` | Кондиционер Подсветка | загружена | — |
### Станция Мини Red

- Производитель: Яндекс.
- Модель: Станция Мини 2 (2021).
- Интеграции: yandex_station.
- Версия ПО, прочитана 2026-11-09: 0.374.1.20.4835226640.20261106.304.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `calendar.yandex_station_m101k3a00pba6r_calendar` | Станция Мини Red Будильники | отключена: integration; нет в states | — |
| `camera.yandex_station_mini_lyrics` | Яндекс Станция Мини Red Текст | отключена: user; нет в states | — |
| `conversation.stantsiia_mini_alisa` | Станция Мини Red Алиса | отключена: user; нет в states | — |
| `media_player.yandex_station_m101k3a00pba6r` | Станция Мини Red | загружена | — |
| `select.yandex_station_mini_equalizer` | Яндекс Станция Мини Red Эквалайзер | отключена: integration; нет в states | — |
### Трек в кухне

- Производитель: Tuya.
- Модель: 1000-DB-100.
- Интеграции: tuya.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `light.living_room_1000_db_100` | Трек в кухне | загружена | — |

## Кухня

### Cat Feeder Plug 1

- Производитель: Tuya.
- Модель: Smart plug (with power monitoring).
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.cat_feeder_1_identify` | Идентификация | отключена: user; нет в states | identify |
| `number.cat_feeder_1_countdown` | Cat Feeder Plug 1 Countdown | загружена | s |
| `select.cat_feeder_1_indicator_mode` | Cat Feeder Plug 1 Indicator mode | загружена | — |
| `select.cat_feeder_1_power_outage_memory` | Cat Feeder Plug 1 Power outage memory | загружена | — |
| `select.cat_feeder_1_switch_type_button` | Cat Feeder Plug 1 Switch type button | загружена | — |
| `sensor.0xa4c138c14345a59d_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.cat_feeder_1_current` | Ток | отключена: user; нет в states | A / current |
| `sensor.cat_feeder_1_energy` | Энергия | отключена: user; нет в states | kWh / energy |
| `sensor.cat_feeder_1_power` | Мощность | отключена: user; нет в states | W / power |
| `sensor.cat_feeder_1_voltage` | Напряжение | отключена: user; нет в states | V / voltage |
| `switch.cat_feeder_1` | Cat Feeder Plug 1 | загружена | — |
| `switch.cat_feeder_1_child_lock` | Cat Feeder Plug 1 Child lock | загружена | — |
| `update.cat_feeder_1` | Cat Feeder Plug 1 | загружена | firmware |
### Cat Feeder Plug 2

- Производитель: Tuya.
- Модель: Smart plug (with power monitoring).
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.cat_feeder_2_identify` | Идентификация | отключена: user; нет в states | identify |
| `number.cat_feeder_2_countdown` | Cat Feeder Plug 2 Countdown | загружена | s |
| `select.cat_feeder_2_indicator_mode` | Cat Feeder Plug 2 Indicator mode | загружена | — |
| `select.cat_feeder_2_power_outage_memory` | Cat Feeder Plug 2 Power outage memory | загружена | — |
| `select.cat_feeder_2_switch_type_button` | Cat Feeder Plug 2 Switch type button | загружена | — |
| `sensor.0xa4c138e6d7c466b4_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.cat_feeder_2_current` | Ток | отключена: user; нет в states | A / current |
| `sensor.cat_feeder_2_energy` | Энергия | отключена: user; нет в states | kWh / energy |
| `sensor.cat_feeder_2_power` | Мощность | отключена: user; нет в states | W / power |
| `sensor.cat_feeder_2_voltage` | Напряжение | отключена: user; нет в states | V / voltage |
| `switch.cat_feeder_2` | Cat Feeder Plug 2 | загружена | — |
| `switch.cat_feeder_2_child_lock` | Cat Feeder Plug 2 Child lock | загружена | — |
| `update.cat_feeder_2` | Cat Feeder Plug 2 | загружена | firmware |
### Dishwasher

- Производитель: BSEED.
- Модель: Wall-mounted electrical EU/FR/UK socket with power monitoring.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.dishwasher_identify` | Dishwasher Идентификация | загружена | identify |
| `number.dishwasher_countdown` | Dishwasher Countdown | загружена | s |
| `select.dishwasher_indicator_mode` | Dishwasher Indicator mode | загружена | — |
| `select.dishwasher_power_outage_memory` | Dishwasher Power outage memory | загружена | — |
| `select.dishwasher_switch_type_button` | Dishwasher Switch type button | загружена | — |
| `sensor.0xa4c1388e62967342_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.dishwasher_current` | Dishwasher Ток | загружена | A / current |
| `sensor.dishwasher_energy` | Dishwasher Энергия | загружена | kWh / energy |
| `sensor.dishwasher_power` | Dishwasher Мощность | загружена | W / power |
| `sensor.dishwasher_voltage` | Dishwasher Напряжение | загружена | V / voltage |
| `switch.dishwasher` | Посудомоечная машина | загружена | — |
| `switch.dishwasher_child_lock` | Dishwasher Child lock | загружена | — |
| `update.dishwasher` | Dishwasher | загружена | firmware |
### Kitchen Dishwasher Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.kitchen_dishwasher_water_leak_sensor` | Протечка за посудомойкой | загружена | moisture |
| `binary_sensor.kukhnia_kitchen_dishwasher_water_leak_sensor_water_leak_sensor_problem` | Kitchen Dishwasher Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify_6` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.kitchen_dishwasher_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Kitchen Hood

- Производитель: Aqara.
- Модель: AR023.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 0035.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.dual_relay_module_t2_identify_2` | Dual Relay Module T2 Identify | отключена: user; нет в states | identify |
| `switch.kitchen_hood_fan` | Вытяжка | загружена | — |
| `switch.kitchen_hood_led` | Подсветка вытяжки | загружена | — |
### Kitchen LED Light

- Производитель: Aqara.
- Модель: AK027.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 47.
- Аппаратная версия: 19.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.relay_controler_identify` | Relay controler Identify | отключена: user; нет в states | identify |
| `switch.kitchen_led_light` | Подсветка кухни | загружена | — |
| `switch.relay_controler_switch1` | Relay controler Switch1 | отключена: user; нет в states | — |
### Kitchen Sink Water Leak Sensor

- Производитель: Aqara.
- Модель: AS014.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 0032.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.kitchen_sink_water_leak_sensor` | Протечка под раковиной в кухне | загружена | moisture |
| `binary_sensor.kukhnia_kitchen_sink_water_leak_sensor_water_leak_sensor_problem` | Kitchen Sink Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify_7` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.kitchen_sink_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Kitchen Socket

- Производитель: BSEED.
- Модель: Wall-mounted electrical EU/FR/UK socket with power monitoring.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.kitchen_socket_identify` | Kitchen Socket Идентификация | загружена | identify |
| `number.kitchen_socket_countdown` | Kitchen Socket Countdown | загружена | s |
| `select.kitchen_socket_indicator_mode` | Kitchen Socket Indicator mode | загружена | — |
| `select.kitchen_socket_power_outage_memory` | Kitchen Socket Power outage memory | загружена | — |
| `select.kitchen_socket_switch_type_button` | Kitchen Socket Switch type button | загружена | — |
| `sensor.0xa4c1388cfc5e0bcb_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.kitchen_socket_current` | Kitchen Socket Ток | загружена | A / current |
| `sensor.kitchen_socket_energy` | Kitchen Socket Энергия | загружена | kWh / energy |
| `sensor.kitchen_socket_power` | Kitchen Socket Мощность | загружена | W / power |
| `sensor.kitchen_socket_voltage` | Kitchen Socket Напряжение | загружена | V / voltage |
| `switch.kitchen_socket` | Розетка в кухне | загружена | — |
| `switch.kitchen_socket_child_lock` | Kitchen Socket Child lock | загружена | — |
| `update.kitchen_socket` | Kitchen Socket | загружена | firmware |
### Kitchen T1 Sensor

- Производитель: Aqara.
- Модель: Temperature and humidity sensor.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: 3000-0001.
- Аппаратная версия: 30.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.0x00158d000ab738e9_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.kitchen_humidity` | Влажность на кухне | загружена | % / humidity |
| `sensor.kitchen_pressure` | Давление на кухне | загружена | mmHg / atmospheric_pressure |
| `sensor.kitchen_t1_battery` | Kitchen T1 Sensor Батарея | загружена | % / battery |
| `sensor.kitchen_temperature` | Температура на кухне | загружена | °C / temperature |
| `sensor.living_room_t1_sensor_voltage` | Напряжение | отключена: user; нет в states | mV / voltage |
### Кормилка - Фрея

- Производитель: PetKit.
- Модель: Fresh Element Solo.
- Интеграции: petkit.
- Версия ПО, прочитана 2026-11-09: 1.267.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.fresh_element_solo_1_battery_installed` | Кормилка - Фрея Батарея установлена | загружена | — |
| `binary_sensor.fresh_element_solo_1_food_level` | Кормилка - Фрея Уровень пищи | загружена | problem |
| `button.fresh_element_solo_1_cancel_manual_feed` | Кормилка - Фрея Отмена ручного кормления | загружена | — |
| `button.fresh_element_solo_1_reset_desiccant` | Кормилка - Фрея Сброс влагопоглотителя | загружена | — |
| `select.fresh_element_solo_1_manual_feed` | Кормилка - Фрея Кормление вручную | загружена | — |
| `sensor.fresh_element_solo_1_battery_status` | Кормилка - Фрея Статус батареи | загружена | — |
| `sensor.fresh_element_solo_1_desiccant_days_remaining` | Кормилка - Фрея Осталось влагопоглотителя | загружена | d |
| `sensor.fresh_element_solo_1_dispensed` | Кормилка - Фрея Выдано | загружена | g |
| `sensor.fresh_element_solo_1_error` | Кормилка - Фрея Ошибка | загружена | — |
| `sensor.fresh_element_solo_1_manually_dispensed` | Кормилка - Фрея Ручное дозирование | загружена | g |
| `sensor.fresh_element_solo_1_planned` | Кормилка - Фрея Планируется | загружена | g |
| `sensor.fresh_element_solo_1_planned_dispensed` | Кормилка - Фрея Планируется выдача | загружена | g |
| `sensor.fresh_element_solo_1_rssi` | Кормилка - Фрея RSSI | загружена | dBm / signal_strength |
| `sensor.fresh_element_solo_1_status` | Кормилка - Фрея Статус | загружена | — |
| `sensor.fresh_element_solo_1_times_dispensed` | Кормилка - Фрея Время выдачи | загружена | — |
| `switch.fresh_element_solo_1_child_lock` | Кормилка - Фрея Блокировка от детей | загружена | — |
| `switch.fresh_element_solo_1_dispense_tone` | Кормилка - Фрея Звук выдачи | загружена | — |
| `switch.fresh_element_solo_1_food_shortage_alarm` | Кормилка - Фрея Сигнализация нехватки еды | загружена | — |
| `switch.fresh_element_solo_1_indicator_light` | Кормилка - Фрея Световой индикатор | загружена | — |
### Кормилка - Шанталь

- Производитель: PetKit.
- Модель: Fresh Element Solo.
- Интеграции: petkit.
- Версия ПО, прочитана 2026-11-09: 1.267.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.fresh_element_solo_2_battery_installed` | Кормилка - Шанталь Батарея установлена | загружена | — |
| `binary_sensor.fresh_element_solo_2_food_level` | Кормилка - Шанталь Уровень пищи | загружена | problem |
| `button.fresh_element_solo_2_cancel_manual_feed` | Кормилка - Шанталь Отмена ручного кормления | загружена | — |
| `button.fresh_element_solo_2_reset_desiccant` | Кормилка - Шанталь Сброс влагопоглотителя | загружена | — |
| `select.fresh_element_solo_2_manual_feed` | Кормилка - Шанталь Кормление вручную | загружена | — |
| `sensor.fresh_element_solo_2_battery_status` | Кормилка - Шанталь Статус батареи | загружена | — |
| `sensor.fresh_element_solo_2_desiccant_days_remaining` | Кормилка - Шанталь Осталось влагопоглотителя | загружена | d |
| `sensor.fresh_element_solo_2_dispensed` | Кормилка - Шанталь Выдано | загружена | g |
| `sensor.fresh_element_solo_2_error` | Кормилка - Шанталь Ошибка | загружена | — |
| `sensor.fresh_element_solo_2_manually_dispensed` | Кормилка - Шанталь Ручное дозирование | загружена | g |
| `sensor.fresh_element_solo_2_planned` | Кормилка - Шанталь Планируется | загружена | g |
| `sensor.fresh_element_solo_2_planned_dispensed` | Кормилка - Шанталь Планируется выдача | загружена | g |
| `sensor.fresh_element_solo_2_rssi` | Кормилка - Шанталь RSSI | загружена | dBm / signal_strength |
| `sensor.fresh_element_solo_2_status` | Кормилка - Шанталь Статус | загружена | — |
| `sensor.fresh_element_solo_2_times_dispensed` | Кормилка - Шанталь Время выдачи | загружена | — |
| `switch.fresh_element_solo_2_child_lock` | Кормилка - Шанталь Блокировка от детей | загружена | — |
| `switch.fresh_element_solo_2_dispense_tone` | Кормилка - Шанталь Звук выдачи | загружена | — |
| `switch.fresh_element_solo_2_food_shortage_alarm` | Кормилка - Шанталь Сигнализация нехватки еды | загружена | — |
| `switch.fresh_element_solo_2_indicator_light` | Кормилка - Шанталь Световой индикатор | загружена | — |
### Питьевой фонтан

- Производитель: PetKit.
- Модель: Eversweet 3 Pro (UVC Version).
- Интеграции: petkit.
- Версия ПО, прочитана 2026-11-09: 2.49.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.eversweet_3_pro_uvc_water_level` | Питьевой фонтан Уровень воды | загружена | problem |
| `button.eversweet_3_pro_uvc_reset_filter` | Питьевой фонтан Сброс фильтра | загружена | — |
| `select.eversweet_3_pro_uvc_light_brightness` | Яркость света | отключена: user; нет в states | — |
| `select.eversweet_3_pro_uvc_mode` | Режим | отключена: user; нет в states | — |
| `sensor.eversweet_3_pro_uvc_energy_usage` | Энергопотребление | отключена: user; нет в states | kWh / energy |
| `sensor.eversweet_3_pro_uvc_filter` | Питьевой фонтан Фильтр | загружена | % |
| `sensor.eversweet_3_pro_uvc_last_data_update` | Питьевой фонтан Последнее обновление данных | загружена | timestamp |
| `sensor.eversweet_3_pro_uvc_purified_water_today` | Очищенная вода сегодня | отключена: user; нет в states | — |
| `switch.eversweet_3_pro_uvc_do_not_disturb` | Не беспокоить | отключена: user; нет в states | — |
| `switch.eversweet_3_pro_uvc_light` | Свет | отключена: user; нет в states | — |
| `switch.eversweet_3_pro_uvc_power` | Питьевой фонтан Мощность | загружена | — |
### Холодильник

- Производитель: BSEED.
- Модель: Wall-mounted electrical EU/FR/UK socket with power monitoring.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.fridge_socket_identify` | Холодильник Идентификация | загружена | identify |
| `number.fridge_socket_countdown` | Холодильник Countdown | загружена | s |
| `select.fridge_socket_indicator_mode` | Холодильник Indicator mode | загружена | — |
| `select.fridge_socket_power_outage_memory` | Холодильник Power outage memory | загружена | — |
| `select.fridge_socket_switch_type_button` | Холодильник Switch type button | загружена | — |
| `sensor.0xa4c1382d9b41cc1a_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.fridge_socket_current` | Холодильник Ток | загружена | A / current |
| `sensor.fridge_socket_energy` | Холодильник Энергия | загружена | kWh / energy |
| `sensor.fridge_socket_power` | Холодильник Мощность | загружена | W / power |
| `sensor.fridge_socket_voltage` | Холодильник Напряжение | загружена | V / voltage |
| `switch.fridge_socket` | Холодильник | загружена | — |
| `switch.fridge_socket_child_lock` | Холодильник Child lock | загружена | — |
| `update.fridge_socket` | Холодильник | загружена | firmware |

## Спальня

### AirMonitor2

- Производитель: Qingping.
- Модель: CGS2.
- Интеграции: qingping_cgs1.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `number.airmonitor2_co2_offset` | AirMonitor2 CO2 Offset | загружена | ppm |
| `number.airmonitor2_humidity_offset` | AirMonitor2 Humidity Offset | загружена | % |
| `number.airmonitor2_noise_offset` | AirMonitor2 Noise Offset | загружена | dB |
| `number.airmonitor2_pm10_offset` | AirMonitor2 PM10 Offset | загружена | μg/m³ |
| `number.airmonitor2_pm2_5_offset` | AirMonitor2 PM2.5 Offset | загружена | μg/m³ |
| `number.airmonitor2_temp_offset` | AirMonitor2 Temp Offset | загружена | °C |
| `number.airmonitor2_tvoc_index_offset` | AirMonitor2 eTVOC Index Offset | загружена | % |
| `number.airmonitor2_update_interval` | AirMonitor2 Update Interval | загружена | s |
| `select.airmonitor2_etvoc_unit` | AirMonitor2 eTVOC Unit | загружена | — |
| `sensor.airmonitor2_battery` | AirMonitor2 Battery | загружена | % / battery |
| `sensor.airmonitor2_battery_state` | AirMonitor2 Battery State | загружена | — |
| `sensor.airmonitor2_co2` | AirMonitor2 CO2 | загружена | ppm / carbon_dioxide |
| `sensor.airmonitor2_etvoc` | AirMonitor2 eTVOC | загружена | volatile_organic_compounds |
| `sensor.airmonitor2_firmware` | AirMonitor2 Firmware | загружена | — |
| `sensor.airmonitor2_humidity` | AirMonitor2 Humidity | загружена | % / humidity |
| `sensor.airmonitor2_mac_address` | AirMonitor2 MAC Address | загружена | — |
| `sensor.airmonitor2_noise` | AirMonitor2 Noise | загружена | dB / sound_pressure |
| `sensor.airmonitor2_pm10` | AirMonitor2 PM10 | загружена | μg/m³ / pm10 |
| `sensor.airmonitor2_pm25` | AirMonitor2 PM25 | загружена | μg/m³ / pm25 |
| `sensor.airmonitor2_report_type` | AirMonitor2 Report Type | загружена | — |
| `sensor.airmonitor2_status` | AirMonitor2 Status | загружена | — |
| `sensor.airmonitor2_temperature` | AirMonitor2 Temperature | загружена | °C / temperature |
### Bedroom Curtain

- Производитель: Aqara.
- Модель: AM001.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 36.
- Аппаратная версия: 17.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.curtain_identify` | Curtain Identify | отключена: user; нет в states | identify |
| `cover.bedroom_curtain` | Шторы в спальне | загружена | — |
### Bedroom Desktop Lights

- Производитель: Aqara.
- Модель: AK074.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.bedroom_desktop_bright_light` | Яркий свет | загружена | — |
| `switch.bedroom_desktop_dimmed_light` | Приглушенный свет | загружена | — |
### Bedroom Lights

- Производитель: Aqara.
- Модель: AK074.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_2` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.bedroom_bright_light` | Яркий | загружена | — |
| `switch.bedroom_dimmed_light` | Приглушенный свет | загружена | — |
### Bedroom Mirror Backlight

- Производитель: Aqara.
- Модель: AK073.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_8` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.bedroom_mirror_backlight` | Подсветка зеркала | загружена | — |
### Bedroom Radiator Thermostat

- Производитель: Aqara.
- Модель: AA006.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1030.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.spalnia_bedroom_radiator_thermostat_smart_radiator_thermostat_e1_problem` | Bedroom Radiator Thermostat Smart Radiator Thermostat E1 Problem | загружена | problem |
| `button.aqara_e1_thermostat_bedroom_identify` | Bedroom Radiator Thermostat Identify | отключена: user; нет в states | identify |
| `climate.bedroom_radiator_thermostat` | Батарея в спальне | загружена | — |
| `sensor.bedroom_radiator_current_temperature` | Bedroom Radiator Thermostat Current Temperature | загружена | °C / temperature |
| `sensor.bedroom_radiator_thermostat_battery` | Батарея термостата | загружена | % / battery |
### Bedroom Track L

- Производитель: Aqara.
- Модель: AK073.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_13` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.bedroom_track_l` | Трек в спальне - Лина | загружена | — |
### Bedroom Track R

- Производитель: Aqara.
- Модель: AK073.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_14` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.bedroom_track_r` | Трек в спальне - Миша | загружена | — |
### Desktop PC

- Производитель: Ping.
- Модель: —.
- Интеграции: ping.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.ping_desktop_pc` | Desktop PC | загружена | connectivity |
| `device_tracker.192_168_1_95` | Desktop PC | отключена: integration; нет в states | — |
### HDMI Hub

- Производитель: Aqara.
- Модель: AU001.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 0030.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.relay_controler_identify_4` | HDMI Hub Identify | отключена: user; нет в states | identify |
| `switch.hdmi_hub` | HDMI Hub | загружена | — |
### Meross Ambient Light L

- Производитель: Meross.
- Модель: msl430-un.
- Интеграции: meross_lan.
- Версия ПО, прочитана 2026-11-09: 4.2.6.
- Аппаратная версия: 4.0.0.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.meross_abmient_light_2_refresh` | Обновление | отключена: user; нет в states | update |
| `button.meross_abmient_light_2_reload` | Перезапустить | отключена: user; нет в states | restart |
| `light.meross_ambient_light_2_dnd` | Dnd | отключена: user; нет в states | — |
| `light.meross_ambient_light_l` | Цветной светильник слева | загружена | — |
| `sensor.meross_ambient_light_2_sensor_protocol` | Protocol | отключена: integration; нет в states | enum |
| `sensor.meross_ambient_light_2_signal_strength` | Signal strength | отключена: user; нет в states | % |
### Meross Ambient Light R

- Производитель: Meross.
- Модель: msl430-un.
- Интеграции: meross_lan.
- Версия ПО, прочитана 2026-11-09: 4.2.6.
- Аппаратная версия: 4.0.0.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.meross_ambient_light_1_refresh` | Обновление | отключена: user; нет в states | update |
| `button.meross_ambient_light_1_reload` | Перезапустить | отключена: user; нет в states | restart |
| `light.meross_ambient_light_1_dnd` | Dnd | отключена: user; нет в states | — |
| `light.meross_ambient_light_r` | Цветной светильник справа | загружена | — |
| `sensor.meross_ambient_light_1_sensor_protocol` | Protocol | отключена: integration; нет в states | enum |
| `sensor.meross_ambient_light_1_signal_strength` | Signal strength | отключена: user; нет в states | % |
### PC Power Button

- Производитель: Espressif.
- Модель: esp32-c3.
- Интеграции: esphome.
- Версия ПО, прочитана 2026-11-09: 2026.7.3 (2026-09-24 12:18:07 +0300).

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.esp_pc_force_shutdown` | PC Power Button PC Force Shutdown | загружена | — |
| `button.esp_pc_power_button` | PC Power Button PC Power Button | загружена | — |
| `button.esp_rgb_test` | PC Power Button RGB Test | загружена | — |
### PC Power Switch

Примечание владельца: Aqara AR023 в старом ПК; сейчас не используется. Владелец 2026-11-09 явно указал ничего с ним сейчас не делать.

- Производитель: Aqara.
- Модель: AR023.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 0035.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.dual_relay_module_t2_identify` | PC Power Switch Identify | отключена: user; нет в states | identify |
| `switch.aqara_t2_ch2_nc` | NC | отключена: user; нет в states | — |
| `switch.pc_power_switch` | Компьютер | загружена | — |
### Кондиционер

- Производитель: HAIER.
- Модель: AS20PS1HRA-M.
- Интеграции: yandex_station.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `climate.spalnia_haier_white` | Кондиционер УДЯ - Спальня | загружена | — |
| `number.spalnia_haier_white_temperatura` | Кондиционер Температура | загружена | °C |
| `select.spalnia_haier_white_bedroom_termostat` | Кондиционер Термостат | загружена | — |
| `select.spalnia_haier_white_napravlenie_vozdukha` | Кондиционер Направление воздуха | загружена | — |
| `select.spalnia_haier_white_skorost_ventiliatsii` | Кондиционер Скорость вентиляции | загружена | — |
| `switch.spalnia_haier_white_podsvetka` | Кондиционер Подсветка | загружена | — |
### Лава-лампа

- Производитель: Tuya.
- Модель: Dimmer Switch.
- Интеграции: tuya.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `light.lava_lamp` | Лава-лампа | загружена | — |
| `number.lava_lamp_brightness` | Максимальная яркость | загружена | — |
| `number.lava_lamp_minimum_brightness` | Минимальная яркость | загружена | — |
| `select.lava_lamp_power_on_behavior` | Лава-лампа Поведение при запуске | загружена | — |
### Проектор звездное небо

- Производитель: Tuya.
- Модель: Smart-Star-Projector .
- Интеграции: tuya.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `light.stars_projector` | Проектор звездное небо | загружена | — |
### Станция Мини White

- Производитель: Яндекс.
- Модель: Станция Мини 2 (2021).
- Интеграции: yandex_station.
- Версия ПО, прочитана 2026-11-09: 0.374.1.20.4835226640.20261106.304.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `calendar.yandex_station_m00db3710dqrsg_calendar` | Станция Мини White Будильники | отключена: integration; нет в states | — |
| `camera.yandex_station_m00db3710dqrsg_lyrics` | Станция Мини White Текст | отключена: integration; нет в states | — |
| `conversation.stantsiia_mini_white_alisa` | Станция Мини White Алиса | отключена: integration; нет в states | — |
| `media_player.yandex_station_m00db3710dqrsg` | Станция Мини White | загружена | — |
| `select.yandex_station_m00db3710dqrsg_equalizer` | Станция Мини White Эквалайзер | отключена: integration; нет в states | — |
### Трек в спальне Tuya - Лина

- Производитель: Tuya.
- Модель: 1000-DB-100.
- Интеграции: tuya.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `light.bedroom_1000_db_100_l` | Трек в спальне Tuya - Лина | загружена | — |
### Трек в спальне Tuya - Миша

- Производитель: Tuya.
- Модель: 1000-DB-100.
- Интеграции: tuya.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `light.bedroom_1000_db_100_r` | Трек в спальне Tuya - Миша | загружена | — |

## Детская

### Kids Room Curtain

- Производитель: Aqara.
- Модель: AM001.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 36.
- Аппаратная версия: 17.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.curtain_identify_3` | Curtain Identify | отключена: user; нет в states | identify |
| `cover.kids_room_curtain` | Шторы в детской | загружена | — |
### Kids Room Desktop Light

- Производитель: Aqara.
- Модель: AK073.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_12` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.kids_room_desktop_light` | Рабочий стол в детской | загружена | — |
### Kids Room Light

- Производитель: Aqara.
- Модель: AK073.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_10` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.kids_room_light` | Яркий свет в детской | загружена | — |
### Kids Room Radiator Thermostat

- Производитель: Aqara.
- Модель: AA006.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1030.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.detskaia_kids_room_radiator_thermostat_smart_radiator_thermostat_e1_problem` | Kids Room Radiator Thermostat Smart Radiator Thermostat E1 Problem | загружена | problem |
| `button.smart_radiator_thermostat_e1_identify_2` | Smart Radiator Thermostat E1 Identify | отключена: user; нет в states | identify |
| `climate.kids_room_radiator_thermostat` | Батарея в детской | загружена | — |
| `sensor.kids_room_radiator_thermostat_battery` | Батарея термостата | загружена | % / battery |
| `sensor.kids_room_radiator_thermostat_current_temperature` | Kids Room Radiator Thermostat Current Temperature | загружена | °C / temperature |
### Kids Room T1 Sensor

- Производитель: Aqara.
- Модель: Temperature and humidity sensor T1.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: 2019 www..
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.0x54ef44100150c9c8_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.0x54ef44100150c9c8_power_outage_count` | Power outage count | отключена: integration; нет в states | — |
| `sensor.kids_room_humidity` | Влажность в детской | загружена | % / humidity |
| `sensor.kids_room_pressure` | Давление в детской | загружена | mmHg / atmospheric_pressure |
| `sensor.kids_room_t1_battery` | Kids Room T1 Sensor Батарея | загружена | % / battery |
| `sensor.kids_room_t1_sensor_device_temperature` | Температура | отключена: user; нет в states | °C / temperature |
| `sensor.kids_room_t1_sensor_voltage` | Напряжение | отключена: user; нет в states | mV / voltage |
| `sensor.kids_room_temperature` | Температура в детской | загружена | °C / temperature |
| `update.kids_room_t1_sensor` | Kids Room T1 Sensor | загружена | firmware |
### Kids Room Track

- Производитель: Aqara.
- Модель: AK073.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_11` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.kids_room_track` | Трек в детской | загружена | — |
### Кондиционер

- Производитель: HAIER.
- Модель: AS20PS1HRA-M.
- Интеграции: yandex_station.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `climate.detskaia_haier_white` | Кондиционер УДЯ - Детская | загружена | — |
| `number.detskaia_haier_white_temperatura` | Кондиционер Температура | загружена | °C |
| `select.detskaia_haier_white_napravlenie_vozdukha` | Кондиционер Направление воздуха | загружена | — |
| `select.detskaia_haier_white_skorost_ventiliatsii` | Кондиционер Скорость вентиляции | загружена | — |
| `select.detskaia_konditsioner_termostat` | Кондиционер Термостат | загружена | — |
| `switch.detskaia_haier_white_podsvetka` | Кондиционер Подсветка | загружена | — |
### Трек в детской

- Производитель: Tuya.
- Модель: 1000-DB-100.
- Интеграции: tuya.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `light.kids_room_1000_db_100` | Трек в детской | загружена | — |

## Коридор

### Air Conditioner System Relay

- Производитель: Tomzn.
- Модель: Smart circuit breaker.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.air_conditioner_system_relay_identify` | Air Conditioner System Relay Идентификация | загружена | identify |
| `number.air_conditioner_system_relay_countdown` | Air Conditioner System Relay Countdown | загружена | s |
| `number.air_conditioner_system_relay_over_current_threshold` | Air Conditioner System Relay Over current threshold | загружена | A |
| `number.air_conditioner_system_relay_over_voltage_threshold` | Air Conditioner System Relay Over voltage threshold | загружена | V |
| `number.air_conditioner_system_relay_power_threshold` | Air Conditioner System Relay Power threshold | загружена | kW |
| `number.air_conditioner_system_relay_under_voltage_threshold` | Air Conditioner System Relay Under voltage threshold | загружена | V |
| `select.air_conditioner_system_relay_indicator_mode` | Air Conditioner System Relay Indicator mode | загружена | — |
| `select.air_conditioner_system_relay_power_outage_memory` | Air Conditioner System Relay Power outage memory | загружена | — |
| `sensor.0x403059fffebd3c59_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.air_conditioner_system_relay_current` | Air Conditioner System Relay Ток | загружена | A / current |
| `sensor.air_conditioner_system_relay_energy` | Air Conditioner System Relay Энергия | загружена | kWh / energy |
| `sensor.air_conditioner_system_relay_power` | Air Conditioner System Relay Мощность | загружена | W / power |
| `sensor.air_conditioner_system_relay_voltage` | Air Conditioner System Relay Напряжение | загружена | V / voltage |
| `switch.air_conditioner_system_relay` | Air Conditioner System Relay | загружена | — |
| `switch.air_conditioner_system_relay_child_lock` | Air Conditioner System Relay Child lock | загружена | — |
| `switch.air_conditioner_system_relay_over_current_breaker` | Air Conditioner System Relay Over current breaker | загружена | — |
| `switch.air_conditioner_system_relay_over_voltage_breaker` | Air Conditioner System Relay Over voltage breaker | загружена | — |
| `switch.air_conditioner_system_relay_power_breaker` | Air Conditioner System Relay Power breaker | загружена | — |
| `switch.air_conditioner_system_relay_under_voltage_breaker` | Air Conditioner System Relay Under voltage breaker | загружена | — |
| `update.air_conditioner_system_relay` | Air Conditioner System Relay | загружена | firmware |
### Aqara Smart Lock U200

- Производитель: Aqara.
- Модель: Aqara Smart Lock U200.
- Интеграции: matter.
- Версия ПО, прочитана 2026-11-09: 085.
- Аппаратная версия: 1.0.0.0.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.aqara_smart_lock_u200_actuator` | Aqara Smart Lock U200 Actuator | загружена | — |
| `binary_sensor.koridor_aqara_smart_lock_u200_hardware_faults` | Hardware faults | отключена: integration; нет в states | problem |
| `binary_sensor.koridor_aqara_smart_lock_u200_network_faults` | Network faults | отключена: integration; нет в states | problem |
| `binary_sensor.koridor_aqara_smart_lock_u200_radio_faults` | Radio faults | отключена: integration; нет в states | problem |
| `button.aqara_smart_lock_u200_identifikatsiia` | Aqara Smart Lock U200 Идентификация | загружена | identify |
| `lock.aqara_smart_lock_u200` | Aqara Smart Lock U200 | загружена | — |
| `number.aqara_smart_lock_u200_user_code_temporary_disable_time` | Aqara Smart Lock U200 User code temporary disable time | загружена | s |
| `number.aqara_smart_lock_u200_wrong_code_limit` | Aqara Smart Lock U200 Wrong code limit | загружена | — |
| `select.aqara_smart_lock_u200_rezhim_raboty` | Aqara Smart Lock U200 Режим работы | загружена | — |
| `sensor.aqara_smart_lock_u200_batareia` | Aqara Smart Lock U200 Батарея | загружена | % / battery |
| `sensor.aqara_smart_lock_u200_battery_voltage` | Aqara Smart Lock U200 Battery voltage | загружена | V / voltage |
| `sensor.koridor_aqara_smart_lock_u200_boot_reason` | Boot reason | отключена: integration; нет в states | enum |
| `sensor.koridor_aqara_smart_lock_u200_reboot_count` | Reboot count | отключена: integration; нет в states | — |
| `sensor.koridor_aqara_smart_lock_u200_uptime` | Uptime | отключена: integration; нет в states | uptime |
| `switch.koridor_aqara_smart_lock_u200_one_touch_locking` | Aqara Smart Lock U200 One-touch locking | загружена | — |
| `update.aqara_smart_lock_u200_obnovlenie_proshivki` | Aqara Smart Lock U200 Обновление прошивки | загружена | firmware |
### Electricity Outage Sensor

- Производитель: Aqara.
- Модель: AS012.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 0030.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.electricity_outage_sensor` | Датчик 220В | загружена | opening |
| `button.contact_sensor_identify` | Contact Sensor Identify | отключена: user; нет в states | identify |
| `sensor.electricity_outage_sensor_battery` | Electricity Outage Sensor Contact Sensor Battery Sensor | загружена | % / battery |
### Hall Collector Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.hall_collector_water_leak_sensor` | Протечка в коллекторе в коридоре | загружена | moisture |
| `binary_sensor.koridor_hall_collector_water_leak_sensor_water_leak_sensor_problem` | Hall Collector Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.hall_collector_water_leak_sensor_battery` | Hall Collector Water Leak Sensor Water Leak Sensor Battery Sensor | загружена | % / battery |
### Hall Door Sensor

- Производитель: Aqara.
- Модель: AS006.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 3.
- Аппаратная версия: 1.0.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.hall_contact_sensor` | Датчик входной двери | загружена | opening |
| `button.contact_sensor_identify_3` | Contact Sensor Identify | отключена: user; нет в states | identify |
| `sensor.hall_contact_sensor_battery` | Hall Door Sensor Contact Sensor Battery Sensor | загружена | % / battery |
### Hall T1 Sensor

- Производитель: Aqara.
- Модель: Temperature and humidity sensor T1.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.0x54ef441000821570_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.0x54ef441000821570_power_outage_count` | Power outage count | отключена: integration; нет в states | — |
| `sensor.hall_humidity` | Влажность в коридоре | загружена | % / humidity |
| `sensor.hall_pressure` | Давление в коридоре | загружена | mmHg / atmospheric_pressure |
| `sensor.hall_t1_battery` | Hall T1 Sensor Батарея | загружена | % / battery |
| `sensor.hall_t1_sensor_device_temperature` | Температура | отключена: user; нет в states | °C / temperature |
| `sensor.hall_t1_sensor_voltage` | Напряжение | отключена: user; нет в states | mV / voltage |
| `sensor.hall_temperature` | Температура в коридоре | загружена | °C / temperature |
| `update.hall_t1_sensor` | Hall T1 Sensor | загружена | firmware |
### Hall Under Wardrobe Socket

- Производитель: BSEED.
- Модель: Wall-mounted electrical EU/FR/UK socket with power monitoring.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.hall_under_wardrobe_socket_identify` | Hall Under Wardrobe Socket Идентификация | загружена | identify |
| `number.hall_under_wardrobe_socket_countdown` | Hall Under Wardrobe Socket Countdown | загружена | s |
| `select.hall_under_wardrobe_socket_indicator_mode` | Hall Under Wardrobe Socket Indicator mode | загружена | — |
| `select.hall_under_wardrobe_socket_power_outage_memory` | Hall Under Wardrobe Socket Power outage memory | загружена | — |
| `select.hall_under_wardrobe_socket_switch_type_button` | Hall Under Wardrobe Socket Switch type button | загружена | — |
| `sensor.hall_under_wardrobe_socket_current` | Hall Under Wardrobe Socket Ток | загружена | A / current |
| `sensor.hall_under_wardrobe_socket_energy` | Hall Under Wardrobe Socket Энергия | загружена | kWh / energy |
| `sensor.hall_under_wardrobe_socket_linkquality` | Hall Under Wardrobe Socket Linkquality | загружена | lqi |
| `sensor.hall_under_wardrobe_socket_power` | Hall Under Wardrobe Socket Мощность | загружена | W / power |
| `sensor.hall_under_wardrobe_socket_voltage` | Hall Under Wardrobe Socket Напряжение | загружена | V / voltage |
| `switch.hall_under_wardrobe_socket` | Розетка под шкафом | загружена | outlet |
| `switch.hall_under_wardrobe_socket_child_lock` | Hall Under Wardrobe Socket Child lock | загружена | — |
| `update.hall_under_wardrobe_socket` | Hall Under Wardrobe Socket | загружена | firmware |
### Hall Wall Switch 1

- Производитель: Aqara.
- Модель: AK074.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_5` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.hall_track_part_1` | Свет в коридоре 1 | загружена | — |
| `switch.hall_wardrobe_light` | Подсветка шкафа | загружена | — |
### Hall Wall Switch 2

- Производитель: Aqara.
- Модель: AK074.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_4` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.hall_track_part_2` | Свет в коридоре 2 | загружена | — |
| `switch.living_room_bright_light` | Яркий свет в гостиной | загружена | — |
### Hall Wall Switch 3

- Производитель: Aqara.
- Модель: AK074.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_3` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.kitchen_dinner_table` | Обеденный стол | загружена | — |
| `switch.living_room_dimmed_light` | Подсветка | загружена | — |
### Humidifier System Relay

- Производитель: Tomzn.
- Модель: Smart circuit breaker.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.humidifier_system_relay_identify` | Humidifier System Relay Идентификация | загружена | identify |
| `number.humidifier_system_relay_countdown` | Humidifier System Relay Countdown | загружена | s |
| `number.humidifier_system_relay_over_current_threshold` | Humidifier System Relay Over current threshold | загружена | A |
| `number.humidifier_system_relay_over_voltage_threshold` | Humidifier System Relay Over voltage threshold | загружена | V |
| `number.humidifier_system_relay_power_threshold` | Humidifier System Relay Power threshold | загружена | kW |
| `number.humidifier_system_relay_under_voltage_threshold` | Humidifier System Relay Under voltage threshold | загружена | V |
| `select.humidifier_system_relay_indicator_mode` | Humidifier System Relay Indicator mode | загружена | — |
| `select.humidifier_system_relay_power_outage_memory` | Humidifier System Relay Power outage memory | загружена | — |
| `sensor.0x94b216fffef5b66e_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.humidifier_system_relay_current` | Humidifier System Relay Ток | загружена | A / current |
| `sensor.humidifier_system_relay_energy` | Humidifier System Relay Энергия | загружена | kWh / energy |
| `sensor.humidifier_system_relay_power` | Humidifier System Relay Мощность | загружена | W / power |
| `sensor.humidifier_system_relay_voltage` | Humidifier System Relay Напряжение | загружена | V / voltage |
| `switch.humidifier_system_relay` | Humidifier System Relay | загружена | — |
| `switch.humidifier_system_relay_child_lock` | Humidifier System Relay Child lock | загружена | — |
| `switch.humidifier_system_relay_over_current_breaker` | Humidifier System Relay Over current breaker | загружена | — |
| `switch.humidifier_system_relay_over_voltage_breaker` | Humidifier System Relay Over voltage breaker | загружена | — |
| `switch.humidifier_system_relay_power_breaker` | Humidifier System Relay Power breaker | загружена | — |
| `switch.humidifier_system_relay_under_voltage_breaker` | Humidifier System Relay Under voltage breaker | загружена | — |
| `update.humidifier_system_relay` | Humidifier System Relay | загружена | firmware |
### Kitchen Water Valve

- Производитель: Aqara.
- Модель: AK027.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 47.
- Аппаратная версия: 19.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.relay_controler_identify_2` | Relay controler Identify | отключена: user; нет в states | identify |
| `switch.kitchen_water_valve_close` | Закрыть | загружена | — |
| `switch.kitchen_water_valve_open` | Открыть | загружена | — |
### Smoke Sensor

- Производитель: Aqara.
- Модель: AS018.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 0019.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.koridor_smoke_sensor_problem` | Smoke Sensor Problem | загружена | problem |
| `binary_sensor.smoke_sensor` | Датчик дыма | загружена | smoke |
| `button.vibration_sensor_identify` | Smoke Sensor Identify | отключена: user; нет в states | identify |
| `sensor.smoke_sensor_battery` | Батарея датчика дыма | загружена | % / battery |
### Ventilation System Relay

- Производитель: Tomzn.
- Модель: Smart circuit breaker.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.ventilation_system_relay_identify` | Ventilation System Relay Идентификация | загружена | identify |
| `number.ventilation_system_relay_countdown` | Ventilation System Relay Countdown | загружена | s |
| `number.ventilation_system_relay_over_current_threshold` | Ventilation System Relay Over current threshold | загружена | A |
| `number.ventilation_system_relay_over_voltage_threshold` | Ventilation System Relay Over voltage threshold | загружена | V |
| `number.ventilation_system_relay_power_threshold` | Ventilation System Relay Power threshold | загружена | kW |
| `number.ventilation_system_relay_under_voltage_threshold` | Ventilation System Relay Under voltage threshold | загружена | V |
| `select.ventilation_system_relay_indicator_mode` | Ventilation System Relay Indicator mode | загружена | — |
| `select.ventilation_system_relay_power_outage_memory` | Ventilation System Relay Power outage memory | загружена | — |
| `sensor.0x403059fffebd33f7_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.ventilation_system_relay_current` | Ventilation System Relay Ток | загружена | A / current |
| `sensor.ventilation_system_relay_energy` | Ventilation System Relay Энергия | загружена | kWh / energy |
| `sensor.ventilation_system_relay_power` | Ventilation System Relay Мощность | загружена | W / power |
| `sensor.ventilation_system_relay_voltage` | Ventilation System Relay Напряжение | загружена | V / voltage |
| `switch.ventilation_system_relay` | Ventilation System Relay | загружена | — |
| `switch.ventilation_system_relay_child_lock` | Ventilation System Relay Child lock | загружена | — |
| `switch.ventilation_system_relay_over_current_breaker` | Ventilation System Relay Over current breaker | загружена | — |
| `switch.ventilation_system_relay_over_voltage_breaker` | Ventilation System Relay Over voltage breaker | загружена | — |
| `switch.ventilation_system_relay_power_breaker` | Ventilation System Relay Power breaker | загружена | — |
| `switch.ventilation_system_relay_under_voltage_breaker` | Ventilation System Relay Under voltage breaker | загружена | — |
| `update.ventilation_system_relay` | Ventilation System Relay | загружена | firmware |
### Zemismart SMP01

- Производитель: Tuya.
- Модель: Smart energy monitor for 1P+N system.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee module: 1.0.10, MCU module: 3.2.2.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `number.zemismart_smp01_data_report_duration` | Zemismart SMP01 Data report duration | загружена | s |
| `sensor.zemismart_smp01_ac_frequency` | Zemismart SMP01 Частота | загружена | Hz / frequency |
| `sensor.zemismart_smp01_current` | Zemismart SMP01 Ток | загружена | A / current |
| `sensor.zemismart_smp01_energy` | Zemismart SMP01 Энергия | загружена | kWh / energy |
| `sensor.zemismart_smp01_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.zemismart_smp01_power` | Zemismart SMP01 Мощность | загружена | kW / power |
| `sensor.zemismart_smp01_power_factor` | Коэффициент мощности | отключена: integration; нет в states | % / power_factor |
| `sensor.zemismart_smp01_produced_energy` | Энергия | отключена: user; нет в states | kWh / energy |
| `sensor.zemismart_smp01_voltage` | Zemismart SMP01 Напряжение | загружена | V / voltage |

## Кладовка

### 3D Printer Motion Sensor

- Производитель: Tuya.
- Модель: Motion sensor.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.3d_printer_motion_sensor_battery_low` | Батарея | отключена: user; нет в states | battery |
| `binary_sensor.3d_printer_motion_sensor_occupancy` | 3D Printer Motion Sensor Занятость | загружена | occupancy |
| `binary_sensor.3d_printer_motion_sensor_tamper` | Вмешательство | отключена: user; нет в states | tamper |
| `sensor.0xa4c138a0d51668e0_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.3d_printer_motion_sensor_battery` | 3D Printer Motion Sensor Батарея | загружена | % / battery |
| `sensor.3d_printer_motion_sensor_voltage` | Напряжение | отключена: user; нет в states | mV / voltage |
### 3D Printer Plug

- Производитель: Tuya.
- Модель: Smart plug (with power monitoring).
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.3d_printer_plug_identify` | 3D Printer Plug Идентификация | загружена | identify |
| `number.3d_printer_plug_countdown` | 3D Printer Plug Countdown | загружена | s |
| `select.3d_printer_plug_indicator_mode` | 3D Printer Plug Indicator mode | загружена | — |
| `select.3d_printer_plug_power_outage_memory` | 3D Printer Plug Power outage memory | загружена | — |
| `select.3d_printer_plug_switch_type_button` | 3D Printer Plug Switch type button | загружена | — |
| `sensor.0xa4c1382f2b4f2b5a_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.3d_printer_plug_current` | 3D Printer Plug Ток | загружена | A / current |
| `sensor.3d_printer_plug_energy` | 3D Printer Plug Энергия | загружена | kWh / energy |
| `sensor.3d_printer_plug_power` | 3D Printer Plug Мощность | загружена | W / power |
| `sensor.3d_printer_plug_voltage` | 3D Printer Plug Напряжение | загружена | V / voltage |
| `switch.3d_printer_plug` | 3D Принтер | загружена | — |
| `switch.3d_printer_plug_child_lock` | 3D Printer Plug Child lock | загружена | — |
| `update.3d_printer_plug` | 3D Printer Plug | загружена | firmware |
### Aqara Hub E1 8F1B

- Производитель: Aqara.
- Модель: HE1-G01.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 4.5.30.
- Аппаратная версия: 1.0.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `alarm_control_panel.aqara_hub_e1_8f1b_security_system` | Aqara Hub E1 8F1B Security System | загружена | — |
| `button.aqara_hub_e1_8f1b_identify` | Aqara Hub E1 8F1B Identify | отключена: user; нет в states | identify |
| `switch.aqara_hub_e1_8f1b_pairing_mode` | Aqara-Hub-E1-8F1B Pairing Mode | отключена: user; нет в states | — |
### EFEKTA_Smart_AQ_Box

- Производитель: EfektaLab.
- Модель: [EFEKTA Smart Air Quality Box, PM1.0, PM2.5, PM10, AQ PM2.5 Index, PM Size, CO2, VOC Index, Pressure, Temperature, Humidity, ws2812b indicator, can control the relay, binding on some other devices](http://efektalab.com/Smart_Air_Quality_Box).
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: 1.0.6.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `number.efekta_smart_aq_box_auto_clean_interval` | EFEKTA_Smart_AQ_Box Auto clean interval | загружена | day |
| `number.efekta_smart_aq_box_high_co2` | EFEKTA_Smart_AQ_Box High co2 | загружена | ppm |
| `number.efekta_smart_aq_box_high_pm25` | EFEKTA_Smart_AQ_Box High pm25 | загружена | μg/m³ |
| `number.efekta_smart_aq_box_high_voc` | EFEKTA_Smart_AQ_Box High voc | загружена | index point |
| `number.efekta_smart_aq_box_humidity_offset` | EFEKTA_Smart_AQ_Box Humidity offset | загружена | % |
| `number.efekta_smart_aq_box_light_ind_level` | EFEKTA_Smart_AQ_Box Light ind level | загружена | % |
| `number.efekta_smart_aq_box_low_co2` | EFEKTA_Smart_AQ_Box Low co2 | загружена | ppm |
| `number.efekta_smart_aq_box_low_pm25` | EFEKTA_Smart_AQ_Box Low pm25 | загружена | μg/m³ |
| `number.efekta_smart_aq_box_low_voc` | EFEKTA_Smart_AQ_Box Low voc | загружена | index point |
| `number.efekta_smart_aq_box_manual_forced_recalibration` | EFEKTA_Smart_AQ_Box Manual forced recalibration | загружена | ppm |
| `number.efekta_smart_aq_box_reading_delay` | EFEKTA_Smart_AQ_Box Reading delay | загружена | Seconds |
| `number.efekta_smart_aq_box_temperature_offset` | EFEKTA_Smart_AQ_Box Temperature offset | загружена | °C |
| `sensor.efekta_smart_aq_box_aqi_25_index` | EFEKTA_Smart_AQ_Box PM25 Index | загружена | PM2.5 Index |
| `sensor.efekta_smart_aq_box_co2` | EFEKTA_Smart_AQ_Box Углекислый газ | загружена | ppm / carbon_dioxide |
| `sensor.efekta_smart_aq_box_humidity` | EFEKTA_Smart_AQ_Box Влажность | загружена | % / humidity |
| `sensor.efekta_smart_aq_box_linkquality` | EFEKTA_Smart_AQ_Box Linkquality | загружена | lqi |
| `sensor.efekta_smart_aq_box_pm1` | EFEKTA_Smart_AQ_Box PM1 | загружена | μg/m³ |
| `sensor.efekta_smart_aq_box_pm10` | EFEKTA_Smart_AQ_Box PM10 | загружена | μg/m³ / pm10 |
| `sensor.efekta_smart_aq_box_pm25` | EFEKTA_Smart_AQ_Box PM2.5 | загружена | μg/m³ / pm25 |
| `sensor.efekta_smart_aq_box_pm_size` | EFEKTA_Smart_AQ_Box PM Size | загружена | µm |
| `sensor.efekta_smart_aq_box_pressure` | EFEKTA_Smart_AQ_Box Атмосферное давление | загружена | mmHg / atmospheric_pressure |
| `sensor.efekta_smart_aq_box_temperature` | EFEKTA_Smart_AQ_Box Температура | загружена | °C / temperature |
| `sensor.efekta_smart_aq_box_voc_index` | EFEKTA_Smart_AQ_Box VOC Index | загружена | VOC Index |
| `switch.efekta_smart_aq_box_alarm` | EFEKTA_Smart_AQ_Box Alarm | загружена | — |
| `switch.efekta_smart_aq_box_automatic_scal` | EFEKTA_Smart_AQ_Box Automatic scal | загружена | — |
| `switch.efekta_smart_aq_box_enable_co2` | EFEKTA_Smart_AQ_Box Enable co2 | загружена | — |
| `switch.efekta_smart_aq_box_enable_pm25` | EFEKTA_Smart_AQ_Box Enable pm25 | загружена | — |
| `switch.efekta_smart_aq_box_enable_voc` | EFEKTA_Smart_AQ_Box Enable voc | загружена | — |
| `switch.efekta_smart_aq_box_factory_reset_co2` | EFEKTA_Smart_AQ_Box Factory reset co2 | загружена | — |
| `switch.efekta_smart_aq_box_forced_recalibration` | EFEKTA_Smart_AQ_Box Forced recalibration | загружена | — |
| `switch.efekta_smart_aq_box_light_indicator` | EFEKTA_Smart_AQ_Box Light indicator | загружена | — |
| `switch.efekta_smart_aq_box_manual_clean` | EFEKTA_Smart_AQ_Box Manual clean | загружена | — |
### RIVER 3

- Производитель: EcoFlow.
- Модель: RIVER_3.
- Интеграции: ecoflow_cloud.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.river_3_reconnect` | RIVER 3 Reconnect | загружена | restart |
| `number.river_3_ac_charging_power` | RIVER 3 AC Charging Power | загружена | W / power |
| `number.river_3_backup_reserve_level` | Backup Reserve Level | отключена: user; нет в states | % |
| `number.river_3_max_charge_level` | RIVER 3 Max Charge Level | загружена | % |
| `number.river_3_min_discharge_level` | RIVER 3 Min Discharge Level | загружена | % |
| `select.river_3_ac_timeout` | AC Timeout | отключена: user; нет в states | — |
| `select.river_3_dc_12v_charge_current` | DC (12V) Charge Current | отключена: user; нет в states | — |
| `select.river_3_dc_mode` | DC Mode | отключена: user; нет в states | — |
| `select.river_3_screen_timeout` | Screen Timeout | отключена: user; нет в states | — |
| `select.river_3_unit_timeout` | Unit Timeout | отключена: user; нет в states | — |
| `sensor.river_3_ac_in_power` | RIVER 3 AC In Power | загружена | W / power |
| `sensor.river_3_ac_in_volts` | AC In Volts | отключена: user; нет в states | V / voltage |
| `sensor.river_3_ac_input_energy` | RIVER 3 AC Input Energy | загружена | Wh / energy |
| `sensor.river_3_ac_out_power` | RIVER 3 AC Out Power | загружена | W / power |
| `sensor.river_3_ac_output_energy` | RIVER 3 AC Output Energy | загружена | Wh / energy |
| `sensor.river_3_battery_charging_state` | RIVER 3 Battery Charging State | загружена | — |
| `sensor.river_3_battery_level` | RIVER 3 Battery Level | загружена | % / battery |
| `sensor.river_3_battery_temperature` | RIVER 3 Battery Temperature | загружена | °C / temperature |
| `sensor.river_3_battery_volts` | Battery Volts | отключена: integration; скрыта: integration; нет в states | V / voltage |
| `sensor.river_3_charge_remaining_time` | RIVER 3 Charge Remaining Time | загружена | min / duration |
| `sensor.river_3_cycles` | RIVER 3 Cycles | загружена | — |
| `sensor.river_3_dc_12v_output_energy` | DC 12V Output Energy | отключена: integration; скрыта: integration; нет в states | Wh / energy |
| `sensor.river_3_dc_out_power` | RIVER 3 DC Out Power | загружена | W / power |
| `sensor.river_3_discharge_remaining_time` | RIVER 3 Discharge Remaining Time | загружена | min / duration |
| `sensor.river_3_main_battery_level` | Main Battery Level | отключена: user; нет в states | % / battery |
| `sensor.river_3_main_design_capacity` | Main Design Capacity | отключена: integration; скрыта: integration; нет в states | mAh |
| `sensor.river_3_main_full_capacity` | Main Full Capacity | отключена: integration; скрыта: integration; нет в states | mAh |
| `sensor.river_3_main_remain_capacity` | Main Remain Capacity | отключена: integration; скрыта: integration; нет в states | mAh |
| `sensor.river_3_max_cell_temperature` | Max Cell Temperature | отключена: integration; скрыта: integration; нет в states | °C / temperature |
| `sensor.river_3_max_cell_volts` | Max Cell Volts | отключена: integration; скрыта: integration; нет в states | V / voltage |
| `sensor.river_3_min_cell_volts` | Min Cell Volts | отключена: integration; скрыта: integration; нет в states | V / voltage |
| `sensor.river_3_pcs_ac_temperature` | RIVER 3 PCS AC Temperature | загружена | °C / temperature |
| `sensor.river_3_pcs_dc_temperature` | RIVER 3 PCS DC Temperature | загружена | °C / temperature |
| `sensor.river_3_power_difference` | RIVER 3 Power Difference | загружена | W / power |
| `sensor.river_3_remaining_time` | RIVER 3 Remaining Time | загружена | min / duration |
| `sensor.river_3_solar_in_current` | Solar In Current | отключена: user; нет в states | mA / current |
| `sensor.river_3_solar_in_energy` | Solar In Energy | отключена: user; нет в states | Wh / energy |
| `sensor.river_3_solar_in_power` | Solar In Power | отключена: user; нет в states | W / power |
| `sensor.river_3_state_of_health` | RIVER 3 State of Health | загружена | % |
| `sensor.river_3_status` | RIVER 3 Status | загружена | — |
| `sensor.river_3_total_in_energy` | RIVER 3 Total In  Energy | скрыта: integration | energy |
| `sensor.river_3_total_in_power` | RIVER 3 Total In Power | загружена | W / power |
| `sensor.river_3_total_out_energy` | RIVER 3 Total Out  Energy | скрыта: integration | energy |
| `sensor.river_3_total_out_power` | RIVER 3 Total Out Power | загружена | W / power |
| `sensor.river_3_type_c_1_out_power` | RIVER 3 Type-C (1) Out Power | загружена | W / power |
| `sensor.river_3_type_c_output_energy` | Type-C Output Energy | отключена: integration; скрыта: integration; нет в states | Wh / energy |
| `sensor.river_3_usb_a_output_energy` | USB-A Output Energy | отключена: integration; скрыта: integration; нет в states | Wh / energy |
| `sensor.river_3_usb_qc_1_out_power` | RIVER 3 USB QC (1) Out Power | загружена | W / power |
| `sensor.river_3_usb_qc_2_out_power` | RIVER 3 USB QC (2) Out Power | загружена | W / power |
| `switch.river_3_ac_always_on` | AC Output Memory | отключена: user; нет в states | — |
| `switch.river_3_ac_enabled` | RIVER 3 AC Enabled | загружена | — |
| `switch.river_3_backup_reserve_enabled` | Backup Reserve Enabled | отключена: user; нет в states | — |
| `switch.river_3_beeper` | Beeper | отключена: user; нет в states | — |
| `switch.river_3_dc_12v_enabled` | RIVER 3 DC (12V) Enabled | загружена | — |
| `switch.river_3_x_boost_enabled` | X-Boost Enabled | отключена: user; нет в states | — |
### Store Room Socket

- Производитель: BSEED.
- Модель: Wall-mounted electrical EU/FR/UK socket with power monitoring.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.store_room_socket_identify` | Store Room Socket Идентификация | загружена | identify |
| `number.store_room_socket_countdown` | Store Room Socket Countdown | загружена | s |
| `select.store_room_socket_indicator_mode` | Store Room Socket Indicator mode | загружена | — |
| `select.store_room_socket_power_outage_memory` | Store Room Socket Power outage memory | загружена | — |
| `select.store_room_socket_switch_type_button` | Store Room Socket Switch type button | загружена | — |
| `sensor.store_room_socket_current` | Store Room Socket Ток | загружена | A / current |
| `sensor.store_room_socket_energy` | Store Room Socket Энергия | загружена | kWh / energy |
| `sensor.store_room_socket_power` | Store Room Socket Мощность | загружена | W / power |
| `sensor.store_room_socket_voltage` | Store Room Socket Напряжение | загружена | V / voltage |
| `sensor.vertical_vacuum_cleaner_linkquality` | Linkquality | отключена: user; нет в states | lqi |
| `switch.store_room_socket` | Розетка в кладовке | загружена | — |
| `switch.store_room_socket_child_lock` | Store Room Socket Child lock | загружена | — |
| `update.store_room_socket` | Store Room Socket | загружена | firmware |
### Store Room Table Light

- Производитель: Aqara.
- Модель: AU001.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 0030.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.relay_controler_identify_5` | Relay controler Identify | отключена: user; нет в states | identify |
| `switch.store_room_table_light` | Свет над столом | загружена | — |
### Store Room Wall Switch

- Производитель: Aqara.
- Модель: AK073.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_6` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.store_room_light` | Свет в кладовке | загружена | — |
### Transmission

- Производитель: Transmission.
- Модель: —.
- Интеграции: transmission3.
- Версия ПО, прочитана 2026-11-09: 3.00 (ab47000043).

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `event.transmission_torrent` | Transmission torrent | загружена | — |
| `sensor.transmission_active_torrents` | Transmission active_torrents | загружена | — |
| `sensor.transmission_completed_torrents` | Transmission completed_torrents | загружена | — |
| `sensor.transmission_download_speed` | Transmission download_speed | загружена | MB/s / data_rate |
| `sensor.transmission_paused_torrents` | Transmission paused_torrents | загружена | — |
| `sensor.transmission_session_download` | Transmission session_download | загружена | GiB / data_size |
| `sensor.transmission_session_ratio` | Transmission session_ratio | загружена | — |
| `sensor.transmission_session_upload` | Transmission session_upload | загружена | GiB / data_size |
| `sensor.transmission_started_torrents` | Transmission started_torrents | загружена | — |
| `sensor.transmission_status` | Transmission status | загружена | enum |
| `sensor.transmission_total_download` | Transmission total_download | загружена | GiB / data_size |
| `sensor.transmission_total_ratio` | Transmission total_ratio | загружена | — |
| `sensor.transmission_total_torrents` | Transmission total_torrents | загружена | — |
| `sensor.transmission_total_upload` | Transmission total_upload | загружена | GiB / data_size |
| `sensor.transmission_upload_speed` | Transmission upload_speed | загружена | MB/s / data_rate |
| `switch.transmission_switch` | Transmission switch | загружена | — |
| `switch.transmission_turtle_mode` | Transmission turtle_mode | загружена | — |
### Пылесос

- Производитель: Roborock.
- Модель: Roborock Robotic Vacuum Cleaner.
- Интеграции: matter.
- Версия ПО, прочитана 2026-11-09: 1.4.
- Аппаратная версия: 1.4.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.kladovka_pylesos_identifikatsiia` | Пылесос Идентификация | загружена | identify |
| `select.kladovka_pylesos_rezhim_ochistki` | Пылесос Режим очистки | загружена | — |
| `sensor.kladovka_pylesos_batareia` | Пылесос Батарея | загружена | % / battery |
| `sensor.kladovka_pylesos_operational_error` | Пылесос Operational error | загружена | enum |
| `sensor.kladovka_pylesos_rabochee_sostoianie` | Пылесос Рабочее состояние | загружена | enum |
| `sensor.kladovka_pylesos_sostoianie_zariada_batarei` | Пылесос Состояние заряда батареи | загружена | enum |
| `sensor.kladovka_roborock_robotic_vacuum_cleaner_reboot_count` | Reboot count | отключена: integration; нет в states | — |
| `sensor.kladovka_roborock_robotic_vacuum_cleaner_uptime` | Uptime | отключена: integration; нет в states | uptime |
| `vacuum.roborock_robotic_vacuum_cleaner` | Пылесос | загружена | — |

## Ванная

### Bathroom Bath Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.bathroom_bath_water_leak_sensor` | Протечка под ванной | загружена | moisture |
| `binary_sensor.vannaia_bathroom_bath_water_leak_sensor_water_leak_sensor_problem` | Bathroom Bath Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify_3` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.bathroom_bath_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Bathroom Drain Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.bathroom_drain_water_leak_sensor` | Протечка у фановой трубы в ванной | загружена | moisture |
| `binary_sensor.vannaia_bathroom_drain_water_leak_sensor_water_leak_sensor_problem` | Bathroom Drain Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify_4` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.bathroom_drain_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Bathroom Heat Floor

- Производитель: Moes.
- Модель: Moes BHT series Thermostat.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `climate.bathroom_heat_floor` | Теплый пол в ванной | загружена | — |
| `number.bathroom_heat_floor_deadzone_temperature` | Bathroom Heat Floor Deadzone temperature | загружена | °C |
| `number.bathroom_heat_floor_local_temperature_calibration` | Bathroom Heat Floor Дельта температуры | загружена | °C / temperature_delta |
| `number.bathroom_heat_floor_max_temperature_limit` | Bathroom Heat Floor Max temperature limit | загружена | °C |
| `number.bathroom_heat_floor_min_temperature_limit` | Bathroom Heat Floor Min temperature limit | загружена | °C |
| `select.bathroom_heat_floor_sensor` | Bathroom Heat Floor Sensor | загружена | — |
| `sensor.bathroom_heat_floor_linkquality` | Bathroom Heat Floor Linkquality | загружена | lqi |
| `sensor.bathroom_heat_floor_local_temperature` | Bathroom Heat Floor Температура | загружена | °C / temperature |
| `sensor.bathroom_heat_floor_program` | Bathroom Heat Floor Program | загружена | — |
| `switch.bathroom_heat_floor_child_lock` | Bathroom Heat Floor Child lock | загружена | — |
### Bathroom Heat Wall

- Производитель: Moes.
- Модель: Moes BHT series Thermostat.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `climate.bathroom_heat_wall` | Теплая стена в ванной | загружена | — |
| `number.bathroom_heat_wall_deadzone_temperature` | Bathroom Heat Wall Deadzone temperature | загружена | °C |
| `number.bathroom_heat_wall_local_temperature_calibration` | Bathroom Heat Wall Дельта температуры | загружена | °C / temperature_delta |
| `number.bathroom_heat_wall_max_temperature_limit` | Bathroom Heat Wall Max temperature limit | загружена | °C |
| `number.bathroom_heat_wall_min_temperature_limit` | Bathroom Heat Wall Min temperature limit | загружена | °C |
| `select.bathroom_heat_wall_sensor` | Bathroom Heat Wall Sensor | загружена | — |
| `sensor.bathroom_heat_wall_linkquality` | Bathroom Heat Wall Linkquality | загружена | lqi |
| `sensor.bathroom_heat_wall_local_temperature` | Bathroom Heat Wall Температура | загружена | °C / temperature |
| `sensor.bathroom_heat_wall_program` | Bathroom Heat Wall Program | загружена | — |
| `switch.bathroom_heat_wall_child_lock` | Bathroom Heat Wall Child lock | загружена | — |
### Bathroom Installation Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.bathroom_installation_water_leak_sensor` | Протечка в инсталляции в ванной | загружена | moisture |
| `binary_sensor.vannaia_bathroom_installation_water_leak_sensor_water_leak_sensor_problem` | Bathroom Installation Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify_5` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.bathroom_installation_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Bathroom Lights

- Производитель: Aqara.
- Модель: AK074.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_16` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.bathroom_bright_light` | Яркий свет | загружена | — |
| `switch.bathroom_dimmed_light` | Приглушенный свет | загружена | — |
### Bathroom Sconce

- Производитель: Aqara.
- Модель: AK073.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_15` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.bathroom_sconce` | Бра в ванной | загружена | — |
### Bathroom Sink Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.bathroom_sink_water_leak_sensor` | Протечка под раковиной в ванной | загружена | moisture |
| `binary_sensor.vannaia_bathroom_sink_water_leak_sensor_water_leak_sensor_problem` | Bathroom Sink Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify_2` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.bathroom_sink_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Bathroom T1 Sensor

- Производитель: Aqara.
- Модель: Temperature and humidity sensor T1.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.0x54ef4410008213e3_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.0x54ef4410008213e3_power_outage_count` | Power outage count | отключена: integration; нет в states | — |
| `sensor.bathroom_humidity` | Влажность в ванной | загружена | % / humidity |
| `sensor.bathroom_pressure` | Давление в ванной | загружена | mmHg / atmospheric_pressure |
| `sensor.bathroom_t1_battery` | Bathroom T1 Sensor Батарея | загружена | % / battery |
| `sensor.bathroom_t1_sensor_device_temperature` | Температура | отключена: user; нет в states | °C / temperature |
| `sensor.bathroom_t1_sensor_voltage` | Напряжение | отключена: user; нет в states | mV / voltage |
| `sensor.bathroom_temperature` | Температура в ванной | загружена | °C / temperature |
| `update.bathroom_t1_sensor` | Bathroom T1 Sensor | загружена | firmware |
### Полотенцесушитель

- Производитель: Tuya.
- Модель: JC01-T.
- Интеграции: tuya.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `climate.towel_dryer` | Полотенцесушитель | загружена | — |
| `number.towel_dryer_temperature_correction` | Полотенцесушитель Коррекция температуры | загружена | ℃ |

## Прачечная

### Drying Machine

- Производитель: BSEED.
- Модель: Wall-mounted electrical EU/FR/UK socket with power monitoring.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.drying_machine_identify` | Drying Machine Идентификация | загружена | identify |
| `number.drying_machine_countdown` | Drying Machine Countdown | загружена | s |
| `select.drying_machine_indicator_mode` | Drying Machine Indicator mode | загружена | — |
| `select.drying_machine_power_outage_memory` | Drying Machine Power outage memory | загружена | — |
| `select.drying_machine_switch_type_button` | Drying Machine Switch type button | загружена | — |
| `sensor.0xa4c1389e034c86c7_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.drying_machine_current` | Drying Machine Ток | загружена | A / current |
| `sensor.drying_machine_energy` | Drying Machine Энергия | загружена | kWh / energy |
| `sensor.drying_machine_power` | Drying Machine Мощность | загружена | W / power |
| `sensor.drying_machine_voltage` | Drying Machine Напряжение | загружена | V / voltage |
| `switch.drying_machine` | Сушильная машина | загружена | — |
| `switch.drying_machine_child_lock` | Drying Machine Child lock | загружена | — |
| `update.drying_machine` | Drying Machine | загружена | firmware |
### Humidifier System Control Switch

- Производитель: MHCOZY.
- Модель: 4 channel relay.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `select.humidifier_system_control_switch_power_on_behavior_l1` | Humidifier System Control Switch Power-on behavior l1 | загружена | — |
| `select.humidifier_system_control_switch_power_on_behavior_l2` | Humidifier System Control Switch Power-on behavior l2 | загружена | — |
| `select.humidifier_system_control_switch_power_on_behavior_l3` | Humidifier System Control Switch Power-on behavior l3 | загружена | — |
| `select.humidity_control_4ch_switch_power_on_behavior_l4` | Power-on behavior l4 | отключена: user; нет в states | — |
| `sensor.humidifier_system_control_switch_linkquality` | Humidifier System Control Switch Linkquality | загружена | lqi |
| `switch.humidifier_system_control_switch_backlight_mode` | Humidifier System Control Switch Backlight mode | загружена | — |
| `switch.humidifier_system_control_switch_l1` | Увлажнение гостиная | загружена | — |
| `switch.humidifier_system_control_switch_l2` | Увлажнение спальня | загружена | — |
| `switch.humidifier_system_control_switch_l3` | Увлажнение детская | загружена | — |
| `switch.humidity_control_4ch_switch_l4` | L4 | отключена: user; нет в states | — |
### Laundry Collector Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.laundry_collector_water_leak_sensor` | Протечка в коллекторе в прачечной | загружена | moisture |
| `binary_sensor.prachechnaia_laundry_collector_water_leak_sensor_water_leak_sensor_problem` | Laundry Collector Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify_8` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.laundry_collector_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Laundry Heat Floor

- Производитель: Moes.
- Модель: Moes BHT series Thermostat.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `climate.laundry_heat_floor` | Теплый пол в прачечной | загружена | — |
| `number.laundry_heat_floor_deadzone_temperature` | Laundry Heat Floor Deadzone temperature | загружена | °C |
| `number.laundry_heat_floor_local_temperature_calibration` | Laundry Heat Floor Дельта температуры | загружена | °C / temperature_delta |
| `number.laundry_heat_floor_max_temperature_limit` | Laundry Heat Floor Max temperature limit | загружена | °C |
| `number.laundry_heat_floor_min_temperature_limit` | Laundry Heat Floor Min temperature limit | загружена | °C |
| `select.laundry_heat_floor_sensor` | Laundry Heat Floor Sensor | загружена | — |
| `sensor.laundry_heat_floor_linkquality` | Laundry Heat Floor Linkquality | загружена | lqi |
| `sensor.laundry_heat_floor_local_temperature` | Laundry Heat Floor Температура | загружена | °C / temperature |
| `sensor.laundry_heat_floor_program` | Laundry Heat Floor Program | загружена | — |
| `switch.laundry_heat_floor_child_lock` | Laundry Heat Floor Child lock | загружена | — |
### Laundry Humidifier Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.laundry_humidifier_water_leak_sensor` | Протечка в системе увлажнения | загружена | moisture |
| `binary_sensor.prachechnaia_laundry_humidifier_water_leak_sensor_water_leak_sensor_problem` | Laundry Humidifier Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.aqara_leak_sensor_1_identify` | Laundry Humidifier Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.laundry_humidifier_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Laundry Installation Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.laundry_installation_water_leak_sensor` | Протечка в инсталляции в прачечной | загружена | moisture |
| `binary_sensor.prachechnaia_laundry_installation_water_leak_sensor_water_leak_sensor_problem` | Laundry Installation Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify_9` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.laundry_installation_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Laundry Light

- Производитель: Aqara.
- Модель: AK074.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 1125.
- Аппаратная версия: 1.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.wall_switch_identify_7` | Wall Switch Identify | отключена: user; нет в states | identify |
| `switch.laundry_light` | Свет | загружена | — |
| `switch.wall_switch_switch2_6` | Wall Switch Switch2 | отключена: user; нет в states | — |
### Laundry Sink Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.laundry_sink_water_leak_sensor` | Протечка под раковиной в прачечной | загружена | moisture |
| `binary_sensor.prachechnaia_laundry_sink_water_leak_sensor_water_leak_sensor_problem` | Laundry Sink Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify_10` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.laundry_sink_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Laundry T1 Sensor

- Производитель: Aqara.
- Модель: Temperature and humidity sensor T1.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.0x54ef441000822af3_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.0x54ef441000822af3_power_outage_count` | Power outage count | отключена: integration; нет в states | — |
| `sensor.laundry_humidity` | Влажность в прачечной | загружена | % / humidity |
| `sensor.laundry_pressure` | Давление в прачечной | загружена | mmHg / atmospheric_pressure |
| `sensor.laundry_t1_battery` | Laundry T1 Sensor Батарея | загружена | % / battery |
| `sensor.laundry_t1_sensor_device_temperature` | Температура | отключена: user; нет в states | °C / temperature |
| `sensor.laundry_t1_sensor_voltage` | Напряжение | отключена: user; нет в states | mV / voltage |
| `sensor.laundry_temperature` | Температура в прачечной | загружена | °C / temperature |
| `update.laundry_t1_sensor` | Laundry T1 Sensor | загружена | firmware |
### Laundry Washing Machine Water Leak Sensor

- Производитель: Aqara.
- Модель: AS010.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 6.
- Аппаратная версия: 2.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.laundry_washing_machine_water_leak_sensor` | Протечка за стиральной машинкой | загружена | moisture |
| `binary_sensor.prachechnaia_laundry_washing_machine_water_leak_sensor_water_leak_sensor_problem` | Laundry Washing Machine Water Leak Sensor Water Leak Sensor Problem | загружена | problem |
| `button.water_leak_sensor_identify_11` | Water Leak Sensor Identify | отключена: user; нет в states | identify |
| `sensor.laundry_washing_machine_water_leak_sensor_battery` | Батарея датчика протечки | загружена | % / battery |
### Laundry Water Valve

- Производитель: Aqara.
- Модель: AK027.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 47.
- Аппаратная версия: 19.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.relay_controler_identify_3` | Relay controler Identify | отключена: user; нет в states | identify |
| `switch.laundry_water_valve_close` | Закрыть | загружена | — |
| `switch.laundry_water_valve_open` | Открыть | загружена | — |
### Washing Machine

- Производитель: BSEED.
- Модель: Wall-mounted electrical EU/FR/UK socket with power monitoring.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.washing_machine_identify` | Washing Machine Идентификация | загружена | identify |
| `number.washing_machine_countdown` | Countdown | отключена: user; нет в states | s |
| `select.washing_machine_indicator_mode` | Washing Machine Indicator mode | загружена | — |
| `select.washing_machine_power_outage_memory` | Washing Machine Power outage memory | загружена | — |
| `select.washing_machine_switch_type_button` | Washing Machine Switch type button | загружена | — |
| `sensor.0xa4c1380faa3fe216_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.washing_machine_current` | Washing Machine Ток | загружена | A / current |
| `sensor.washing_machine_energy` | Washing Machine Энергия | загружена | kWh / energy |
| `sensor.washing_machine_power` | Washing Machine Мощность | загружена | W / power |
| `sensor.washing_machine_voltage` | Washing Machine Напряжение | загружена | V / voltage |
| `switch.washing_machine` | Стиральная машина | загружена | — |
| `switch.washing_machine_child_lock` | Washing Machine Child lock | загружена | — |
| `update.washing_machine` | Washing Machine | загружена | firmware |

## Балкон

### Loggia Heat Floor

- Производитель: Moes.
- Модель: Moes BHT series Thermostat.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee module: 1.0.8, MCU module: 1.0.0.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `climate.loggia_heat_floor` | Теплый пол на балконе | загружена | — |
| `number.loggia_heat_floor_deadzone_temperature` | Loggia Heat Floor Deadzone temperature | загружена | °C |
| `number.loggia_heat_floor_local_temperature_calibration` | Loggia Heat Floor Дельта температуры | загружена | °C / temperature_delta |
| `number.loggia_heat_floor_max_temperature_limit` | Loggia Heat Floor Max temperature limit | загружена | °C |
| `number.loggia_heat_floor_min_temperature_limit` | Loggia Heat Floor Min temperature limit | загружена | °C |
| `select.loggia_heat_floor_sensor` | Loggia Heat Floor Sensor | загружена | — |
| `sensor.loggia_heat_floor_linkquality` | Loggia Heat Floor Linkquality | загружена | lqi |
| `sensor.loggia_heat_floor_local_temperature` | Loggia Heat Floor Температура | загружена | °C / temperature |
| `sensor.loggia_heat_floor_program` | Loggia Heat Floor Program | загружена | — |
| `switch.loggia_heat_floor_child_lock` | Loggia Heat Floor Child lock | загружена | — |
### Loggia T1 Sensor

- Производитель: Aqara.
- Модель: Temperature and humidity sensor.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.0x00158d000ab73965_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.loggia_humidity` | Влажность на балконе | загружена | % / humidity |
| `sensor.loggia_pressure` | Давление на балконе | загружена | mmHg / atmospheric_pressure |
| `sensor.loggia_t1_battery` | Loggia T1 Sensor Батарея | загружена | % / battery |
| `sensor.loggia_t1_sensor_voltage` | Напряжение | отключена: user; нет в states | mV / voltage |
| `sensor.loggia_temperature` | Температура на балконе | загружена | °C / temperature |

## Система

### 8.8.8.8

- Производитель: Ping.
- Модель: —.
- Интеграции: ping.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.ping_8_8_8_8` | Ping Google | загружена | connectivity |
| `device_tracker.8_8_8_8` | 8.8.8.8 | отключена: integration; нет в states | — |
| `sensor.8_8_8_8_jitter` | Джиттер | отключена: integration; нет в states | ms / duration |
| `sensor.8_8_8_8_packet_loss` | Packet loss | отключена: integration; нет в states | % |
| `sensor.8_8_8_8_round_trip_time_average` | Среднее время в пути туда и обратно | отключена: integration; нет в states | ms / duration |
| `sensor.8_8_8_8_round_trip_time_maximum` | Максимальное время в пути туда и обратно | отключена: integration; нет в states | ms / duration |
| `sensor.8_8_8_8_round_trip_time_minimum` | Минимальное время в пути туда и обратно | отключена: integration; нет в states | ms / duration |
### AdGuard Home

- Производитель: Home Assistant Community Apps.
- Модель: Home Assistant App.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 6.3.2.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.adguard_home_running` | Работает | отключена: integration; нет в states | running |
| `sensor.adguard_home_cpu_percent` | AdGuard Home Использование ЦП | загружена | % |
| `sensor.adguard_home_memory_percent` | AdGuard Home Использование ОЗУ | загружена | % |
| `sensor.adguard_home_newest_version` | Новая версия | отключена: integration; нет в states | — |
| `sensor.adguard_home_version` | Версия | отключена: integration; нет в states | — |
| `switch.adguard_home` | switch.adguard_home | отключена: integration; нет в states | — |
| `update.adguard_home_update` | AdGuard Home Обновление | загружена | — |
### Advanced SSH & Web Terminal

- Производитель: Home Assistant Community Apps.
- Модель: Home Assistant App.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 24.2.0.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.advanced_ssh_web_terminal_running` | Работает | отключена: integration; нет в states | running |
| `sensor.advanced_ssh_web_terminal_cpu_percent` | Advanced SSH & Web Terminal Использование ЦП | загружена | % |
| `sensor.advanced_ssh_web_terminal_memory_percent` | Advanced SSH & Web Terminal Использование ОЗУ | загружена | % |
| `sensor.advanced_ssh_web_terminal_newest_version` | Новая версия | отключена: integration; нет в states | — |
| `sensor.advanced_ssh_web_terminal_version` | Версия | отключена: integration; нет в states | — |
| `switch.advanced_ssh_web_terminal` | switch.advanced_ssh_web_terminal | отключена: integration; нет в states | — |
| `update.advanced_ssh_web_terminal_update` | Advanced SSH & Web Terminal Обновление | загружена | — |
### Backup

- Производитель: Home Assistant.
- Модель: Home Assistant Backup.
- Интеграции: backup.
- Версия ПО, прочитана 2026-11-09: 2026.10.4.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `event.backup_automatic_backup` | Backup Автоматическое резервное копирование | загружена | — |
| `sensor.backup_backup_manager_state` | Backup Состояние менеджера резервного копирования | загружена | enum |
| `sensor.backup_last_attempted_automatic_backup` | Backup Последняя попытка автоматического резервного копирования | загружена | timestamp |
| `sensor.backup_last_successful_automatic_backup` | Backup Последнее успешное автоматическое резервное копирование | загружена | timestamp |
| `sensor.backup_next_scheduled_automatic_backup` | Backup Следующее запланированное автоматическое резервное копирование | загружена | timestamp |
### Black River

- Производитель: Gismeteo.
- Модель: Forecast.
- Интеграции: gismeteo.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.black_river_apparent_temperature` | Black River Ощущаемая Температура | загружена | °C / temperature |
| `sensor.black_river_birch_pollen_index` | Уровень Пыльцы Берёзы | отключена: integration; нет в states | — |
| `sensor.black_river_cloud_coverage` | Black River Облачность | загружена | % |
| `sensor.black_river_condition` | Black River Погода | загружена | gismeteo__condition |
| `sensor.black_river_geomagnetic_field` | Геомагнитный Фон | отключена: integration; нет в states | — |
| `sensor.black_river_grass_pollen_index` | Уровень Пыльцы Трав | отключена: integration; нет в states | — |
| `sensor.black_river_humidity` | Black River Влажность | загружена | % / humidity |
| `sensor.black_river_precipitation` | Black River Осадки | загружена | mm / precipitation |
| `sensor.black_river_pressure` | Black River Давление | загружена | mmHg / pressure |
| `sensor.black_river_ragweed_pollen_index` | Уровень Пыльцы Амброзии | отключена: integration; нет в states | — |
| `sensor.black_river_rain_amount` | Выпадение Дождя | отключена: integration; нет в states | mm / precipitation |
| `sensor.black_river_road_condition` | Состояние Дорог | отключена: integration; нет в states | — |
| `sensor.black_river_snow_amount` | Выпадение Снега | отключена: integration; нет в states | mm / precipitation |
| `sensor.black_river_storm` | Шторм | отключена: integration; нет в states | — |
| `sensor.black_river_temperature` | Black River Температура | загружена | °C / temperature |
| `sensor.black_river_uv_index` | УФ Фон | отключена: integration; нет в states | — |
| `sensor.black_river_water_temperature` | Температура Воды | отключена: integration; нет в states | °C / temperature |
| `sensor.black_river_wind_bearing` | Black River Направление Ветра | загружена | ° |
| `sensor.black_river_wind_bearing_2` | Black River Направление Ветра | загружена | — |
| `sensor.black_river_wind_speed` | Black River Скорость Ветра | загружена | m/s |
| `weather.black_river` | Black River | загружена | — |
### Database Size Sqlite

- Производитель: SQL.
- Модель: —.
- Интеграции: sql.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.database_size_sqlite` | Database Size Sqlite | загружена | MB / data_size |
### Gismeteo

- Производитель: Limych.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.gismeteo_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.gismeteo_update` | Gismeteo Update | загружена | — |
### HACS

- Производитель: hacs.xyz.
- Модель: —.
- Интеграции: hacs.
- Версия ПО, прочитана 2026-11-09: 2.0.5.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.hacs_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.hacs_update` | HACS Update | загружена | — |
### Home Assistant Core

- Производитель: Home Assistant.
- Модель: Home Assistant Core.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 2026.10.4.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.home_assistant_core_cpu_percent` | Home Assistant Core Использование ЦП | загружена | % |
| `sensor.home_assistant_core_memory_percent` | Home Assistant Core Использование ОЗУ | загружена | % |
| `update.home_assistant_core_update` | Home Assistant Core Обновление | загружена | — |
### Home Assistant Google Drive Backup

- Производитель: Home Assistant Google Drive Backup Repository.
- Модель: Home Assistant App.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 0.112.1.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.home_assistant_google_drive_backup_running` | Работает | отключена: integration; нет в states | running |
| `sensor.home_assistant_google_drive_backup_cpu_percent` | Home Assistant Google Drive Backup Использование ЦП | загружена | % |
| `sensor.home_assistant_google_drive_backup_memory_percent` | Home Assistant Google Drive Backup Использование ОЗУ | загружена | % |
| `sensor.home_assistant_google_drive_backup_newest_version` | Новая версия | отключена: integration; нет в states | — |
| `sensor.home_assistant_google_drive_backup_version` | Версия | отключена: integration; нет в states | — |
| `switch.home_assistant_google_drive_backup` | switch.home_assistant_google_drive_backup | отключена: integration; нет в states | — |
| `update.home_assistant_google_drive_backup_update` | Home Assistant Google Drive Backup Обновление | загружена | — |
### Home Assistant Host

- Производитель: Home Assistant.
- Модель: Home Assistant Host.
- Интеграции: hassio.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.home_assistant_host_apparmor_version` | Версия AppArmor | отключена: integration; нет в states | — |
| `sensor.home_assistant_host_disk_free` | Home Assistant Host Памяти доступно | загружена | GB / data_size |
| `sensor.home_assistant_host_disk_total` | Home Assistant Host Памяти всего | загружена | GB / data_size |
| `sensor.home_assistant_host_disk_used` | Home Assistant Host Памяти использовано | загружена | GB / data_size |
| `sensor.home_assistant_host_os_agent_version` | Версия OS Agent | отключена: integration; нет в states | — |
### Home Assistant Operating System

- Производитель: Home Assistant.
- Модель: Home Assistant Operating System.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 18.4.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.home_assistant_operating_system_newest_version` | Новая версия | отключена: integration; нет в states | — |
| `sensor.home_assistant_operating_system_version` | Home Assistant Operating System Версия | загружена | — |
| `update.home_assistant_operating_system_update` | Home Assistant Operating System Обновление | загружена | — |
### Home Assistant SkyConnect ZBT-1 Thread (1ce57667)

- Производитель: Nabu Casa.
- Модель: Home Assistant Connect ZBT-1.
- Интеграции: homeassistant_sky_connect.
- Версия ПО, прочитана 2026-11-09: OpenThread RCP 2.7.2.0.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.home_assistant_skyconnect_zbt_1_thread_1ce57667_beta_firmware_updates` | Бета-обновления прошивки | отключена: integration; нет в states | — |
| `update.home_assistant_connect_zbt_1_1ce57667_firmware` | Home Assistant SkyConnect ZBT-1 Thread (1ce57667) Обновление прошивки | загружена | firmware |
### Home Assistant SkyConnect ZBT-1 z2m (32c8cd8c)

- Производитель: Nabu Casa.
- Модель: Home Assistant Connect ZBT-1.
- Интеграции: homeassistant_sky_connect.
- Версия ПО, прочитана 2026-11-09: EmberZNet Zigbee None.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.home_assistant_skyconnect_zbt_1_z2m_32c8cd8c_beta_firmware_updates` | Бета-обновления прошивки | отключена: integration; нет в states | — |
| `update.home_assistant_connect_zbt_1_32c8cd8c_firmware` | Home Assistant SkyConnect ZBT-1 z2m (32c8cd8c) Обновление прошивки | загружена | firmware |
### Home Assistant Supervisor

- Производитель: Home Assistant.
- Модель: Home Assistant Supervisor.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 2026.10.5.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.home_assistant_supervisor_cpu_percent` | Home Assistant Supervisor Использование ЦП | загружена | % |
| `sensor.home_assistant_supervisor_memory_percent` | Home Assistant Supervisor Использование ОЗУ | загружена | % |
| `update.home_assistant_supervisor_update` | Home Assistant Supervisor Обновление | загружена | — |
### iPad

- Производитель: Apple.
- Модель: iPad7,1.
- Интеграции: mobile_app.
- Версия ПО, прочитана 2026-11-09: 17.7.11.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.sistema_ipad_camera_motion` | iPad Camera Motion | отключена: user; нет в states | — |
| `binary_sensor.sistema_ipad_focus` | iPad Focus | загружена | — |
| `binary_sensor.sistema_ipad_kiosk_mode` | iPad Kiosk Mode | загружена | — |
| `binary_sensor.sistema_ipad_kiosk_screensaver` | iPad Kiosk Screensaver | загружена | — |
| `device_tracker.ipad` | iPad | отключена: user; нет в states | — |
| `notify.ipad` | iPad | загружена | — |
| `sensor.ipad_app_version` | iPad App Version | загружена | — |
| `sensor.ipad_audio_output` | iPad Audio Output | загружена | — |
| `sensor.ipad_battery_level` | iPad Battery Level | загружена | % / battery |
| `sensor.ipad_battery_state` | iPad Battery State | загружена | — |
| `sensor.ipad_bssid` | iPad BSSID | загружена | — |
| `sensor.ipad_connection_type` | iPad Connection Type | загружена | — |
| `sensor.ipad_geocoded_location` | iPad Geocoded Location | загружена | — |
| `sensor.ipad_last_update_trigger` | iPad Last Update Trigger | загружена | — |
| `sensor.ipad_location_permission` | iPad Location permission | загружена | — |
| `sensor.ipad_ssid` | iPad SSID | загружена | — |
| `sensor.ipad_storage` | iPad Storage | загружена | % available |
| `sensor.sistema_ipad_activity` | iPad Activity | загружена | — |
| `sensor.sistema_ipad_camera_stream` | iPad Camera Stream | отключена: user; нет в states | — |
| `sensor.sistema_ipad_focus_name` | iPad Focus name | отключена: integration; нет в states | — |
| `sensor.sistema_ipad_kiosk_brightness` | iPad Kiosk Brightness | отключена: user; нет в states | — |
| `sensor.sistema_ipad_kiosk_volume` | iPad Kiosk Volume | отключена: user; нет в states | — |
| `sensor.sistema_ipad_pressure` | iPad Pressure | загружена | — |
### iPhone 17 Pro

- Производитель: Apple.
- Модель: iPhone18,1.
- Интеграции: mobile_app.
- Версия ПО, прочитана 2026-11-09: 26.6.2.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.sistema_iphone_17_pro_camera_motion` | iPhone 17 Pro Camera Motion | отключена: user; нет в states | — |
| `binary_sensor.sistema_iphone_17_pro_focus` | iPhone 17 Pro Focus | отключена: user; нет в states | — |
| `binary_sensor.sistema_iphone_17_pro_kiosk_mode` | iPhone 17 Pro Kiosk Mode | загружена | — |
| `binary_sensor.sistema_iphone_17_pro_kiosk_screensaver` | iPhone 17 Pro Kiosk Screensaver | загружена | — |
| `device_tracker.iphone_17_pro` | iPhone 17 Pro | отключена: user; нет в states | — |
| `notify.iphone_17_pro` | iPhone 17 Pro | загружена | — |
| `sensor.sistema_iphone_17_pro_activity` | iPhone 17 Pro Activity | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_app_version` | iPhone 17 Pro App Version | загружена | — |
| `sensor.sistema_iphone_17_pro_audio_output` | iPhone 17 Pro Audio Output | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_average_active_pace` | iPhone 17 Pro Average Active Pace | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_battery_level` | iPhone 17 Pro Battery Level | загружена | % / battery |
| `sensor.sistema_iphone_17_pro_battery_state` | iPhone 17 Pro Battery State | загружена | — |
| `sensor.sistema_iphone_17_pro_bssid` | iPhone 17 Pro BSSID | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_camera_stream` | iPhone 17 Pro Camera Stream | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_connection_type` | iPhone 17 Pro Connection Type | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_current_cadence` | iPhone 17 Pro Current Cadence | загружена | — |
| `sensor.sistema_iphone_17_pro_current_pace` | iPhone 17 Pro Current Pace | загружена | — |
| `sensor.sistema_iphone_17_pro_distance` | iPhone 17 Pro Distance | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_floors_ascended` | iPhone 17 Pro Floors Ascended | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_floors_descended` | iPhone 17 Pro Floors Descended | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_focus_name` | iPhone 17 Pro Focus name | загружена | — |
| `sensor.sistema_iphone_17_pro_geocoded_location` | iPhone 17 Pro Geocoded Location | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_kiosk_brightness` | iPhone 17 Pro Kiosk Brightness | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_kiosk_volume` | iPhone 17 Pro Kiosk Volume | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_last_update_trigger` | iPhone 17 Pro Last Update Trigger | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_location_permission` | iPhone 17 Pro Location permission | загружена | — |
| `sensor.sistema_iphone_17_pro_pressure` | iPhone 17 Pro Pressure | загружена | hPa / pressure |
| `sensor.sistema_iphone_17_pro_sim_1` | iPhone 17 Pro SIM 1 | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_sim_2` | iPhone 17 Pro SIM 2 | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_ssid` | iPhone 17 Pro SSID | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_steps` | iPhone 17 Pro Steps | отключена: user; нет в states | — |
| `sensor.sistema_iphone_17_pro_storage` | iPhone 17 Pro Storage | отключена: user; нет в states | — |
### Maintenance Supporter

- Производитель: —.
- Модель: —.
- Интеграции: maintenance_supporter.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.maintenance_supporter_batteries_to_replace` | Maintenance Supporter Батареи к замене | загружена | batteries |
| `sensor.maintenance_supporter_document_storage` | Maintenance Supporter Хранилище документов | загружена | B / data_size |
| `sensor.maintenance_supporter_due_soon` | Maintenance Supporter Скоро наступит | загружена | tasks |
| `sensor.maintenance_supporter_needs_attention` | Maintenance Supporter Требует внимания | загружена | tasks |
| `sensor.maintenance_supporter_ok` | Maintenance Supporter ОК | загружена | tasks |
| `sensor.maintenance_supporter_overdue` | Maintenance Supporter Просрочено | загружена | tasks |
| `sensor.maintenance_supporter_parts_to_reorder` | Maintenance Supporter Детали к дозаказу | загружена | parts |
| `sensor.maintenance_supporter_total_tasks` | Maintenance Supporter Всего задач | загружена | tasks |
| `sensor.maintenance_supporter_triggered` | Maintenance Supporter Сработал | загружена | tasks |
### Matter Server

- Производитель: Official apps.
- Модель: Home Assistant App.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 9.3.0.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.matter_server_running` | Matter Server Работает | загружена | running |
| `sensor.matter_server_cpu_percent` | Matter Server Использование ЦП | загружена | % |
| `sensor.matter_server_memory_percent` | Matter Server Использование ОЗУ | загружена | % |
| `sensor.matter_server_newest_version` | Matter Server Новая версия | загружена | — |
| `sensor.matter_server_version` | Matter Server Версия | загружена | — |
| `switch.matter_server` | switch.matter_server | отключена: integration; нет в states | — |
| `update.matter_server_update` | Matter Server Обновление | загружена | — |
### Meross LAN

- Производитель: krahabb.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.meross_lan_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.meross_lan_update` | Meross LAN Update | загружена | — |
### mini-graph-card

- Производитель: kalkih.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.mini_graph_card_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.mini_graph_card_update` | mini-graph-card Update | загружена | — |
### Moon

- Производитель: —.
- Модель: —.
- Интеграции: moon.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `sensor.moon_phase` | Moon Фаза | загружена | enum |
### Mosquitto broker

- Производитель: Official apps.
- Модель: Home Assistant App.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 7.1.3.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.mosquitto_broker_running` | Работает | отключена: integration; нет в states | running |
| `sensor.mosquitto_broker_cpu_percent` | Mosquitto broker Использование ЦП | загружена | % |
| `sensor.mosquitto_broker_memory_percent` | Mosquitto broker Использование ОЗУ | загружена | % |
| `sensor.mosquitto_broker_newest_version` | Новая версия | отключена: integration; нет в states | — |
| `sensor.mosquitto_broker_version` | Версия | отключена: integration; нет в states | — |
| `switch.mosquitto_broker` | switch.mosquitto_broker | отключена: integration; нет в states | — |
| `update.mosquitto_broker_update` | Mosquitto broker Обновление | загружена | — |
### OpenThread Border Router

- Производитель: Official apps.
- Модель: Home Assistant App.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 3.3.0.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.openthread_border_router_running` | Работает | отключена: integration; нет в states | running |
| `sensor.openthread_border_router_cpu_percent` | OpenThread Border Router Использование ЦП | загружена | % |
| `sensor.openthread_border_router_memory_percent` | OpenThread Border Router Использование ОЗУ | загружена | % |
| `sensor.openthread_border_router_newest_version` | Новая версия | отключена: integration; нет в states | — |
| `sensor.openthread_border_router_version` | Версия | отключена: integration; нет в states | — |
| `switch.openthread_border_router` | switch.openthread_border_router | отключена: integration; нет в states | — |
| `update.openthread_border_router_update` | OpenThread Border Router Обновление | загружена | — |
### PetKit

- Производитель: RobertD502.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.petkit_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.petkit_update` | PetKit Update | загружена | — |
### Silicon Labs Flasher

- Производитель: Official apps.
- Модель: Home Assistant App.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 0.5.0.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.silicon_labs_flasher_running` | Работает | отключена: integration; нет в states | running |
| `sensor.silicon_labs_flasher_cpu_percent` | Silicon Labs Flasher Использование ЦП | загружена | % |
| `sensor.silicon_labs_flasher_memory_percent` | Silicon Labs Flasher Использование ОЗУ | загружена | % |
| `sensor.silicon_labs_flasher_newest_version` | Новая версия | отключена: integration; нет в states | — |
| `sensor.silicon_labs_flasher_version` | Версия | отключена: integration; нет в states | — |
| `switch.silicon_labs_flasher` | switch.silicon_labs_flasher | отключена: integration; нет в states | — |
| `update.silicon_labs_flasher_update` | Silicon Labs Flasher Обновление | загружена | — |
### Studio Code Server

- Производитель: Home Assistant Community Apps.
- Модель: Home Assistant App.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 7.2.0.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.studio_code_server_running` | Работает | отключена: integration; нет в states | running |
| `sensor.studio_code_server_cpu_percent` | Studio Code Server Использование ЦП | загружена | % |
| `sensor.studio_code_server_memory_percent` | Studio Code Server Использование ОЗУ | загружена | % |
| `sensor.studio_code_server_newest_version` | Новая версия | отключена: integration; нет в states | — |
| `sensor.studio_code_server_version` | Версия | отключена: integration; нет в states | — |
| `switch.studio_code_server` | switch.studio_code_server | отключена: integration; нет в states | — |
| `update.studio_code_server_update` | Studio Code Server Обновление | загружена | — |
### Sun

- Производитель: —.
- Модель: —.
- Интеграции: sun.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.sun_solar_rising` | Восход солнца | отключена: integration; нет в states | — |
| `sensor.sun_next_dawn` | Sun Следующий рассвет | загружена | timestamp |
| `sensor.sun_next_dusk` | Sun Следующие сумерки | загружена | timestamp |
| `sensor.sun_next_midnight` | Sun Следующая полночь | загружена | timestamp |
| `sensor.sun_next_noon` | Sun Следующий полдень | загружена | timestamp |
| `sensor.sun_next_rising` | Sun Следующий восход | загружена | timestamp |
| `sensor.sun_next_setting` | Sun Следующий заход | загружена | timestamp |
| `sensor.sun_solar_azimuth` | Азимут | отключена: integration; нет в states | ° |
| `sensor.sun_solar_elevation` | Высота над горизонтом | отключена: integration; нет в states | ° |
### Yandex Smart Home

- Производитель: dext0r.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.yandex_smart_home_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.yandex_smart_home_update` | Yandex Smart Home Update | загружена | — |
### Yandex.Station

- Производитель: AlexxIT.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.yandex_station_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.yandex_station_update` | Yandex.Station Update | загружена | — |
### Zigbee2MQTT

- Производитель: Home Assistant App: Zigbee2MQTT.
- Модель: Home Assistant App.
- Интеграции: hassio.
- Версия ПО, прочитана 2026-11-09: 2.14.3-1.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.zigbee2mqtt_running` | Работает | отключена: integration; нет в states | running |
| `sensor.zigbee2mqtt_cpu_percent` | Zigbee2MQTT Использование ЦП | загружена | % |
| `sensor.zigbee2mqtt_memory_percent` | Zigbee2MQTT Использование ОЗУ | загружена | % |
| `sensor.zigbee2mqtt_newest_version` | Новая версия | отключена: integration; нет в states | — |
| `sensor.zigbee2mqtt_version` | Версия | отключена: integration; нет в states | — |
| `switch.zigbee2mqtt` | switch.zigbee2mqtt | отключена: integration; нет в states | — |
| `update.zigbee2mqtt_update` | Zigbee2MQTT Обновление | загружена | — |
### Zigbee2MQTT Bridge

- Производитель: Zigbee2MQTT.
- Модель: Bridge.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: 2.14.3.
- Аппаратная версия: EmberZNet 7.4.4 [GA].

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.zigbee2mqtt_bridge_connection_state` | Zigbee2MQTT Bridge Connection state | загружена | connectivity |
| `binary_sensor.zigbee2mqtt_bridge_restart_required` | Restart required | отключена: integration; нет в states | problem |
| `button.zigbee2mqtt_bridge_restart` | Zigbee2MQTT Bridge Restart | загружена | restart |
| `select.zigbee2mqtt_bridge_log_level` | Zigbee2MQTT Bridge Log level | загружена | — |
| `sensor.zigbee2mqtt_bridge_coordinator_version` | Coordinator version | отключена: integration; нет в states | — |
| `sensor.zigbee2mqtt_bridge_network_map` | Network map | отключена: integration; нет в states | — |
| `sensor.zigbee2mqtt_bridge_version` | Zigbee2MQTT Bridge Version | загружена | — |
| `switch.zigbee2mqtt_bridge_permit_join` | Zigbee2MQTT Bridge Permit join | загружена | — |

## Без назначенной комнаты

### __Phantom Contact Sensor

Примечание владельца: По объяснению владельца 2026-11-09: физически не существует, фантом после многократного переподключения сенсора к Aqara Hub. В Aqara app отсутствует; HA отклоняет удаление: Failed to remove device entry, rejected by integration. Исправление сейчас не запрошено.

- Производитель: Aqara.
- Модель: AS006.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 3.
- Аппаратная версия: 1.0.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.contact_sensor` | Contact Sensor | отключена: user; нет в states | opening |
| `button.phantom_contact_sensor_identify` | __Phantom Contact Sensor Identify | отключена: user; нет в states | identify |
| `sensor.phantom_contact_sensor_battery_sensor` | __Phantom Contact Sensor Battery Sensor | отключена: user; нет в states | % / battery |
### auto-entities

- Производитель: thomasloven.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.auto_entities_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.auto_entities_update` | auto-entities Update | загружена | — |
### Bar Sensor Card

- Производитель: headsoft-mikhail.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.bar_sensor_card_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.bar_sensor_card_update` | Bar Sensor Card Update | загружена | — |
### browser_mod

- Производитель: thomasloven.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.browser_mod_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.browser_mod_update` | browser_mod Update | загружена | — |
### Clock Weather Card

- Производитель: pkissling.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.clock_weather_card_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.clock_weather_card_update` | Clock Weather Card Update | загружена | — |
### Custom Features for Home Assistant Cards

- Производитель: Nerwyn.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.custom_features_for_home_assistant_cards_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.custom_features_for_home_assistant_cards_update` | Custom Features for Home Assistant Cards Update | загружена | — |
### EcoFlowCloud

- Производитель: tolwi.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.ecoflowcloud_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.ecoflowcloud_update` | EcoFlowCloud Update | загружена | — |
### FingerBot

- Производитель: Tuya.
- Модель: Zigbee fingerbot plus.
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `number.fingerbot_delay` | FingerBot Delay | загружена | s |
| `number.fingerbot_lower` | FingerBot Lower | загружена | % |
| `number.fingerbot_upper` | FingerBot Upper | загружена | % |
| `select.fingerbot_mode` | FingerBot Mode | загружена | — |
| `sensor.0xa4c138105ed9ae69_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.fingerbot_battery` | Батарея | отключена: user; нет в states | % / battery |
| `switch.fingerbot` | FingerBot | загружена | — |
| `switch.fingerbot_reverse` | FingerBot Reverse | загружена | — |
| `switch.fingerbot_touch` | FingerBot Touch | загружена | — |
### Fireplace Plug

- Производитель: Tuya.
- Модель: Smart plug (with power monitoring).
- Интеграции: mqtt.
- Версия ПО, прочитана 2026-11-09: Zigbee2MQTT 2.14.3.
- Аппаратная версия: 1.
- Родительское устройство: Zigbee2MQTT Bridge.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `button.fireplace_plug_identify` | Fireplace Plug Идентификация | загружена | identify |
| `number.fireplace_plug_countdown` | Fireplace Plug Countdown | загружена | s |
| `select.fireplace_plug_indicator_mode` | Fireplace Plug Indicator mode | загружена | — |
| `select.fireplace_plug_power_outage_memory` | Fireplace Plug Power outage memory | загружена | — |
| `select.fireplace_plug_switch_type_button` | Fireplace Plug Switch type button | загружена | — |
| `sensor.0xa4c13838cbef1864_linkquality` | Linkquality | отключена: integration; нет в states | lqi |
| `sensor.fireplace_plug_current` | Fireplace Plug Ток | загружена | A / current |
| `sensor.fireplace_plug_energy` | Fireplace Plug Энергия | загружена | kWh / energy |
| `sensor.fireplace_plug_power` | Fireplace Plug Мощность | загружена | W / power |
| `sensor.fireplace_plug_voltage` | Fireplace Plug Напряжение | загружена | V / voltage |
| `switch.fireplace_plug` | Fireplace Plug | загружена | — |
| `switch.fireplace_plug_child_lock` | Fireplace Plug Child lock | загружена | — |
| `update.fireplace_plug` | Fireplace Plug | загружена | firmware |
### HASS Bridge Bathroom:56320

- Производитель: Home Assistant.
- Модель: HomeBridge.
- Интеграции: нет entity.

Сущностей в действующем реестре не найдено.
### HASS Bridge Bedroom:56321

- Производитель: Home Assistant.
- Модель: HomeBridge.
- Интеграции: нет entity.

Сущностей в действующем реестре не найдено.
### HASS Bridge Hall:56322

- Производитель: Home Assistant.
- Модель: HomeBridge.
- Интеграции: нет entity.

Сущностей в действующем реестре не найдено.
### HASS Bridge KidsRoom:56323

- Производитель: Home Assistant.
- Модель: HomeBridge.
- Интеграции: нет entity.

Сущностей в действующем реестре не найдено.
### HASS Bridge Kitchen:56324

- Производитель: Home Assistant.
- Модель: HomeBridge.
- Интеграции: нет entity.

Сущностей в действующем реестре не найдено.
### HASS Bridge Laundry:56326

- Производитель: Home Assistant.
- Модель: HomeBridge.
- Интеграции: нет entity.

Сущностей в действующем реестре не найдено.
### HASS Bridge LivingRoom:56325

- Производитель: Home Assistant.
- Модель: HomeBridge.
- Интеграции: нет entity.

Сущностей в действующем реестре не найдено.
### HASS Bridge Loggia:56327

- Производитель: Home Assistant.
- Модель: HomeBridge.
- Интеграции: нет entity.

Сущностей в действующем реестре не найдено.
### HASS Bridge StoreRoom:56328

- Производитель: Home Assistant.
- Модель: HomeBridge.
- Интеграции: нет entity.

Сущностей в действующем реестре не найдено.
### Horizon Card

- Производитель: rejuvenate.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.horizon_card_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.horizon_card_update` | Horizon Card Update | загружена | — |
### Hourly Weather Card

- Производитель: decompil3d.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.hourly_weather_card_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.hourly_weather_card_update` | Hourly Weather Card Update | загружена | — |
### iPhone (Ангелина)

- Производитель: Apple.
- Модель: iPhone13,2.
- Интеграции: mobile_app.
- Версия ПО, прочитана 2026-11-09: 27.0.1.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.iphone_angelina_camera_motion` | iPhone (Ангелина) Camera Motion | отключена: user; нет в states | — |
| `binary_sensor.iphone_angelina_focus` | iPhone (Ангелина) Focus | загружена | — |
| `binary_sensor.iphone_angelina_kiosk_mode` | iPhone (Ангелина) Kiosk Mode | загружена | — |
| `binary_sensor.iphone_angelina_kiosk_screensaver` | iPhone (Ангелина) Kiosk Screensaver | загружена | — |
| `device_tracker.iphone_angelina` | iPhone (Ангелина) | отключена: user; нет в states | — |
| `notify.iphone_angelina` | iPhone (Ангелина) | загружена | — |
| `sensor.iphone_angelina_activity` | iPhone (Ангелина) Activity | загружена | — |
| `sensor.iphone_angelina_app_version` | iPhone (Ангелина) App Version | загружена | — |
| `sensor.iphone_angelina_audio_output` | iPhone (Ангелина) Audio Output | отключена: user; нет в states | — |
| `sensor.iphone_angelina_average_active_pace` | iPhone (Ангелина) Average Active Pace | загружена | — |
| `sensor.iphone_angelina_battery_level` | iPhone (Ангелина) Battery Level | загружена | % / battery |
| `sensor.iphone_angelina_battery_state` | iPhone (Ангелина) Battery State | загружена | — |
| `sensor.iphone_angelina_bssid` | iPhone (Ангелина) BSSID | отключена: user; нет в states | — |
| `sensor.iphone_angelina_camera_stream` | iPhone (Ангелина) Camera Stream | отключена: user; нет в states | — |
| `sensor.iphone_angelina_connection_type` | iPhone (Ангелина) Connection Type | отключена: user; нет в states | — |
| `sensor.iphone_angelina_current_cadence` | iPhone (Ангелина) Current Cadence | загружена | — |
| `sensor.iphone_angelina_current_pace` | iPhone (Ангелина) Current Pace | загружена | — |
| `sensor.iphone_angelina_distance` | iPhone (Ангелина) Distance | загружена | — |
| `sensor.iphone_angelina_floors_ascended` | iPhone (Ангелина) Floors Ascended | загружена | — |
| `sensor.iphone_angelina_floors_descended` | iPhone (Ангелина) Floors Descended | загружена | — |
| `sensor.iphone_angelina_focus_name` | iPhone (Ангелина) Focus name | загружена | — |
| `sensor.iphone_angelina_geocoded_location` | iPhone (Ангелина) Geocoded Location | отключена: user; нет в states | — |
| `sensor.iphone_angelina_kiosk_brightness` | iPhone (Ангелина) Kiosk Brightness | отключена: user; нет в states | — |
| `sensor.iphone_angelina_kiosk_volume` | iPhone (Ангелина) Kiosk Volume | отключена: user; нет в states | — |
| `sensor.iphone_angelina_last_update_trigger` | iPhone (Ангелина) Last Update Trigger | отключена: user; нет в states | — |
| `sensor.iphone_angelina_location_permission` | iPhone (Ангелина) Location permission | загружена | — |
| `sensor.iphone_angelina_pressure` | iPhone (Ангелина) Pressure | загружена | — |
| `sensor.iphone_angelina_sim_1` | iPhone (Ангелина) SIM 1 | отключена: user; нет в states | — |
| `sensor.iphone_angelina_sim_2` | iPhone (Ангелина) SIM 2 | отключена: user; нет в states | — |
| `sensor.iphone_angelina_ssid` | iPhone (Ангелина) SSID | отключена: user; нет в states | — |
| `sensor.iphone_angelina_steps` | iPhone (Ангелина) Steps | загружена | — |
| `sensor.iphone_angelina_storage` | iPhone (Ангелина) Storage | отключена: user; нет в states | % available |
### KeeneticElements

- Производитель: Home Assistant.
- Модель: Home Assistant Mount.
- Интеграции: hassio.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.keeneticelements_connected` | Connected | отключена: integration; нет в states | connectivity |
### KeeneticMyPassport

- Производитель: Home Assistant.
- Модель: Home Assistant Mount.
- Интеграции: hassio.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.keeneticmypassport_connected` | Connected | отключена: integration; нет в states | connectivity |
### layout-card

- Производитель: thomasloven.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.layout_card_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.layout_card_update` | layout-card Update | загружена | — |
### Maintenance Supporter

- Производитель: iluebbe.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.maintenance_supporter_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.maintenance_supporter_update` | Maintenance Supporter Update | загружена | — |
### Mushroom

- Производитель: piitaya.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.mushroom_pre_release` | Mushroom Pre-release | загружена | — |
| `update.mushroom_update` | Mushroom Update | загружена | — |
### Pie Chart Card

- Производитель: sdelliot.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.pie_chart_card_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.pie_chart_card_update` | Pie Chart Card Update | загружена | — |
### Power Flow Card Plus

- Производитель: flixlix.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.power_flow_card_plus_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.power_flow_card_plus_update` | Power Flow Card Plus Update | загружена | — |
### Qingping

- Производитель: mash2k3.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.qingping_pro_aqm_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.qingping_pro_aqm_update` | Qingping Update | загружена | — |
### Raspberry Pi

- Производитель: Raspberry Pi.
- Модель: —.
- Интеграции: rpi_power.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.rpi_power_status` | Raspberry Pi Power status | загружена | problem |
### Raspberry Pi 5

- Производитель: Raspberry Pi.
- Модель: 5.
- Интеграции: raspberry_pi.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `update.raspberry_pi_5_firmware` | Raspberry Pi 5 Firmware | загружена | firmware |
### Raspberry Pi GPIO

- Производитель: thecode, tomer-w.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.raspberry_pi_gpio_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.raspberry_pi_gpio_update` | Raspberry Pi GPIO Update | загружена | — |
### Transmission 3.x

- Производитель: headsoft-mikhail.
- Модель: integration.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.transmission_3_x_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.transmission_3_x_update` | Transmission 3.x Update | загружена | — |
### Transmission Card

- Производитель: amaximus.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.transmission_card_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.transmission_card_update` | Transmission Card Update | загружена | — |
### Uptime Card

- Производитель: dylandoamaral.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.uptime_card_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.uptime_card_update` | Uptime Card Update | загружена | — |
### Vibration Sensor

Примечание владельца: Подключён к умному дому; применение пока не выбрано. Ответ владельца 2026-11-09.

- Производитель: Aqara.
- Модель: AS009.
- Интеграции: homekit_controller.
- Версия ПО, прочитана 2026-11-09: 8.
- Аппаратная версия: 3.
- Родительское устройство: Aqara Hub E1 8F1B.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.vibration_sensor` | Vibration Sensor | загружена | motion |
| `button.vibration_sensor_identify_2` | Vibration Sensor Identify | отключена: user; нет в states | identify |
| `sensor.vibration_sensor_battery_sensor` | Vibration Sensor Battery Sensor | загружена | % / battery |
### Wind Rose Card

- Производитель: aukedejong.
- Модель: plugin.
- Интеграции: hacs.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `switch.wind_rose_card_pre_release` | Pre-release | отключена: integration; нет в states | — |
| `update.wind_rose_card_update` | Wind Rose Card Update | загружена | — |
### Автоматические кормилки

- Производитель: Petkit.
- Модель: Solo.
- Интеграции: maintenance_supporter.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.avtomaticheskie_kormilki_dosypat_korm_overdue` | Автоматические кормилки Досыпать корм просрочено | загружена | problem |
| `binary_sensor.avtomaticheskie_kormilki_kupit_korm_overdue_2` | Автоматические кормилки Купить корм просрочено | загружена | problem |
| `binary_sensor.avtomaticheskie_kormilki_zamena_vlagopoglotitelia_overdue_2` | Автоматические кормилки Замена влагопоглотителя просрочено | загружена | problem |
| `button.avtomaticheskie_kormilki_dosypat_korm_complete` | Автоматические кормилки Досыпать корм Выполнить | загружена | — |
| `button.avtomaticheskie_kormilki_dosypat_korm_reset` | Автоматические кормилки Досыпать корм Сбросить | загружена | — |
| `button.avtomaticheskie_kormilki_dosypat_korm_skip` | Автоматические кормилки Досыпать корм Пропустить | загружена | — |
| `button.avtomaticheskie_kormilki_kupit_korm_complete_2` | Автоматические кормилки Купить корм Выполнить | загружена | — |
| `button.avtomaticheskie_kormilki_kupit_korm_reset_2` | Автоматические кормилки Купить корм Сбросить | загружена | — |
| `button.avtomaticheskie_kormilki_kupit_korm_skip_2` | Автоматические кормилки Купить корм Пропустить | загружена | — |
| `button.avtomaticheskie_kormilki_zamena_vlagopoglotitelia_complete_2` | Автоматические кормилки Замена влагопоглотителя Выполнить | загружена | — |
| `button.avtomaticheskie_kormilki_zamena_vlagopoglotitelia_reset_2` | Автоматические кормилки Замена влагопоглотителя Сбросить | загружена | — |
| `button.avtomaticheskie_kormilki_zamena_vlagopoglotitelia_skip_2` | Автоматические кормилки Замена влагопоглотителя Пропустить | загружена | — |
| `sensor.avtomaticheskie_kormilki_dosypat_korm` | Автоматические кормилки Досыпать корм | загружена | enum |
| `sensor.avtomaticheskie_kormilki_dosypat_korm_next_due` | Досыпать корм Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.avtomaticheskie_kormilki_kupit_korm_2` | Автоматические кормилки Купить корм | загружена | enum |
| `sensor.avtomaticheskie_kormilki_kupit_korm_next_due` | Купить корм Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.avtomaticheskie_kormilki_kupit_korm_next_due_2` | Купить корм Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.avtomaticheskie_kormilki_zamena_vlagopoglotitelia_2` | Автоматические кормилки Замена влагопоглотителя | загружена | enum |
| `sensor.avtomaticheskie_kormilki_zamena_vlagopoglotitelia_next_due` | Замена влагопоглотителя Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.avtomaticheskie_kormilki_zamena_vlagopoglotitelia_next_due_2` | Замена влагопоглотителя Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.obj_830b1164f0ce_obj_1b4bdc45160b_days_until_due` | Замена влагопоглотителя Дней до срока | отключена: integration; нет в states | d |
| `sensor.obj_830b1164f0ce_obj_6471a626041d_days_until_due` | Досыпать корм Дней до срока | отключена: integration; нет в states | d |
| `sensor.obj_830b1164f0ce_obj_d01a24e44564_days_until_due` | Купить корм Дней до срока | отключена: integration; нет в states | d |
### Кошачий лоток

- Производитель: Petkit.
- Модель: Cat Litter Box.
- Интеграции: maintenance_supporter.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.koshachii_lotok_kupit_napolnitel_overdue_2` | Кошачий лоток Купить наполнитель просрочено | загружена | problem |
| `binary_sensor.koshachii_lotok_zamena_batareek_v_osvezhitele_overdue_2` | Кошачий лоток Замена батареек в освежителе просрочено | загружена | problem |
| `binary_sensor.koshachii_lotok_zamena_osvezhitelia_overdue_2` | Кошачий лоток Замена освежителя просрочено | загружена | problem |
| `button.koshachii_lotok_kupit_napolnitel_complete_2` | Кошачий лоток Купить наполнитель Выполнить | загружена | — |
| `button.koshachii_lotok_kupit_napolnitel_reset_2` | Кошачий лоток Купить наполнитель Сбросить | загружена | — |
| `button.koshachii_lotok_kupit_napolnitel_skip_2` | Кошачий лоток Купить наполнитель Пропустить | загружена | — |
| `button.koshachii_lotok_zamena_batareek_v_osvezhitele_complete_2` | Кошачий лоток Замена батареек в освежителе Выполнить | загружена | — |
| `button.koshachii_lotok_zamena_batareek_v_osvezhitele_reset_2` | Кошачий лоток Замена батареек в освежителе Сбросить | загружена | — |
| `button.koshachii_lotok_zamena_batareek_v_osvezhitele_skip_2` | Кошачий лоток Замена батареек в освежителе Пропустить | загружена | — |
| `button.koshachii_lotok_zamena_osvezhitelia_complete_2` | Кошачий лоток Замена освежителя Выполнить | загружена | — |
| `button.koshachii_lotok_zamena_osvezhitelia_reset_2` | Кошачий лоток Замена освежителя Сбросить | загружена | — |
| `button.koshachii_lotok_zamena_osvezhitelia_skip_2` | Кошачий лоток Замена освежителя Пропустить | загружена | — |
| `sensor.koshachii_lotok_kupit_napolnitel_2` | Кошачий лоток Купить наполнитель | загружена | enum |
| `sensor.koshachii_lotok_kupit_napolnitel_next_due` | Купить наполнитель Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.koshachii_lotok_kupit_napolnitel_next_due_2` | Купить наполнитель Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.koshachii_lotok_zamena_batareek_v_osvezhitele_2` | Кошачий лоток Замена батареек в освежителе | загружена | enum |
| `sensor.koshachii_lotok_zamena_batareek_v_osvezhitele_next_due` | Замена батареек в освежителе Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.koshachii_lotok_zamena_batareek_v_osvezhitele_next_due_2` | Замена батареек в освежителе Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.koshachii_lotok_zamena_osvezhitelia_2` | Кошачий лоток Замена освежителя | загружена | enum |
| `sensor.koshachii_lotok_zamena_osvezhitelia_next_due` | Замена освежителя Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.koshachii_lotok_zamena_osvezhitelia_next_due_2` | Замена освежителя Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.obj_da9bb19a447d_obj_72cb2501d376_days_until_due` | Замена батареек в освежителе Дней до срока | отключена: integration; нет в states | d |
| `sensor.obj_da9bb19a447d_obj_c358e6639dba_days_until_due` | Замена освежителя Дней до срока | отключена: integration; нет в states | d |
| `sensor.obj_da9bb19a447d_obj_fc8c7bcc56bd_days_until_due` | Купить наполнитель Дней до срока | отключена: integration; нет в states | d |
### Магистральные фильтры очистки воды

- Производитель: Гидротек.
- Модель: Нитяной SWF 5мкм 10SL.
- Интеграции: maintenance_supporter.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.magistralnye_filtry_ochistki_vody_zamena_overdue_2` | Магистральные фильтры очистки воды Замена просрочено | загружена | problem |
| `button.magistralnye_filtry_ochistki_vody_zamena_complete_2` | Магистральные фильтры очистки воды Замена Выполнить | загружена | — |
| `button.magistralnye_filtry_ochistki_vody_zamena_reset_2` | Магистральные фильтры очистки воды Замена Сбросить | загружена | — |
| `button.magistralnye_filtry_ochistki_vody_zamena_skip_2` | Магистральные фильтры очистки воды Замена Пропустить | загружена | — |
| `sensor.magistralnye_filtry_ochistki_vody_zamena_2` | Магистральные фильтры очистки воды Замена | загружена | enum |
| `sensor.magistralnye_filtry_ochistki_vody_zamena_next_due` | Замена Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.magistralnye_filtry_ochistki_vody_zamena_next_due_2` | Замена Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.obj_66c642fb94a3_obj_cd207be3c612_days_until_due` | Замена Дней до срока | отключена: integration; нет в states | d |
### Питьевой фонтан

- Производитель: Petkit.
- Модель: Eversweet Pro UVC.
- Интеграции: maintenance_supporter.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.pitevoi_fontan_myte_overdue_2` | Питьевой фонтан Мытье просрочено | загружена | problem |
| `binary_sensor.pitevoi_fontan_zamena_filtra_overdue_2` | Питьевой фонтан Замена фильтра просрочено | загружена | problem |
| `button.pitevoi_fontan_myte_complete_2` | Питьевой фонтан Мытье Выполнить | загружена | — |
| `button.pitevoi_fontan_myte_reset_2` | Питьевой фонтан Мытье Сбросить | загружена | — |
| `button.pitevoi_fontan_myte_skip_2` | Питьевой фонтан Мытье Пропустить | загружена | — |
| `button.pitevoi_fontan_zamena_filtra_complete_2` | Питьевой фонтан Замена фильтра Выполнить | загружена | — |
| `button.pitevoi_fontan_zamena_filtra_reset_2` | Питьевой фонтан Замена фильтра Сбросить | загружена | — |
| `button.pitevoi_fontan_zamena_filtra_skip_2` | Питьевой фонтан Замена фильтра Пропустить | загружена | — |
| `sensor.obj_56e9b6a71cdf_obj_4bcddaf92ddb_days_until_due` | Мытье Дней до срока | отключена: integration; нет в states | d |
| `sensor.obj_56e9b6a71cdf_obj_722e392352e3_days_until_due` | Замена фильтра Дней до срока | отключена: integration; нет в states | d |
| `sensor.pitevoi_fontan_myte_2` | Питьевой фонтан Мытье | загружена | enum |
| `sensor.pitevoi_fontan_myte_next_due` | Мытье Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.pitevoi_fontan_myte_next_due_2` | Мытье Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.pitevoi_fontan_zamena_filtra_2` | Питьевой фонтан Замена фильтра | загружена | enum |
| `sensor.pitevoi_fontan_zamena_filtra_next_due` | Замена фильтра Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.pitevoi_fontan_zamena_filtra_next_due_2` | Замена фильтра Следующий срок | отключена: integration; нет в states | timestamp |
### Посудомоечная машина

- Производитель: BEKO.
- Модель: BDIS38120Q.
- Интеграции: maintenance_supporter.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.posudomoechnaia_mashina_myte_pri_povyshennoi_temperature_overdue_2` | Посудомоечная машина Мытье при повышенной температуре просрочено | загружена | problem |
| `button.posudomoechnaia_mashina_myte_pri_povyshennoi_temperature_complete_2` | Посудомоечная машина Мытье при повышенной температуре Выполнить | загружена | — |
| `button.posudomoechnaia_mashina_myte_pri_povyshennoi_temperature_reset_2` | Посудомоечная машина Мытье при повышенной температуре Сбросить | загружена | — |
| `button.posudomoechnaia_mashina_myte_pri_povyshennoi_temperature_skip_2` | Посудомоечная машина Мытье при повышенной температуре Пропустить | загружена | — |
| `sensor.obj_1873eba961fa_obj_c9d1ef9ac46d_days_until_due` | Мытье при повышенной температуре Дней до срока | отключена: integration; нет в states | d |
| `sensor.posudomoechnaia_mashina_myte_pri_povyshennoi_temperature_2` | Посудомоечная машина Мытье при повышенной температуре | загружена | enum |
| `sensor.posudomoechnaia_mashina_myte_pri_povyshennoi_temperature_next_due` | Мытье при повышенной температуре Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.posudomoechnaia_mashina_myte_pri_povyshennoi_temperature_next_due_2` | Мытье при повышенной температуре Следующий срок | отключена: integration; нет в states | timestamp |
### Приточная установка

- Производитель: Horynize.
- Модель: CF-700.
- Интеграции: maintenance_supporter.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.pritochnaia_ustanovka_tekhobsluzhivanie_overdue_2` | Приточная установка Техобслуживание просрочено | загружена | problem |
| `binary_sensor.pritochnaia_ustanovka_zamena_filtra_e11_overdue_2` | Приточная установка Замена фильтра E11 просрочено | загружена | problem |
| `binary_sensor.pritochnaia_ustanovka_zamena_filtra_g4_overdue_2` | Приточная установка Замена фильтра G4 просрочено | загружена | problem |
| `button.pritochnaia_ustanovka_tekhobsluzhivanie_complete_2` | Приточная установка Техобслуживание Выполнить | загружена | — |
| `button.pritochnaia_ustanovka_tekhobsluzhivanie_reset_2` | Приточная установка Техобслуживание Сбросить | загружена | — |
| `button.pritochnaia_ustanovka_tekhobsluzhivanie_skip_2` | Приточная установка Техобслуживание Пропустить | загружена | — |
| `button.pritochnaia_ustanovka_zamena_filtra_e11_complete_2` | Приточная установка Замена фильтра E11 Выполнить | загружена | — |
| `button.pritochnaia_ustanovka_zamena_filtra_e11_reset_2` | Приточная установка Замена фильтра E11 Сбросить | загружена | — |
| `button.pritochnaia_ustanovka_zamena_filtra_e11_skip_2` | Приточная установка Замена фильтра E11 Пропустить | загружена | — |
| `button.pritochnaia_ustanovka_zamena_filtra_g4_complete_2` | Приточная установка Замена фильтра G4 Выполнить | загружена | — |
| `button.pritochnaia_ustanovka_zamena_filtra_g4_reset_2` | Приточная установка Замена фильтра G4 Сбросить | загружена | — |
| `button.pritochnaia_ustanovka_zamena_filtra_g4_skip_2` | Приточная установка Замена фильтра G4 Пропустить | загружена | — |
| `sensor.obj_57fecacc4de2_e11_days_until_due` | Замена фильтра E11 Дней до срока | отключена: integration; нет в states | d |
| `sensor.obj_57fecacc4de2_g4_days_until_due` | Замена фильтра G4 Дней до срока | отключена: integration; нет в states | d |
| `sensor.obj_57fecacc4de2_obj_f9a4603a6c44_days_until_due` | Техобслуживание Дней до срока | отключена: integration; нет в states | d |
| `sensor.pritochnaia_ustanovka_filtr_e11_stock` | Приточная установка Фильтр Е11 stock | загружена | — |
| `sensor.pritochnaia_ustanovka_filtr_g4_stock` | Приточная установка Фильтр G4 stock | загружена | — |
| `sensor.pritochnaia_ustanovka_tekhobsluzhivanie_2` | Приточная установка Техобслуживание | загружена | enum |
| `sensor.pritochnaia_ustanovka_tekhobsluzhivanie_next_due` | Техобслуживание Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.pritochnaia_ustanovka_tekhobsluzhivanie_next_due_2` | Техобслуживание Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.pritochnaia_ustanovka_zamena_filtra_e11_2` | Приточная установка Замена фильтра E11 | загружена | enum |
| `sensor.pritochnaia_ustanovka_zamena_filtra_e11_next_due` | Замена фильтра E11 Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.pritochnaia_ustanovka_zamena_filtra_e11_next_due_2` | Замена фильтра E11 Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.pritochnaia_ustanovka_zamena_filtra_g4_2` | Приточная установка Замена фильтра G4 | загружена | enum |
| `sensor.pritochnaia_ustanovka_zamena_filtra_g4_next_due` | Замена фильтра G4 Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.pritochnaia_ustanovka_zamena_filtra_g4_next_due_2` | Замена фильтра G4 Следующий срок | отключена: integration; нет в states | timestamp |
### Система кондиционирования

- Производитель: Haier.
- Модель: 3U55S2SR5FA/AS25S2SF2FA-B/AS20PSHRA-M.
- Интеграции: maintenance_supporter.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.sistema_konditsionirovaniia_tekhobsluzhivanie_overdue_2` | Система кондиционирования Техобслуживание просрочено | загружена | problem |
| `button.sistema_konditsionirovaniia_tekhobsluzhivanie_complete_2` | Система кондиционирования Техобслуживание Выполнить | загружена | — |
| `button.sistema_konditsionirovaniia_tekhobsluzhivanie_reset_2` | Система кондиционирования Техобслуживание Сбросить | загружена | — |
| `button.sistema_konditsionirovaniia_tekhobsluzhivanie_skip_2` | Система кондиционирования Техобслуживание Пропустить | загружена | — |
| `sensor.obj_04ec0b54069e_obj_f9a4603a6c44_days_until_due` | Техобслуживание Дней до срока | отключена: integration; нет в states | d |
| `sensor.sistema_konditsionirovaniia_tekhobsluzhivanie_2` | Система кондиционирования Техобслуживание | загружена | enum |
| `sensor.sistema_konditsionirovaniia_tekhobsluzhivanie_next_due` | Техобслуживание Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.sistema_konditsionirovaniia_tekhobsluzhivanie_next_due_2` | Техобслуживание Следующий срок | отключена: integration; нет в states | timestamp |
### Система увлажнения

- Производитель: AirWet.
- Модель: —.
- Интеграции: maintenance_supporter.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.sistema_uvlazhneniia_tekhobsluzhivanie_overdue_2` | Система увлажнения Техобслуживание просрочено | загружена | problem |
| `button.sistema_uvlazhneniia_tekhobsluzhivanie_complete_2` | Система увлажнения Техобслуживание Выполнить | загружена | — |
| `button.sistema_uvlazhneniia_tekhobsluzhivanie_reset_2` | Система увлажнения Техобслуживание Сбросить | загружена | — |
| `button.sistema_uvlazhneniia_tekhobsluzhivanie_skip_2` | Система увлажнения Техобслуживание Пропустить | загружена | — |
| `sensor.obj_17467d5f6550_obj_f9a4603a6c44_days_until_due` | Техобслуживание Дней до срока | отключена: integration; нет в states | d |
| `sensor.sistema_uvlazhneniia_tekhobsluzhivanie_2` | Система увлажнения Техобслуживание | загружена | enum |
| `sensor.sistema_uvlazhneniia_tekhobsluzhivanie_next_due` | Техобслуживание Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.sistema_uvlazhneniia_tekhobsluzhivanie_next_due_2` | Техобслуживание Следующий срок | отключена: integration; нет в states | timestamp |
### Фильтр питьевой воды

- Производитель: atoll.
- Модель: TWIST 600.
- Интеграции: maintenance_supporter.

| Entity ID | Имя | Статус | Единица / класс |
| --- | --- | --- | --- |
| `binary_sensor.filtr_pitevoi_vody_zamena_filtra_overdue_2` | Фильтр питьевой воды Замена фильтра PPC просрочено | загружена | problem |
| `binary_sensor.filtr_pitevoi_vody_zamena_membrany_overdue_2` | Фильтр питьевой воды Замена мембраны RO просрочено | загружена | problem |
| `button.filtr_pitevoi_vody_zamena_filtra_complete_2` | Фильтр питьевой воды Замена фильтра PPC Выполнить | загружена | — |
| `button.filtr_pitevoi_vody_zamena_filtra_reset_2` | Фильтр питьевой воды Замена фильтра PPC Сбросить | загружена | — |
| `button.filtr_pitevoi_vody_zamena_filtra_skip_2` | Фильтр питьевой воды Замена фильтра PPC Пропустить | загружена | — |
| `button.filtr_pitevoi_vody_zamena_membrany_complete_2` | Фильтр питьевой воды Замена мембраны RO Выполнить | загружена | — |
| `button.filtr_pitevoi_vody_zamena_membrany_reset_2` | Фильтр питьевой воды Замена мембраны RO Сбросить | загружена | — |
| `button.filtr_pitevoi_vody_zamena_membrany_skip_2` | Фильтр питьевой воды Замена мембраны RO Пропустить | загружена | — |
| `sensor.filtr_pitevoi_vody_zamena_filtra_2` | Фильтр питьевой воды Замена фильтра PPC | загружена | enum |
| `sensor.filtr_pitevoi_vody_zamena_filtra_next_due` | Замена фильтра Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.filtr_pitevoi_vody_zamena_filtra_next_due_2` | Замена фильтра PPC Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.filtr_pitevoi_vody_zamena_membrany_2` | Фильтр питьевой воды Замена мембраны RO | загружена | enum |
| `sensor.filtr_pitevoi_vody_zamena_membrany_next_due` | Замена мембраны Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.filtr_pitevoi_vody_zamena_membrany_next_due_2` | Замена мембраны RO Следующий срок | отключена: integration; нет в states | timestamp |
| `sensor.obj_36d8a987ab6d_obj_722e392352e3_days_until_due` | Замена фильтра PPC Дней до срока | отключена: integration; нет в states | d |
| `sensor.obj_36d8a987ab6d_obj_7b3d87334850_days_until_due` | Замена мембраны RO Дней до срока | отключена: integration; нет в states | d |

## Entity без привязки к устройству


### automation

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `automation.bathroom_floor_cycle` | bathroom_floor_cycle | Система | automation | загружена |
| `automation.bedroom_air_conditioner_backlight` | bedroom_air_conditioner_backlight | Спальня | automation | загружена |
| `automation.change_audio_system_signal_source` | change_audio_system_signal_source | Гостиная | automation | загружена |
| `automation.end_lavalamp_warming` | end_lavalamp_warming | Спальня | automation | загружена |
| `automation.haier_yaha_sync` | haier_yaha_sync | Система | automation | загружена |
| `automation.kids_room_air_conditioner_backlight` | kids_room_air_conditioner_backlight | Детская | automation | загружена |
| `automation.laundry_floor_cycle` | laundry_floor_cycle | Система | automation | загружена |
| `automation.living_room_air_conditioner_backlight` | living_room_air_conditioner_backlight | Гостиная | automation | загружена |
| `automation.notify_about_activity_ended` | notify_about_activity_ended | Система | automation | загружена |
| `automation.notify_about_door_not_locked` | notify_about_door_not_locked | Коридор | automation | загружена |
| `automation.notify_about_download_completed` | notify_about_download_completed | Система | automation | загружена |
| `automation.notify_about_homeassistant_started` | notify_about_homeassistant_started | Система | automation | загружена |
| `automation.notify_about_homeassistant_stopped` | notify_about_homeassistant_stopped | Система | automation | загружена |
| `automation.notify_about_low_humidity` | notify_about_low_humidity | Система | automation | загружена |
| `automation.notify_about_petkit_low_level` | notify_about_petkit_low_level | Кухня | automation | загружена |
| `automation.notify_about_ping_google_fail` | notify_about_ping_google_fail | Система | automation | загружена |
| `automation.notify_about_ping_google_ok` | notify_about_ping_google_ok | Система | automation | загружена |
| `automation.notify_about_power_off` | notify_about_power_off | Система | automation | загружена |
| `automation.notify_about_power_on` | notify_about_power_on | Система | automation | загружена |
| `automation.notify_about_switch_state_changed` | notify_about_switch_state_changed | Система | automation | загружена |
| `automation.notify_about_water_leak` | notify_about_water_leak | Система | automation | загружена |
| `automation.oasis_climate_set_temperature` | oasis_climate_set_temperature | Балкон | automation | загружена |
| `automation.oasis_confirmed_sync_switch_after_start` | oasis_confirmed_sync_switch_after_start | Балкон | automation | загружена |
| `automation.oasis_confirmed_sync_switch_and_cancel_applying` | oasis_confirmed_sync_switch_and_cancel_applying | Балкон | automation | загружена |
| `automation.oasis_set_target_fan_speed` | oasis_set_target_fan_speed | Балкон | automation | загружена |
| `automation.oasis_set_target_temperature` | oasis_set_target_temperature | Балкон | automation | загружена |
| `automation.oasis_sync_fan_speed_from_sensor_to_input_number` | oasis_sync_fan_speed_from_sensor_to_input_number | Балкон | automation | загружена |
| `automation.oasis_sync_temperature_from_sensor_to_climate` | oasis_sync_temperature_from_sensor_to_climate | Балкон | automation | загружена |
| `automation.oasis_sync_temperature_from_sensor_to_input_number` | oasis_sync_temperature_from_sensor_to_input_number | Балкон | automation | загружена |
| `automation.petkit_cat_feeder_reboot` | petkit_cat_feeder_reboot | Кухня | automation | загружена |
| `automation.power_sensors_heartbeat_15s` | power_sensors_heartbeat_15s | Система | automation | загружена |
| `automation.select_kitchen_water_valve_state` | select_kitchen_water_valve_state | Коридор | automation | загружена |
| `automation.select_laundry_water_valve_state` | select_laundry_water_valve_state | Прачечная | automation | загружена |
| `automation.sync_kitchen_hood_fan_state` | sync_kitchen_hood_fan_state | Кухня | automation | загружена |
| `automation.sync_kitchen_hood_led_state` | sync_kitchen_hood_led_state | Кухня | automation | загружена |
| `automation.turn_off_vertical_vacuum_cleaner_charging_after_4h` | turn_off_vertical_vacuum_cleaner_charging_after_4h | Прачечная | automation | загружена |
| `automation.xgimi_sync_state` | xgimi_sync_state | Гостиная | automation | загружена |
| `automation.yandex_station_volume_default` | yandex_station_volume_default | Система | automation | загружена |

### binary_sensor

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `binary_sensor.3d_printer_activity` | Печать | Кладовка | template | загружена |
| `binary_sensor.backups_stale` | Backups Stale | — | — | загружена |
| `binary_sensor.dishwasher_activity` | Мытье посуды | Кухня | template | загружена |
| `binary_sensor.drying_machine_activity` | Сушка белья | Прачечная | template | загружена |
| `binary_sensor.fridge_activity` | Fridge Activity | Кухня | template | загружена |
| `binary_sensor.oasis_power_state_applying` | Oasis Power State Applying | Балкон | template | загружена |
| `binary_sensor.oasis_power_state_confirmed` | Oasis Power State Confirmed | Балкон | template | загружена |
| `binary_sensor.washing_machine_activity` | Стирка | Прачечная | template | загружена |

### button

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `button.audio_system_off` | Audio System Off | Гостиная | template | загружена |
| `button.audio_system_volume_down` | Audio System Volume Down | Гостиная | template | загружена |
| `button.audio_system_volume_up` | Audio System Volume Up | Гостиная | template | загружена |

### calendar

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `calendar.maintenance_schedule` | Maintenance Schedule | — | maintenance_supporter | загружена |

### climate

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `climate.oasis` | Oasis | Балкон | generic_thermostat | загружена |

### conversation

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `conversation.home_assistant` | Home Assistant | — | — | загружена |

### cover

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `cover.kitchen_water_valve` | Вода в кухне | Коридор | template | загружена |
| `cover.laundry_water_valve` | Вода в санузлах | Прачечная | template | загружена |

### input_boolean

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `input_boolean.bathroom_floor_cycle` | Bathroom floor cycle | Ванная | input_boolean | загружена |
| `input_boolean.kitchen_hood_fan_state` | Kitchen hood fan state | Кухня | input_boolean | загружена |
| `input_boolean.kitchen_hood_led_state` | Kitchen hood LED state | Кухня | input_boolean | загружена |
| `input_boolean.laundry_floor_cycle` | Laundry floor cycle | Прачечная | input_boolean | загружена |

### input_button

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `input_button.wifi_qr` | Wi-Fi QR | Система | input_button | загружена |

### input_datetime

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `input_datetime.electricity_down_at` | Electricity Down At | Система | input_datetime | загружена |
| `input_datetime.internet_down_at` | Internet Down At | Система | input_datetime | загружена |

### input_number

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `input_number.bathroom_floor_heat_minutes` | Bathroom floor heat time | Ванная | input_number | загружена |
| `input_number.laundry_floor_heat_minutes` | Laundry floor heat time | Прачечная | input_number | загружена |
| `input_number.oasis_target_fan_speed` | Oasis Target Fan Speed | Балкон | input_number | загружена |
| `input_number.oasis_target_temperature` | Oasis Target Temperature | Балкон | input_number | загружена |

### input_select

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `input_select.audio_system_signal_source` | Источник сигнала колонок | Гостиная | input_select | загружена |
| `input_select.kitchen_water_valve_state` | Kitchen water valve state | Коридор | input_select | загружена |
| `input_select.laundry_water_valve_state` | Laundry water valve state | Прачечная | input_select | загружена |
| `input_select.xgimi_power_state` | Xgimi power state | — | input_select | загружена |

### light

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `light.bathroom_floor_heating` | Bathroom Floor Heating | Ванная | template | загружена |
| `light.kitchen_hood_led_ext` | Kitchen Hood LED Ext | Кухня | template | загружена |
| `light.laundry_floor_heating` | Laundry Floor Heating | Прачечная | template | загружена |

### person

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `person.headsoft` | Миша | — | person | загружена |
| `person.lina` | Лина | — | person | загружена |

### scene

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `scene.after_cinema` | After Cinema | Система | homeassistant | загружена |
| `scene.cinema` | Cinema | Система | homeassistant | загружена |
| `scene.home` | Home | Система | homeassistant | загружена |
| `scene.leave` | Leave | Система | homeassistant | загружена |
| `scene.night` | Night | Система | homeassistant | загружена |
| `scene.sleep` | Sleep | Система | homeassistant | загружена |
| `scene.work` | Work | Система | homeassistant | загружена |

### script

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `script.cat_spa` | Cat spa | Кухня | script | загружена |
| `script.feed_cats` | Feed Cats | Кухня | script | загружена |
| `script.kitchen_water_valve_toggle_by_state` | Kitchen water valve toggle by state | Кухня | script | загружена |
| `script.laundry_water_valve_toggle_by_state` | Laundry water valve toggle by state | Прачечная | script | загружена |
| `script.loggia_heat` | Loggia heat | Балкон | script | загружена |

### sensor

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `sensor.3d_printer_plug_energy_monthly` | 3D Printer Plug Energy Monthly | Кладовка | utility_meter | загружена |
| `sensor.air_conditioner_system_relay_energy_monthly` | Air Conditioner System Energy Monthly | Коридор | utility_meter | загружена |
| `sensor.airmonitor2_tvoc_ug` | AirMonitor2 TVOC ug | Спальня | template | загружена |
| `sensor.backup_state` | Backup State | — | — | загружена |
| `sensor.bathroom_heat_floor_current_temperature` | Bathroom Heat Floor Current Temperature | Ванная | template | загружена |
| `sensor.bathroom_heat_floor_energy` | Bathroom Heat Floor Energy | Ванная | integration | загружена |
| `sensor.bathroom_heat_floor_energy_monthly` | Bathroom Heat Floor Energy Monthly | Ванная | utility_meter | загружена |
| `sensor.bathroom_heat_floor_power` | Bathroom heat floor power | Ванная | template | загружена |
| `sensor.bathroom_heat_wall_current_temperature` | Bathroom Heat Wall Current Temperature | Ванная | template | загружена |
| `sensor.bathroom_heat_wall_energy` | Bathroom Heat Wall Energy | Ванная | integration | загружена |
| `sensor.bathroom_heat_wall_energy_monthly` | Bathroom Heat Wall Energy Monthly | Ванная | utility_meter | загружена |
| `sensor.bathroom_heat_wall_power` | Bathroom Heat Wall Power | Ванная | template | загружена |
| `sensor.dishwasher_energy_monthly` | Dishwasher Energy Monthly | Кухня | utility_meter | загружена |
| `sensor.drying_machine_energy_monthly` | Drying Machine Energy Monthly | Прачечная | utility_meter | загружена |
| `sensor.efekta_smart_aq_box_tvoc_ug` | efekta_smart_aq_box_tvoc_ug | Кухня | template | загружена |
| `sensor.fireplace_plug_energy_monthly` | Fireplace Plug Energy Monthly | — | utility_meter | загружена |
| `sensor.fresh_element_solo_1_dispensed_stable` | Fresh Element Solo 1 Dispensed Stable | — | template | загружена |
| `sensor.fresh_element_solo_2_dispensed_stable` | Fresh Element Solo 2 Dispensed Stable | — | template | загружена |
| `sensor.fridge_socket_energy_monthly` | Fridge Socket Energy Monthly | Кухня | utility_meter | загружена |
| `sensor.hall_under_wardrobe_socket_energy_monthly` | Hall Under Wardrobe Socket Energy Monthly | Коридор | utility_meter | загружена |
| `sensor.humidifier_system_relay_energy_monthly` | Humidifier System Energy Monthly | Коридор | utility_meter | загружена |
| `sensor.kitchen_socket_energy_monthly` | Kitchen Socket Energy Monthly | Кухня | utility_meter | загружена |
| `sensor.laundry_heat_floor_current_temperature` | Laundry Heat Floor Current Temperature | Прачечная | template | загружена |
| `sensor.laundry_heat_floor_energy` | Laundry Heat Floor Energy | Прачечная | integration | загружена |
| `sensor.laundry_heat_floor_energy_monthly` | Laundry Heat Floor Energy Monthly | Прачечная | utility_meter | загружена |
| `sensor.laundry_heat_floor_power` | Laundry Heat Floor Power | Прачечная | template | загружена |
| `sensor.living_room_behind_sofa_socket_energy_monthly` | Living Room Behind Sofa Socket Energy Monthly | Гостиная | utility_meter | загружена |
| `sensor.loggia_heat_floor_current_temperature` | Loggia Heat Floor Current Temperature | Балкон | template | загружена |
| `sensor.loggia_heat_floor_energy` | Loggia Heat Floor Energy | Балкон | integration | загружена |
| `sensor.loggia_heat_floor_energy_monthly` | Loggia Heat Floor Energy Monthly | Балкон | utility_meter | загружена |
| `sensor.loggia_heat_floor_power` | Loggia Heat Floor Power | Балкон | template | загружена |
| `sensor.oasis_current_fan_speed` | Oasis Current Fan Speed | Балкон | modbus | загружена |
| `sensor.oasis_current_temperature` | Oasis Current Temperature | Балкон | modbus | загружена |
| `sensor.oasis_outdoor_temperature` | Oasis Outdoor Temperature | Балкон | modbus | загружена |
| `sensor.oasis_target_fan_speed` | Oasis Target Fan Speed | Балкон | modbus | загружена |
| `sensor.oasis_target_temperature` | Oasis Target Temperature | Балкон | modbus | загружена |
| `sensor.other_power_consumers_energy` | Other Power Consumers Energy | Коридор | integration | загружена |
| `sensor.other_power_consumers_energy_monthly` | Other Power Consumers Energy Monthly | Коридор | utility_meter | загружена |
| `sensor.other_power_consumers_power` | Other Power Consumers Power | Коридор | template | загружена |
| `sensor.rpi_cpu_temperature` | RPi CPU Temperature | Система | command_line | загружена |
| `sensor.smb_disk_free_elements` | SMB Disk Free Elements | Кладовка | command_line | загружена |
| `sensor.smb_disk_free_mypassport` | SMB Disk Free MyPassport | Кладовка | command_line | загружена |
| `sensor.smb_disk_usage_percent_elements` | SMB Disk Usage Percent Elements | Кладовка | command_line | загружена |
| `sensor.smb_disk_usage_percent_mypassport` | SMB Disk Usage Percent MyPassport | Кладовка | command_line | загружена |
| `sensor.snmp_router_download_speed` | SNMP Router Download Speed | Система | template | загружена |
| `sensor.snmp_router_incoming_bytes` | SNMP Router Incoming Bytes | Система | snmp | загружена |
| `sensor.snmp_router_incoming_bytes_derivative` | SNMP Router Incoming Bytes Derivative | — | — | загружена |
| `sensor.snmp_router_incoming_bytes_monthly` | SNMP Router Incoming Bytes Monthly | Система | utility_meter | загружена |
| `sensor.snmp_router_outgoing_bytes` | SNMP Router Outgoing Bytes | Система | snmp | загружена |
| `sensor.snmp_router_outgoing_bytes_derivative` | SNMP Router Outgoing Bytes Derivative | — | — | загружена |
| `sensor.snmp_router_outgoing_bytes_monthly` | SNMP Router Outgoing Bytes Monthly | Система | utility_meter | загружена |
| `sensor.snmp_router_upload_speed` | SNMP Router Upload Speed | Система | template | загружена |
| `sensor.store_room_socket_energy_monthly` | Store Room Socket Energy Monthly | Кладовка | utility_meter | загружена |
| `sensor.total_cpu_usage` | Total CPU Usage | — | template | загружена |
| `sensor.total_ram_usage` | Total RAM Usage | — | template | загружена |
| `sensor.towel_dryer_current_temperature` | Towel Dryer Current Temperature | Ванная | template | загружена |
| `sensor.towel_dryer_current_temperature_derivative` | Towel Dryer Temperature Direction | Ванная | derivative | загружена |
| `sensor.towel_dryer_energy` | Towel Dryer Energy | Ванная | integration | загружена |
| `sensor.towel_dryer_energy_monthly` | Towel Dryer Energy Monthly | Ванная | utility_meter | загружена |
| `sensor.towel_dryer_power` | Towel Dryer Power | Ванная | template | загружена |
| `sensor.ventilation_system_relay_avg_current` | Ventilation System Relay Avg Current | Коридор | filter | загружена |
| `sensor.ventilation_system_relay_avg_power` | Ventilation System Relay Avg Power | Коридор | filter | загружена |
| `sensor.ventilation_system_relay_current_sampled` | Ventilation System Relay Current Sampled | — | template | загружена |
| `sensor.ventilation_system_relay_energy_monthly` | Ventilation System Energy Monthly | Коридор | utility_meter | загружена |
| `sensor.ventilation_system_relay_power_sampled` | Ventilation System Relay Power Sampled | Коридор | template | загружена |
| `sensor.washing_machine_energy_monthly` | Washing Machine Energy Monthly | Прачечная | utility_meter | загружена |
| `sensor.zemismart_smp01_avg_current` | Zemismart SMP01 Avg Current | Коридор | filter | загружена |
| `sensor.zemismart_smp01_avg_power` | Zemismart SMP01 Avg Power | Коридор | filter | загружена |
| `sensor.zemismart_smp01_current_sampled` | Zemismart SMP01 Current Sampled | — | template | загружена |
| `sensor.zemismart_smp01_energy_daily` | Zemismart SMP01 Energy Daily | Коридор | utility_meter | загружена |
| `sensor.zemismart_smp01_energy_monthly` | Zemismart SMP01 Energy Monthly | Коридор | utility_meter | загружена |
| `sensor.zemismart_smp01_power_sampled` | Zemismart SMP01 Power Sampled | Коридор | template | загружена |

### sun

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `sun.sun` | Sun | — | — | загружена |

### switch

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `switch.bedroom_air_conditioner` | Bedroom air conditioner | Спальня | template | загружена |
| `switch.esp_pc_power` | ESP PC Power | — | template | загружена |
| `switch.kids_room_air_conditioner` | Kids room air conditioner | Детская | template | загружена |
| `switch.kitchen_hood_fan_ext` | Kitchen Hood Fan Ext | Кухня | template | загружена |
| `switch.kitchen_water_valve_switch` | Kitchen water valve switch | Кухня | template | загружена |
| `switch.laundry_water_valve_switch` | Laundry water valve switch | Прачечная | template | загружена |
| `switch.living_room_air_conditioner` | Living room air conditioner | Гостиная | template | загружена |
| `switch.oasis_power` | Oasis Power | Балкон | template | загружена |
| `switch.oasis_power_dummy` | Oasis Power Dummy | — | — | загружена |
| `switch.xgimi_horizon_ultra` | Xgimi Horizon Ultra | Гостиная | template | загружена |

### timer

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `timer.oasis_state_applying` | timer.oasis_state_applying | Балкон | timer | загружена |

### todo

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `todo.maintenance` | Maintenance | — | maintenance_supporter | загружена |

### update

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `update.firmware` | Обновление прошивки | — | — | загружена |
| `update.firmware_2` | Обновление прошивки | — | — | загружена |

### zone

| Entity ID | Имя | Комната | Интеграция | Статус |
| --- | --- | --- | --- | --- |
| `zone.home` | Home Assistant | — | — | загружена |

## Связи с YAML репозитория

Точный поиск entity_id в конфигурации, автоматизациях, сценах, скриптах и копиях dashboard. В списке только найденные ссылки; UI и автономные правила Aqara могут содержать дополнительные зависимости.

| Entity ID | Места использования |
| --- | --- |
| `binary_sensor.3d_printer_activity` | `automations.yaml:218`<br>`homekit.yaml:405`<br>`homekit.yaml:426`<br>`www/dashboards/home.yaml:945`<br>`yaha_cloud.yaml:94`<br>`yaha_cloud.yaml:484` |
| `binary_sensor.3d_printer_motion_sensor_occupancy` | `configuration.yaml:673` |
| `binary_sensor.bathroom_bath_water_leak_sensor` | `automations.yaml:254`<br>`automations.yaml:271`<br>`homekit.yaml:13`<br>`homekit.yaml:38`<br>`www/dashboards/systems.yaml:1157` |
| `binary_sensor.bathroom_drain_water_leak_sensor` | `automations.yaml:256`<br>`automations.yaml:273`<br>`homekit.yaml:14`<br>`homekit.yaml:42`<br>`www/dashboards/systems.yaml:1163` |
| `binary_sensor.bathroom_installation_water_leak_sensor` | `automations.yaml:253`<br>`automations.yaml:270`<br>`homekit.yaml:15`<br>`homekit.yaml:46`<br>`www/dashboards/systems.yaml:1154` |
| `binary_sensor.bathroom_sink_water_leak_sensor` | `automations.yaml:255`<br>`automations.yaml:272`<br>`homekit.yaml:16`<br>`homekit.yaml:50`<br>`www/dashboards/systems.yaml:1160` |
| `binary_sensor.dishwasher_activity` | `automations.yaml:217`<br>`automations.yaml:231`<br>`homekit.yaml:222`<br>`homekit.yaml:241`<br>`www/dashboards/home.yaml:24`<br>`yaha_cloud.yaml:63`<br>`yaha_cloud.yaml:335` |
| `binary_sensor.drying_machine_activity` | `automations.yaml:216`<br>`homekit.yaml:319`<br>`homekit.yaml:343`<br>`www/dashboards/home.yaml:1242`<br>`yaha_cloud.yaml:81`<br>`yaha_cloud.yaml:418` |
| `binary_sensor.electricity_outage_sensor` | `automations.yaml:94`<br>`automations.yaml:118`<br>`automations.yaml:994`<br>`automations.yaml:1031`<br>`automations.yaml:1058`<br>`www/dashboards/systems.yaml:719`<br>`www/dashboards/systems.yaml:1008` |
| `binary_sensor.eversweet_3_pro_uvc_water_level` | `automations.yaml:290`<br>`automations.yaml:296`<br>`www/dashboards/systems.yaml:627` |
| `binary_sensor.fresh_element_solo_1_food_level` | `automations.yaml:288`<br>`www/dashboards/systems.yaml:520`<br>`www/dashboards/systems.yaml:531` |
| `binary_sensor.fresh_element_solo_2_food_level` | `automations.yaml:289`<br>`www/dashboards/systems.yaml:581`<br>`www/dashboards/systems.yaml:592` |
| `binary_sensor.fridge_activity` | `www/dashboards/home.yaml:41` |
| `binary_sensor.hall_collector_water_leak_sensor` | `automations.yaml:245`<br>`automations.yaml:262`<br>`homekit.yaml:142`<br>`homekit.yaml:163`<br>`www/dashboards/systems.yaml:1105` |
| `binary_sensor.hall_contact_sensor` | `automations.yaml:26`<br>`automations.yaml:30`<br>`automations.yaml:38`<br>`automations.yaml:50`<br>`homekit.yaml:135`<br>`homekit.yaml:145`<br>`www/dashboards/home.yaml:840`<br>`www/dashboards/systems.yaml:59`<br>`yaha_cloud.yaml:42`<br>`yaha_cloud.yaml:240` |
| `binary_sensor.kitchen_dishwasher_water_leak_sensor` | `automations.yaml:247`<br>`automations.yaml:264`<br>`homekit.yaml:224`<br>`homekit.yaml:247`<br>`www/dashboards/systems.yaml:1111` |
| `binary_sensor.kitchen_sink_water_leak_sensor` | `automations.yaml:246`<br>`automations.yaml:263`<br>`homekit.yaml:223`<br>`homekit.yaml:243`<br>`www/dashboards/systems.yaml:1108` |
| `binary_sensor.laundry_collector_water_leak_sensor` | `automations.yaml:248`<br>`automations.yaml:265`<br>`homekit.yaml:320`<br>`homekit.yaml:345`<br>`www/dashboards/systems.yaml:1131` |
| `binary_sensor.laundry_humidifier_water_leak_sensor` | `automations.yaml:250`<br>`automations.yaml:267`<br>`homekit.yaml:321`<br>`homekit.yaml:349`<br>`www/dashboards/systems.yaml:1137` |
| `binary_sensor.laundry_installation_water_leak_sensor` | `automations.yaml:249`<br>`automations.yaml:266`<br>`homekit.yaml:322`<br>`homekit.yaml:353`<br>`www/dashboards/systems.yaml:1134` |
| `binary_sensor.laundry_sink_water_leak_sensor` | `automations.yaml:252`<br>`automations.yaml:269`<br>`homekit.yaml:323`<br>`homekit.yaml:357`<br>`www/dashboards/systems.yaml:1143` |
| `binary_sensor.laundry_washing_machine_water_leak_sensor` | `automations.yaml:251`<br>`automations.yaml:268`<br>`homekit.yaml:324`<br>`homekit.yaml:361`<br>`www/dashboards/systems.yaml:1140` |
| `binary_sensor.oasis_power_state_applying` | `configuration.yaml:923`<br>`configuration.yaml:934`<br>`configuration.yaml:953` |
| `binary_sensor.oasis_power_state_confirmed` | `automations.yaml:886`<br>`automations.yaml:888`<br>`automations.yaml:908`<br>`configuration.yaml:925`<br>`configuration.yaml:937`<br>`configuration.yaml:956` |
| `binary_sensor.ping_8_8_8_8` | `automations.yaml:146`<br>`automations.yaml:167`<br>`automations.yaml:995`<br>`automations.yaml:1034`<br>`automations.yaml:1061`<br>`www/dashboards/systems.yaml:181`<br>`www/dashboards/systems.yaml:218` |
| `binary_sensor.ping_desktop_pc` | `configuration.yaml:839`<br>`configuration.yaml:841`<br>`configuration.yaml:845`<br>`configuration.yaml:852` |
| `binary_sensor.ping_xgimi` | `automations.yaml:563`<br>`automations.yaml:570`<br>`automations.yaml:1094`<br>`automations.yaml:1117`<br>`automations.yaml:1128`<br>`configuration.yaml:800`<br>`configuration.yaml:814`<br>`configuration.yaml:826` |
| `binary_sensor.smoke_sensor` | `homekit.yaml:143`<br>`homekit.yaml:167`<br>`www/dashboards/home.yaml:862`<br>`www/dashboards/systems.yaml:29`<br>`yaha_cloud.yaml:271` |
| `binary_sensor.washing_machine_activity` | `automations.yaml:215`<br>`homekit.yaml:318`<br>`homekit.yaml:341`<br>`www/dashboards/home.yaml:1225`<br>`yaha_cloud.yaml:80`<br>`yaha_cloud.yaml:414` |
| `button.audio_system_off` | `automations.yaml:334`<br>`automations.yaml:344`<br>`www/dashboards/home.yaml:168` |
| `button.audio_system_volume_down` | `www/dashboards/home.yaml:305`<br>`www/dashboards/home.yaml:312` |
| `button.audio_system_volume_up` | `www/dashboards/home.yaml:315`<br>`www/dashboards/home.yaml:322` |
| `button.esp_pc_power_button` | `configuration.yaml:842`<br>`configuration.yaml:849`<br>`configuration.yaml:856` |
| `button.eversweet_3_pro_uvc_reset_filter` | `www/dashboards/systems.yaml:655` |
| `button.fresh_element_solo_1_reset_desiccant` | `www/dashboards/systems.yaml:671` |
| `button.fresh_element_solo_2_reset_desiccant` | `www/dashboards/systems.yaml:687` |
| `climate.bathroom_heat_floor` | `automations.yaml:614`<br>`automations.yaml:618`<br>`automations.yaml:623`<br>`automations.yaml:641`<br>`automations.yaml:660`<br>`configuration.yaml:510`<br>`configuration.yaml:543`<br>`configuration.yaml:1003`<br>`www/dashboards/climate.yaml:695`<br>`www/dashboards/climate.yaml:705`<br>`www/dashboards/climate.yaml:719`<br>`www/dashboards/climate.yaml:722`<br>`www/dashboards/climate.yaml:726`<br>`www/dashboards/climate.yaml:729`<br>`www/dashboards/home.yaml:1140`<br>`www/dashboards/home.yaml:1144`<br>`www/dashboards/home.yaml:1165`<br>`www/dashboards/home.yaml:1168`<br>`www/dashboards/home.yaml:1172`<br>`www/dashboards/home.yaml:1175` |
| `climate.bathroom_heat_wall` | `configuration.yaml:515`<br>`configuration.yaml:548`<br>`homekit.yaml:10`<br>`homekit.yaml:28`<br>`www/dashboards/climate.yaml:748`<br>`www/dashboards/home.yaml:1119`<br>`yaha_cloud.yaml:21`<br>`yaha_cloud.yaml:143` |
| `climate.bedroom_radiator_thermostat` | `homekit.yaml:74`<br>`homekit.yaml:112`<br>`www/dashboards/climate.yaml:620`<br>`www/dashboards/home.yaml:622`<br>`yaha_cloud.yaml:39`<br>`yaha_cloud.yaml:219` |
| `climate.detskaia_haier_white` | `automations.yaml:1009`<br>`automations.yaml:1017`<br>`automations.yaml:1042`<br>`automations.yaml:1052`<br>`automations.yaml:1067`<br>`automations.yaml:1171`<br>`automations.yaml:1185`<br>`configuration.yaml:881`<br>`configuration.yaml:885`<br>`configuration.yaml:889`<br>`homekit.yaml:182`<br>`homekit.yaml:201`<br>`www/dashboards/climate.yaml:527`<br>`www/dashboards/home.yaml:767` |
| `climate.gostinaia_haier_black` | `automations.yaml:1007`<br>`automations.yaml:1015`<br>`automations.yaml:1040`<br>`automations.yaml:1050`<br>`automations.yaml:1065`<br>`automations.yaml:1093`<br>`automations.yaml:1099`<br>`automations.yaml:1109`<br>`configuration.yaml:859`<br>`configuration.yaml:863`<br>`configuration.yaml:867`<br>`homekit.yaml:267`<br>`homekit.yaml:294`<br>`www/dashboards/climate.yaml:471`<br>`www/dashboards/home.yaml:343` |
| `climate.kids_room_radiator_thermostat` | `homekit.yaml:181`<br>`homekit.yaml:197`<br>`www/dashboards/climate.yaml:650`<br>`www/dashboards/home.yaml:776`<br>`yaha_cloud.yaml:54`<br>`yaha_cloud.yaml:294` |
| `climate.laundry_heat_floor` | `automations.yaml:686`<br>`automations.yaml:690`<br>`automations.yaml:695`<br>`automations.yaml:713`<br>`automations.yaml:732`<br>`configuration.yaml:530`<br>`configuration.yaml:555`<br>`configuration.yaml:1028`<br>`www/dashboards/climate.yaml:817`<br>`www/dashboards/climate.yaml:827`<br>`www/dashboards/climate.yaml:841`<br>`www/dashboards/climate.yaml:844`<br>`www/dashboards/climate.yaml:848`<br>`www/dashboards/climate.yaml:851`<br>`www/dashboards/home.yaml:1279`<br>`www/dashboards/home.yaml:1283`<br>`www/dashboards/home.yaml:1304`<br>`www/dashboards/home.yaml:1307`<br>`www/dashboards/home.yaml:1311`<br>`www/dashboards/home.yaml:1314` |
| `climate.living_room_radiator_thermostat` | `homekit.yaml:266`<br>`homekit.yaml:290`<br>`www/dashboards/climate.yaml:590`<br>`www/dashboards/home.yaml:352`<br>`yaha_cloud.yaml:73`<br>`yaha_cloud.yaml:373` |
| `climate.loggia_heat_floor` | `configuration.yaml:535`<br>`configuration.yaml:560`<br>`homekit.yaml:372`<br>`homekit.yaml:381`<br>`scripts.yaml:56`<br>`scripts.yaml:72`<br>`www/dashboards/climate.yaml:919`<br>`www/dashboards/home.yaml:1376`<br>`yaha_cloud.yaml:86`<br>`yaha_cloud.yaml:436` |
| `climate.oasis` | `automations.yaml:895`<br>`automations.yaml:923`<br>`automations.yaml:932`<br>`automations.yaml:937`<br>`automations.yaml:941`<br>`automations.yaml:945`<br>`automations.yaml:954`<br>`automations.yaml:973`<br>`automations.yaml:979`<br>`yaha_cloud.yaml:85`<br>`yaha_cloud.yaml:432` |
| `climate.spalnia_haier_white` | `automations.yaml:1008`<br>`automations.yaml:1016`<br>`automations.yaml:1041`<br>`automations.yaml:1051`<br>`automations.yaml:1066`<br>`automations.yaml:1143`<br>`automations.yaml:1157`<br>`configuration.yaml:870`<br>`configuration.yaml:874`<br>`configuration.yaml:878`<br>`homekit.yaml:75`<br>`homekit.yaml:116`<br>`www/dashboards/climate.yaml:500`<br>`www/dashboards/home.yaml:613` |
| `climate.towel_dryer` | `configuration.yaml:521`<br>`configuration.yaml:540`<br>`homekit.yaml:9`<br>`homekit.yaml:26`<br>`www/dashboards/climate.yaml:772`<br>`www/dashboards/home.yaml:1129`<br>`yaha_cloud.yaml:20`<br>`yaha_cloud.yaml:139` |
| `cover.bedroom_curtain` | `homekit.yaml:73`<br>`homekit.yaml:110`<br>`scenes.yaml:47`<br>`scenes.yaml:125`<br>`scenes.yaml:194`<br>`scenes.yaml:241`<br>`scenes.yaml:261`<br>`www/dashboards/home.yaml:463`<br>`yaha_cloud.yaml:38`<br>`yaha_cloud.yaml:215` |
| `cover.kids_room_curtain` | `homekit.yaml:180`<br>`homekit.yaml:195`<br>`www/dashboards/home.yaml:757`<br>`yaha_cloud.yaml:53`<br>`yaha_cloud.yaml:290` |
| `cover.kitchen_water_valve` | `scripts.yaml:33`<br>`scripts.yaml:42`<br>`www/dashboards/systems.yaml:1094`<br>`yaha_cloud.yaml:62`<br>`yaha_cloud.yaml:331` |
| `cover.laundry_water_valve` | `scripts.yaml:9`<br>`scripts.yaml:18`<br>`www/dashboards/systems.yaml:1120`<br>`yaha_cloud.yaml:78`<br>`yaha_cloud.yaml:396` |
| `cover.living_room_curtain` | `homekit.yaml:264`<br>`homekit.yaml:286`<br>`scenes.yaml:243`<br>`scenes.yaml:263`<br>`www/dashboards/home.yaml:109`<br>`yaha_cloud.yaml:71`<br>`yaha_cloud.yaml:365` |
| `cover.living_room_roll_curtain` | `homekit.yaml:265`<br>`homekit.yaml:288`<br>`scenes.yaml:245`<br>`scenes.yaml:265`<br>`www/dashboards/home.yaml:115`<br>`yaha_cloud.yaml:72`<br>`yaha_cloud.yaml:369` |
| `input_boolean.bathroom_floor_cycle` | `automations.yaml:598`<br>`automations.yaml:603`<br>`automations.yaml:609`<br>`automations.yaml:628`<br>`automations.yaml:635`<br>`automations.yaml:646`<br>`automations.yaml:653`<br>`configuration.yaml:1005`<br>`configuration.yaml:1012`<br>`configuration.yaml:1016`<br>`homekit.yaml:8`<br>`homekit.yaml:24`<br>`yaha_cloud.yaml:19`<br>`yaha_cloud.yaml:135` |
| `input_boolean.kitchen_hood_fan_state` | `automations.yaml:760`<br>`configuration.yaml:893`<br>`configuration.yaml:899`<br>`configuration.yaml:902`<br>`configuration.yaml:909`<br>`configuration.yaml:912`<br>`configuration.yaml:919` |
| `input_boolean.kitchen_hood_led_state` | `automations.yaml:747`<br>`configuration.yaml:1053`<br>`configuration.yaml:1059`<br>`configuration.yaml:1062`<br>`configuration.yaml:1069`<br>`configuration.yaml:1072`<br>`configuration.yaml:1079` |
| `input_boolean.laundry_floor_cycle` | `automations.yaml:670`<br>`automations.yaml:675`<br>`automations.yaml:681`<br>`automations.yaml:700`<br>`automations.yaml:707`<br>`automations.yaml:718`<br>`automations.yaml:725`<br>`configuration.yaml:1030`<br>`configuration.yaml:1037`<br>`configuration.yaml:1041`<br>`homekit.yaml:315`<br>`homekit.yaml:331`<br>`yaha_cloud.yaml:77`<br>`yaha_cloud.yaml:400` |
| `input_button.wifi_qr` | `www/dashboards/systems.yaml:176`<br>`www/dashboards/systems.yaml:247` |
| `input_datetime.electricity_down_at` | `automations.yaml:110`<br>`automations.yaml:132` |
| `input_datetime.internet_down_at` | `automations.yaml:159`<br>`automations.yaml:181` |
| `input_number.bathroom_floor_heat_minutes` | `automations.yaml:631`<br>`automations.yaml:649`<br>`configuration.yaml:1008`<br>`configuration.yaml:1021` |
| `input_number.laundry_floor_heat_minutes` | `automations.yaml:703`<br>`automations.yaml:721`<br>`configuration.yaml:1033`<br>`configuration.yaml:1046` |
| `input_number.oasis_target_fan_speed` | `automations.yaml:827`<br>`automations.yaml:831`<br>`automations.yaml:835`<br>`automations.yaml:839`<br>`automations.yaml:851`<br>`automations.yaml:870`<br>`automations.yaml:876`<br>`www/dashboards/climate.yaml:250`<br>`www/dashboards/home.yaml:1363` |
| `input_number.oasis_target_temperature` | `automations.yaml:769`<br>`automations.yaml:773`<br>`automations.yaml:777`<br>`automations.yaml:781`<br>`automations.yaml:792`<br>`automations.yaml:811`<br>`automations.yaml:817`<br>`automations.yaml:947`<br>`automations.yaml:952`<br>`automations.yaml:981`<br>`scenes.yaml:45`<br>`scenes.yaml:123`<br>`scenes.yaml:192`<br>`www/dashboards/climate.yaml:239`<br>`www/dashboards/home.yaml:1358` |
| `input_select.audio_system_signal_source` | `automations.yaml:322`<br>`automations.yaml:326`<br>`scenes.yaml:247`<br>`scenes.yaml:267`<br>`www/dashboards/home.yaml:159`<br>`www/dashboards/home.yaml:173`<br>`www/dashboards/home.yaml:175`<br>`www/dashboards/home.yaml:183`<br>`www/dashboards/home.yaml:196`<br>`www/dashboards/home.yaml:204`<br>`www/dashboards/home.yaml:217`<br>`www/dashboards/home.yaml:225`<br>`www/dashboards/home.yaml:238`<br>`www/dashboards/home.yaml:246`<br>`www/dashboards/home.yaml:259`<br>`www/dashboards/home.yaml:267`<br>`www/dashboards/home.yaml:280`<br>`www/dashboards/home.yaml:288` |
| `input_select.kitchen_water_valve_state` | `automations.yaml:454`<br>`automations.yaml:463`<br>`automations.yaml:472`<br>`automations.yaml:481`<br>`automations.yaml:490`<br>`configuration.yaml:690`<br>`configuration.yaml:703`<br>`configuration.yaml:763` |
| `input_select.laundry_water_valve_state` | `automations.yaml:504`<br>`automations.yaml:513`<br>`automations.yaml:522`<br>`automations.yaml:531`<br>`automations.yaml:540`<br>`configuration.yaml:726`<br>`configuration.yaml:739`<br>`configuration.yaml:782` |
| `input_select.xgimi_power_state` | `automations.yaml:567`<br>`configuration.yaml:802`<br>`configuration.yaml:818`<br>`configuration.yaml:830` |
| `light.bathroom_floor_heating` | `www/dashboards/climate.yaml:702`<br>`www/dashboards/home.yaml:1151` |
| `light.kitchen_hood_led_ext` | `homekit.yaml:221`<br>`homekit.yaml:239`<br>`scenes.yaml:39`<br>`scenes.yaml:186`<br>`scenes.yaml:235`<br>`scenes.yaml:309`<br>`www/dashboards/home.yaml:59`<br>`yaha_cloud.yaml:61`<br>`yaha_cloud.yaml:327` |
| `light.laundry_floor_heating` | `www/dashboards/climate.yaml:824`<br>`www/dashboards/home.yaml:1290` |
| `light.lava_lamp` | `automations.yaml:310`<br>`automations.yaml:316`<br>`homekit.yaml:59`<br>`homekit.yaml:83`<br>`scenes.yaml:41`<br>`scenes.yaml:119`<br>`scenes.yaml:188`<br>`scenes.yaml:237`<br>`scenes.yaml:311`<br>`www/dashboards/home.yaml:479`<br>`www/dashboards/home.yaml:497`<br>`www/dashboards/home.yaml:502`<br>`www/dashboards/home.yaml:509`<br>`www/dashboards/home.yaml:518`<br>`www/dashboards/home.yaml:524`<br>`www/dashboards/home.yaml:526`<br>`www/dashboards/home.yaml:534`<br>`www/dashboards/home.yaml:543`<br>`www/dashboards/home.yaml:548`<br>`www/dashboards/home.yaml:555`<br>`www/dashboards/home.yaml:557`<br>`yaha_cloud.yaml:24`<br>`yaha_cloud.yaml:167` |
| `light.meross_ambient_light_l` | `homekit.yaml:61`<br>`homekit.yaml:87`<br>`scenes.yaml:27`<br>`scenes.yaml:103`<br>`scenes.yaml:166`<br>`scenes.yaml:223`<br>`scenes.yaml:297`<br>`www/dashboards/home.yaml:577`<br>`yaha_cloud.yaml:26`<br>`yaha_cloud.yaml:159` |
| `light.meross_ambient_light_r` | `homekit.yaml:62`<br>`homekit.yaml:88`<br>`scenes.yaml:29`<br>`scenes.yaml:110`<br>`scenes.yaml:173`<br>`scenes.yaml:225`<br>`scenes.yaml:299`<br>`www/dashboards/home.yaml:584`<br>`yaha_cloud.yaml:27`<br>`yaha_cloud.yaml:163` |
| `light.stars_projector` | `homekit.yaml:60`<br>`homekit.yaml:85`<br>`scenes.yaml:33`<br>`scenes.yaml:117`<br>`scenes.yaml:180`<br>`scenes.yaml:229`<br>`scenes.yaml:303`<br>`www/dashboards/home.yaml:560`<br>`yaha_cloud.yaml:25`<br>`yaha_cloud.yaml:171` |
| `lock.aqara_smart_lock_u200` | `automations.yaml:27`<br>`automations.yaml:33`<br>`automations.yaml:41`<br>`automations.yaml:53`<br>`www/dashboards/home.yaml:898`<br>`www/dashboards/systems.yaml:73` |
| `media_player.yandex_station_m00db3710dqrsg` | `automations.yaml:1203`<br>`scenes.yaml:56`<br>`scenes.yaml:132`<br>`www/dashboards/home.yaml:596` |
| `media_player.yandex_station_m101k3a00pba6r` | `automations.yaml:1202`<br>`scenes.yaml:53`<br>`scenes.yaml:129`<br>`scripts.yaml:83`<br>`scripts.yaml:88`<br>`scripts.yaml:98`<br>`scripts.yaml:103`<br>`scripts.yaml:108`<br>`scripts.yaml:113`<br>`www/dashboards/home.yaml:326` |
| `remote.xgimi_horizon_ultra_switch_off` | `configuration.yaml:835` |
| `scene.after_cinema` | `www/dashboards/systems.yaml:106`<br>`yaha_cloud.yaml:11`<br>`yaha_cloud.yaml:110` |
| `scene.cinema` | `www/dashboards/systems.yaml:91`<br>`yaha_cloud.yaml:10`<br>`yaha_cloud.yaml:108` |
| `scene.home` | `www/dashboards/systems.yaml:96`<br>`yaha_cloud.yaml:9`<br>`yaha_cloud.yaml:106` |
| `scene.leave` | `www/dashboards/systems.yaml:111`<br>`yaha_cloud.yaml:8`<br>`yaha_cloud.yaml:104` |
| `scene.night` | `yaha_cloud.yaml:6`<br>`yaha_cloud.yaml:100` |
| `scene.sleep` | `www/dashboards/systems.yaml:86`<br>`www/dashboards/systems.yaml:101`<br>`yaha_cloud.yaml:5`<br>`yaha_cloud.yaml:98` |
| `scene.work` | `www/dashboards/systems.yaml:116`<br>`yaha_cloud.yaml:7`<br>`yaha_cloud.yaml:102` |
| `script.cat_spa` | `www/dashboards/systems.yaml:133`<br>`yaha_cloud.yaml:13`<br>`yaha_cloud.yaml:115` |
| `script.feed_cats` | `homekit.yaml:225`<br>`homekit.yaml:251`<br>`www/dashboards/home.yaml:95`<br>`www/dashboards/systems.yaml:127`<br>`www/dashboards/systems.yaml:698`<br>`yaha_cloud.yaml:12`<br>`yaha_cloud.yaml:112` |
| `script.kitchen_water_valve_toggle_by_state` | `www/dashboards/systems.yaml:1099` |
| `script.laundry_water_valve_toggle_by_state` | `www/dashboards/systems.yaml:1125` |
| `script.loggia_heat` | `www/dashboards/systems.yaml:138`<br>`yaha_cloud.yaml:14`<br>`yaha_cloud.yaml:118` |
| `select.fresh_element_solo_1_manual_feed` | `scripts.yaml:127` |
| `select.fresh_element_solo_2_manual_feed` | `scripts.yaml:133` |
| `sensor.3d_printer_plug_energy` | `configuration.yaml:284` |
| `sensor.3d_printer_plug_energy_monthly` | `www/dashboards/systems.yaml:890` |
| `sensor.3d_printer_plug_power` | `configuration.yaml:622`<br>`www/dashboards/systems.yaml:799` |
| `sensor.adguard_home_cpu_percent` | `configuration.yaml:429`<br>`configuration.yaml:442` |
| `sensor.adguard_home_memory_percent` | `configuration.yaml:458`<br>`configuration.yaml:471` |
| `sensor.advanced_ssh_web_terminal_cpu_percent` | `configuration.yaml:427`<br>`configuration.yaml:441` |
| `sensor.advanced_ssh_web_terminal_memory_percent` | `configuration.yaml:456`<br>`configuration.yaml:469` |
| `sensor.air_conditioner_system_relay_energy` | `configuration.yaml:230` |
| `sensor.air_conditioner_system_relay_energy_monthly` | `www/dashboards/climate.yaml:546`<br>`www/dashboards/systems.yaml:872` |
| `sensor.air_conditioner_system_relay_power` | `configuration.yaml:617`<br>`www/dashboards/climate.yaml:550`<br>`www/dashboards/systems.yaml:836` |
| `sensor.airmonitor2_co2` | `homekit.yaml:79`<br>`homekit.yaml:124`<br>`www/dashboards/home.yaml:692`<br>`yaha_cloud.yaml:233` |
| `sensor.airmonitor2_etvoc` | `configuration.yaml:475` |
| `sensor.airmonitor2_humidity` | `automations.yaml:583`<br>`homekit.yaml:77`<br>`homekit.yaml:120`<br>`www/dashboards/climate.yaml:392`<br>`www/dashboards/home.yaml:646`<br>`yaha_cloud.yaml:231` |
| `sensor.airmonitor2_noise` | `www/dashboards/home.yaml:709` |
| `sensor.airmonitor2_pm10` | `homekit.yaml:81`<br>`homekit.yaml:128` |
| `sensor.airmonitor2_pm25` | `homekit.yaml:80`<br>`homekit.yaml:126`<br>`www/dashboards/home.yaml:652`<br>`yaha_cloud.yaml:237` |
| `sensor.airmonitor2_temperature` | `homekit.yaml:76`<br>`homekit.yaml:118`<br>`www/dashboards/climate.yaml:488`<br>`www/dashboards/climate.yaml:613`<br>`www/dashboards/home.yaml:643`<br>`yaha_cloud.yaml:40`<br>`yaha_cloud.yaml:224`<br>`yaha_cloud.yaml:229` |
| `sensor.airmonitor2_tvoc_ug` | `homekit.yaml:78`<br>`homekit.yaml:122`<br>`www/dashboards/home.yaml:671`<br>`yaha_cloud.yaml:235` |
| `sensor.backup_state` | `www/dashboards/systems.yaml:401`<br>`www/dashboards/systems.yaml:412`<br>`www/dashboards/systems.yaml:425` |
| `sensor.bathroom_bath_water_leak_sensor_battery` | `homekit.yaml:40` |
| `sensor.bathroom_drain_water_leak_sensor_battery` | `homekit.yaml:44` |
| `sensor.bathroom_heat_floor_current_temperature` | `www/dashboards/climate.yaml:682` |
| `sensor.bathroom_heat_floor_energy` | `configuration.yaml:188` |
| `sensor.bathroom_heat_floor_energy_monthly` | `www/dashboards/climate.yaml:685`<br>`www/dashboards/systems.yaml:894` |
| `sensor.bathroom_heat_floor_power` | `configuration.yaml:131`<br>`configuration.yaml:628`<br>`www/dashboards/climate.yaml:689`<br>`www/dashboards/systems.yaml:816` |
| `sensor.bathroom_heat_wall_current_temperature` | `www/dashboards/climate.yaml:737` |
| `sensor.bathroom_heat_wall_energy` | `configuration.yaml:194` |
| `sensor.bathroom_heat_wall_energy_monthly` | `www/dashboards/climate.yaml:740`<br>`www/dashboards/systems.yaml:896` |
| `sensor.bathroom_heat_wall_power` | `configuration.yaml:137`<br>`configuration.yaml:629`<br>`www/dashboards/climate.yaml:744`<br>`www/dashboards/systems.yaml:820` |
| `sensor.bathroom_humidity` | `homekit.yaml:12`<br>`homekit.yaml:34`<br>`www/dashboards/home.yaml:1187`<br>`yaha_cloud.yaml:154` |
| `sensor.bathroom_installation_water_leak_sensor_battery` | `homekit.yaml:48` |
| `sensor.bathroom_pressure` | `www/dashboards/home.yaml:1190`<br>`yaha_cloud.yaml:156` |
| `sensor.bathroom_sink_water_leak_sensor_battery` | `homekit.yaml:52` |
| `sensor.bathroom_t1_battery` | `homekit.yaml:32`<br>`homekit.yaml:36` |
| `sensor.bathroom_temperature` | `homekit.yaml:11`<br>`homekit.yaml:30`<br>`www/dashboards/climate.yaml:673`<br>`www/dashboards/home.yaml:1184`<br>`yaha_cloud.yaml:22`<br>`yaha_cloud.yaml:147`<br>`yaha_cloud.yaml:152` |
| `sensor.bedroom_radiator_thermostat_battery` | `homekit.yaml:114` |
| `sensor.black_river_apparent_temperature` | `www/dashboards/climate.yaml:44`<br>`www/dashboards/climate.yaml:160` |
| `sensor.black_river_cloud_coverage` | `www/dashboards/climate.yaml:192` |
| `sensor.black_river_humidity` | `www/dashboards/climate.yaml:179` |
| `sensor.black_river_precipitation` | `www/dashboards/climate.yaml:197` |
| `sensor.black_river_pressure` | `www/dashboards/climate.yaml:184` |
| `sensor.black_river_temperature` | `www/dashboards/climate.yaml:40`<br>`www/dashboards/climate.yaml:139` |
| `sensor.black_river_wind_bearing` | `www/dashboards/climate.yaml:68`<br>`www/dashboards/climate.yaml:95` |
| `sensor.black_river_wind_bearing_2` | `www/dashboards/climate.yaml:206` |
| `sensor.black_river_wind_speed` | `www/dashboards/climate.yaml:70`<br>`www/dashboards/climate.yaml:89`<br>`www/dashboards/climate.yaml:99`<br>`www/dashboards/climate.yaml:211` |
| `sensor.database_size_sqlite` | `www/dashboards/systems.yaml:461` |
| `sensor.dishwasher_current` | `configuration.yaml:641` |
| `sensor.dishwasher_energy` | `configuration.yaml:248` |
| `sensor.dishwasher_energy_monthly` | `www/dashboards/systems.yaml:878` |
| `sensor.dishwasher_power` | `configuration.yaml:620`<br>`www/dashboards/systems.yaml:791` |
| `sensor.drying_machine_current` | `configuration.yaml:657` |
| `sensor.drying_machine_energy` | `configuration.yaml:242` |
| `sensor.drying_machine_energy_monthly` | `www/dashboards/systems.yaml:876` |
| `sensor.drying_machine_power` | `configuration.yaml:619`<br>`www/dashboards/systems.yaml:788` |
| `sensor.efekta_smart_aq_box_co2` | `www/dashboards/home.yaml:1058`<br>`yaha_cloud.yaml:477` |
| `sensor.efekta_smart_aq_box_humidity` | `homekit.yaml:401`<br>`homekit.yaml:418`<br>`www/dashboards/home.yaml:1007`<br>`yaha_cloud.yaml:475` |
| `sensor.efekta_smart_aq_box_pm10` | `homekit.yaml:404`<br>`homekit.yaml:424` |
| `sensor.efekta_smart_aq_box_pm25` | `homekit.yaml:403`<br>`homekit.yaml:422`<br>`www/dashboards/home.yaml:1018`<br>`yaha_cloud.yaml:481` |
| `sensor.efekta_smart_aq_box_pressure` | `www/dashboards/home.yaml:1011`<br>`yaha_cloud.yaml:483` |
| `sensor.efekta_smart_aq_box_temperature` | `homekit.yaml:400`<br>`homekit.yaml:416`<br>`www/dashboards/climate.yaml:884`<br>`www/dashboards/home.yaml:1003`<br>`yaha_cloud.yaml:93`<br>`yaha_cloud.yaml:468`<br>`yaha_cloud.yaml:473` |
| `sensor.efekta_smart_aq_box_tvoc_ug` | `homekit.yaml:402`<br>`homekit.yaml:420`<br>`www/dashboards/home.yaml:1037`<br>`yaha_cloud.yaml:479` |
| `sensor.efekta_smart_aq_box_voc_index` | `configuration.yaml:482` |
| `sensor.eversweet_3_pro_uvc_filter` | `www/dashboards/systems.yaml:649` |
| `sensor.fireplace_plug_energy` | `configuration.yaml:290` |
| `sensor.fireplace_plug_energy_monthly` | `www/dashboards/climate.yaml:932`<br>`www/dashboards/systems.yaml:892` |
| `sensor.fireplace_plug_power` | `configuration.yaml:621`<br>`www/dashboards/climate.yaml:936`<br>`www/dashboards/systems.yaml:795` |
| `sensor.fresh_element_solo_1_desiccant_days_remaining` | `www/dashboards/systems.yaml:662` |
| `sensor.fresh_element_solo_1_dispensed` | `configuration.yaml:1082`<br>`configuration.yaml:1088`<br>`configuration.yaml:1095`<br>`configuration.yaml:1100` |
| `sensor.fresh_element_solo_1_dispensed_stable` | `www/dashboards/systems.yaml:488` |
| `sensor.fresh_element_solo_1_error` | `www/dashboards/systems.yaml:524`<br>`www/dashboards/systems.yaml:534` |
| `sensor.fresh_element_solo_1_status` | `automations.yaml:420`<br>`automations.yaml:428`<br>`www/dashboards/systems.yaml:528`<br>`www/dashboards/systems.yaml:537` |
| `sensor.fresh_element_solo_2_desiccant_days_remaining` | `www/dashboards/systems.yaml:678` |
| `sensor.fresh_element_solo_2_dispensed` | `configuration.yaml:1107`<br>`configuration.yaml:1113`<br>`configuration.yaml:1120`<br>`configuration.yaml:1125` |
| `sensor.fresh_element_solo_2_dispensed_stable` | `www/dashboards/systems.yaml:549` |
| `sensor.fresh_element_solo_2_error` | `www/dashboards/systems.yaml:585`<br>`www/dashboards/systems.yaml:595` |
| `sensor.fresh_element_solo_2_status` | `automations.yaml:421`<br>`www/dashboards/systems.yaml:589`<br>`www/dashboards/systems.yaml:598` |
| `sensor.fridge_socket_current` | `configuration.yaml:665` |
| `sensor.fridge_socket_energy` | `configuration.yaml:260` |
| `sensor.fridge_socket_energy_monthly` | `www/dashboards/systems.yaml:882` |
| `sensor.fridge_socket_power` | `configuration.yaml:627`<br>`www/dashboards/systems.yaml:812` |
| `sensor.hall_collector_water_leak_sensor_battery` | `homekit.yaml:165` |
| `sensor.hall_humidity` | `homekit.yaml:141`<br>`homekit.yaml:159`<br>`www/dashboards/home.yaml:921`<br>`yaha_cloud.yaml:267` |
| `sensor.hall_pressure` | `www/dashboards/home.yaml:924`<br>`yaha_cloud.yaml:269` |
| `sensor.hall_t1_battery` | `homekit.yaml:158`<br>`homekit.yaml:161` |
| `sensor.hall_temperature` | `homekit.yaml:140`<br>`homekit.yaml:156`<br>`www/dashboards/climate.yaml:869`<br>`www/dashboards/home.yaml:918`<br>`yaha_cloud.yaml:47`<br>`yaha_cloud.yaml:260`<br>`yaha_cloud.yaml:265` |
| `sensor.hall_under_wardrobe_socket_energy` | `configuration.yaml:254` |
| `sensor.hall_under_wardrobe_socket_energy_monthly` | `www/dashboards/systems.yaml:880` |
| `sensor.hall_under_wardrobe_socket_power` | `configuration.yaml:623`<br>`www/dashboards/systems.yaml:804` |
| `sensor.home_assistant_core_cpu_percent` | `configuration.yaml:421`<br>`configuration.yaml:433` |
| `sensor.home_assistant_core_memory_percent` | `configuration.yaml:449`<br>`configuration.yaml:462` |
| `sensor.home_assistant_google_drive_backup_cpu_percent` | `configuration.yaml:426`<br>`configuration.yaml:439` |
| `sensor.home_assistant_google_drive_backup_memory_percent` | `configuration.yaml:455`<br>`configuration.yaml:468` |
| `sensor.home_assistant_host_disk_used` | `www/dashboards/systems.yaml:446` |
| `sensor.home_assistant_operating_system_version` | `www/dashboards/systems.yaml:347` |
| `sensor.home_assistant_supervisor_cpu_percent` | `configuration.yaml:420`<br>`configuration.yaml:434` |
| `sensor.home_assistant_supervisor_memory_percent` | `configuration.yaml:450`<br>`configuration.yaml:463` |
| `sensor.humidifier_system_relay_energy` | `configuration.yaml:224` |
| `sensor.humidifier_system_relay_energy_monthly` | `www/dashboards/climate.yaml:424`<br>`www/dashboards/systems.yaml:870` |
| `sensor.humidifier_system_relay_power` | `configuration.yaml:633`<br>`www/dashboards/climate.yaml:428`<br>`www/dashboards/systems.yaml:840` |
| `sensor.kids_room_humidity` | `automations.yaml:584`<br>`homekit.yaml:184`<br>`homekit.yaml:207`<br>`www/dashboards/climate.yaml:406`<br>`www/dashboards/home.yaml:797`<br>`yaha_cloud.yaml:306` |
| `sensor.kids_room_pressure` | `www/dashboards/home.yaml:800`<br>`yaha_cloud.yaml:308` |
| `sensor.kids_room_radiator_thermostat_battery` | `homekit.yaml:199` |
| `sensor.kids_room_t1_battery` | `homekit.yaml:205`<br>`homekit.yaml:209` |
| `sensor.kids_room_temperature` | `homekit.yaml:183`<br>`homekit.yaml:203`<br>`www/dashboards/climate.yaml:515`<br>`www/dashboards/climate.yaml:643`<br>`www/dashboards/home.yaml:794`<br>`yaha_cloud.yaml:55`<br>`yaha_cloud.yaml:299`<br>`yaha_cloud.yaml:304` |
| `sensor.kitchen_dishwasher_water_leak_sensor_battery` | `homekit.yaml:249` |
| `sensor.kitchen_humidity` | `automations.yaml:582`<br>`homekit.yaml:269`<br>`homekit.yaml:300`<br>`www/dashboards/climate.yaml:378`<br>`www/dashboards/home.yaml:383`<br>`yaha_cloud.yaml:385` |
| `sensor.kitchen_pressure` | `www/dashboards/home.yaml:386`<br>`yaha_cloud.yaml:387` |
| `sensor.kitchen_sink_water_leak_sensor_battery` | `homekit.yaml:245` |
| `sensor.kitchen_socket_energy` | `configuration.yaml:266` |
| `sensor.kitchen_socket_energy_monthly` | `www/dashboards/systems.yaml:884` |
| `sensor.kitchen_socket_power` | `configuration.yaml:624`<br>`www/dashboards/systems.yaml:806` |
| `sensor.kitchen_t1_battery` | `homekit.yaml:298`<br>`homekit.yaml:302` |
| `sensor.kitchen_temperature` | `homekit.yaml:268`<br>`homekit.yaml:296`<br>`www/dashboards/climate.yaml:459`<br>`www/dashboards/climate.yaml:583`<br>`www/dashboards/home.yaml:380`<br>`yaha_cloud.yaml:74`<br>`yaha_cloud.yaml:378`<br>`yaha_cloud.yaml:383` |
| `sensor.laundry_collector_water_leak_sensor_battery` | `homekit.yaml:347` |
| `sensor.laundry_heat_floor_current_temperature` | `www/dashboards/climate.yaml:804` |
| `sensor.laundry_heat_floor_energy` | `configuration.yaml:206` |
| `sensor.laundry_heat_floor_energy_monthly` | `www/dashboards/climate.yaml:807`<br>`www/dashboards/systems.yaml:900` |
| `sensor.laundry_heat_floor_power` | `configuration.yaml:150`<br>`configuration.yaml:631`<br>`www/dashboards/climate.yaml:811`<br>`www/dashboards/systems.yaml:828` |
| `sensor.laundry_humidifier_water_leak_sensor_battery` | `homekit.yaml:351` |
| `sensor.laundry_humidity` | `homekit.yaml:317`<br>`homekit.yaml:337`<br>`www/dashboards/home.yaml:1334`<br>`yaha_cloud.yaml:411` |
| `sensor.laundry_installation_water_leak_sensor_battery` | `homekit.yaml:355` |
| `sensor.laundry_pressure` | `www/dashboards/home.yaml:1337`<br>`yaha_cloud.yaml:413` |
| `sensor.laundry_sink_water_leak_sensor_battery` | `homekit.yaml:359` |
| `sensor.laundry_t1_battery` | `homekit.yaml:335`<br>`homekit.yaml:339` |
| `sensor.laundry_temperature` | `homekit.yaml:316`<br>`homekit.yaml:333`<br>`www/dashboards/climate.yaml:795`<br>`www/dashboards/home.yaml:1331`<br>`yaha_cloud.yaml:79`<br>`yaha_cloud.yaml:404`<br>`yaha_cloud.yaml:409` |
| `sensor.laundry_washing_machine_water_leak_sensor_battery` | `homekit.yaml:363` |
| `sensor.living_room_behind_sofa_socket_energy` | `configuration.yaml:272` |
| `sensor.living_room_behind_sofa_socket_energy_monthly` | `www/dashboards/systems.yaml:886` |
| `sensor.living_room_behind_sofa_socket_power` | `configuration.yaml:625`<br>`www/dashboards/systems.yaml:808` |
| `sensor.living_room_luminance_sensor_battery` | `homekit.yaml:306` |
| `sensor.living_room_luminance_sensor_illuminance` | `homekit.yaml:270`<br>`homekit.yaml:304`<br>`www/dashboards/home.yaml:390`<br>`yaha_cloud.yaml:389` |
| `sensor.living_room_radiator_thermostat_battery` | `homekit.yaml:292` |
| `sensor.loggia_heat_floor_current_temperature` | `www/dashboards/climate.yaml:908` |
| `sensor.loggia_heat_floor_energy` | `configuration.yaml:212` |
| `sensor.loggia_heat_floor_energy_monthly` | `www/dashboards/climate.yaml:911`<br>`www/dashboards/systems.yaml:902` |
| `sensor.loggia_heat_floor_power` | `configuration.yaml:156`<br>`configuration.yaml:632`<br>`www/dashboards/climate.yaml:915`<br>`www/dashboards/systems.yaml:832` |
| `sensor.loggia_humidity` | `homekit.yaml:374`<br>`homekit.yaml:387`<br>`www/dashboards/home.yaml:1407`<br>`yaha_cloud.yaml:447` |
| `sensor.loggia_pressure` | `www/dashboards/home.yaml:1410`<br>`yaha_cloud.yaml:449` |
| `sensor.loggia_t1_battery` | `homekit.yaml:385`<br>`homekit.yaml:389` |
| `sensor.loggia_temperature` | `homekit.yaml:373`<br>`homekit.yaml:383`<br>`www/dashboards/climate.yaml:899`<br>`www/dashboards/home.yaml:1404`<br>`yaha_cloud.yaml:87`<br>`yaha_cloud.yaml:440`<br>`yaha_cloud.yaml:445` |
| `sensor.matter_server_cpu_percent` | `configuration.yaml:424`<br>`configuration.yaml:437` |
| `sensor.matter_server_memory_percent` | `configuration.yaml:453`<br>`configuration.yaml:466` |
| `sensor.mosquitto_broker_cpu_percent` | `configuration.yaml:423`<br>`configuration.yaml:436` |
| `sensor.mosquitto_broker_memory_percent` | `configuration.yaml:452`<br>`configuration.yaml:465` |
| `sensor.oasis_current_fan_speed` | `configuration.yaml:681`<br>`www/dashboards/climate.yaml:349` |
| `sensor.oasis_current_temperature` | `www/dashboards/climate.yaml:328` |
| `sensor.oasis_outdoor_temperature` | `www/dashboards/climate.yaml:290` |
| `sensor.oasis_target_fan_speed` | `automations.yaml:840`<br>`automations.yaml:858`<br>`automations.yaml:862`<br>`automations.yaml:866`<br>`automations.yaml:871`<br>`automations.yaml:879`<br>`www/dashboards/climate.yaml:352` |
| `sensor.oasis_target_temperature` | `automations.yaml:782`<br>`automations.yaml:799`<br>`automations.yaml:803`<br>`automations.yaml:807`<br>`automations.yaml:812`<br>`automations.yaml:820`<br>`automations.yaml:946`<br>`automations.yaml:961`<br>`automations.yaml:965`<br>`automations.yaml:969`<br>`automations.yaml:974`<br>`configuration.yaml:1149`<br>`www/dashboards/climate.yaml:309` |
| `sensor.openthread_border_router_cpu_percent` | `configuration.yaml:425`<br>`configuration.yaml:438` |
| `sensor.openthread_border_router_memory_percent` | `configuration.yaml:454`<br>`configuration.yaml:467` |
| `sensor.other_power_consumers_energy` | `configuration.yaml:308` |
| `sensor.other_power_consumers_energy_monthly` | `www/dashboards/systems.yaml:904` |
| `sensor.other_power_consumers_power` | `configuration.yaml:162`<br>`www/dashboards/systems.yaml:781` |
| `sensor.river_3_battery_charging_state` | `www/dashboards/systems.yaml:919`<br>`www/dashboards/systems.yaml:923` |
| `sensor.river_3_battery_level` | `www/dashboards/home.yaml:956`<br>`www/dashboards/systems.yaml:941`<br>`www/dashboards/systems.yaml:1075` |
| `sensor.river_3_battery_temperature` | `www/dashboards/systems.yaml:937` |
| `sensor.river_3_discharge_remaining_time` | `www/dashboards/systems.yaml:916` |
| `sensor.river_3_total_in_power` | `www/dashboards/systems.yaml:848` |
| `sensor.river_3_total_out_power` | `www/dashboards/home.yaml:960`<br>`www/dashboards/systems.yaml:849`<br>`www/dashboards/systems.yaml:934` |
| `sensor.rpi_cpu_temperature` | `configuration.yaml:1137`<br>`www/dashboards/systems.yaml:355` |
| `sensor.smb_disk_free_elements` | `www/dashboards/systems.yaml:292` |
| `sensor.smb_disk_free_mypassport` | `www/dashboards/systems.yaml:288` |
| `sensor.smb_disk_usage_percent_elements` | `www/dashboards/systems.yaml:306` |
| `sensor.smb_disk_usage_percent_mypassport` | `www/dashboards/systems.yaml:297` |
| `sensor.smoke_sensor_battery` | `homekit.yaml:169` |
| `sensor.snmp_router_download_speed` | `www/dashboards/systems.yaml:210` |
| `sensor.snmp_router_incoming_bytes` | `configuration.yaml:86`<br>`configuration.yaml:176` |
| `sensor.snmp_router_incoming_bytes_derivative` | `configuration.yaml:499` |
| `sensor.snmp_router_incoming_bytes_monthly` | `www/dashboards/systems.yaml:239` |
| `sensor.snmp_router_outgoing_bytes` | `configuration.yaml:92`<br>`configuration.yaml:182` |
| `sensor.snmp_router_outgoing_bytes_derivative` | `configuration.yaml:505` |
| `sensor.snmp_router_outgoing_bytes_monthly` | `www/dashboards/systems.yaml:243` |
| `sensor.snmp_router_upload_speed` | `www/dashboards/systems.yaml:214` |
| `sensor.store_room_socket_energy` | `configuration.yaml:278` |
| `sensor.store_room_socket_energy_monthly` | `www/dashboards/systems.yaml:888` |
| `sensor.store_room_socket_power` | `configuration.yaml:626`<br>`www/dashboards/systems.yaml:810` |
| `sensor.studio_code_server_cpu_percent` | `configuration.yaml:428`<br>`configuration.yaml:440` |
| `sensor.studio_code_server_memory_percent` | `configuration.yaml:457`<br>`configuration.yaml:470` |
| `sensor.total_cpu_usage` | `www/dashboards/systems.yaml:454` |
| `sensor.total_ram_usage` | `www/dashboards/systems.yaml:439` |
| `sensor.towel_dryer_current_temperature` | `configuration.yaml:167`<br>`www/dashboards/climate.yaml:761` |
| `sensor.towel_dryer_current_temperature_derivative` | `configuration.yaml:168`<br>`configuration.yaml:521` |
| `sensor.towel_dryer_energy` | `configuration.yaml:200` |
| `sensor.towel_dryer_energy_monthly` | `www/dashboards/climate.yaml:764`<br>`www/dashboards/systems.yaml:898` |
| `sensor.towel_dryer_power` | `configuration.yaml:143`<br>`configuration.yaml:630`<br>`www/dashboards/climate.yaml:768`<br>`www/dashboards/systems.yaml:824` |
| `sensor.ventilation_system_relay_avg_power` | `configuration.yaml:616`<br>`www/dashboards/climate.yaml:275`<br>`www/dashboards/systems.yaml:777` |
| `sensor.ventilation_system_relay_current` | `automations.yaml:399`<br>`configuration.yaml:576` |
| `sensor.ventilation_system_relay_current_sampled` | `configuration.yaml:107` |
| `sensor.ventilation_system_relay_energy` | `configuration.yaml:218` |
| `sensor.ventilation_system_relay_energy_monthly` | `www/dashboards/climate.yaml:271`<br>`www/dashboards/systems.yaml:868` |
| `sensor.ventilation_system_relay_power` | `automations.yaml:398`<br>`configuration.yaml:567` |
| `sensor.ventilation_system_relay_power_sampled` | `configuration.yaml:99` |
| `sensor.washing_machine_current` | `configuration.yaml:649` |
| `sensor.washing_machine_energy` | `configuration.yaml:236` |
| `sensor.washing_machine_energy_monthly` | `www/dashboards/systems.yaml:874` |
| `sensor.washing_machine_power` | `configuration.yaml:618`<br>`www/dashboards/systems.yaml:785` |
| `sensor.zemismart_smp01_ac_frequency` | `www/dashboards/systems.yaml:1059` |
| `sensor.zemismart_smp01_avg_current` | `www/dashboards/systems.yaml:734` |
| `sensor.zemismart_smp01_avg_power` | `configuration.yaml:613`<br>`www/dashboards/systems.yaml:745`<br>`www/dashboards/systems.yaml:772` |
| `sensor.zemismart_smp01_current` | `automations.yaml:401`<br>`configuration.yaml:594` |
| `sensor.zemismart_smp01_current_sampled` | `configuration.yaml:123` |
| `sensor.zemismart_smp01_energy` | `configuration.yaml:296`<br>`configuration.yaml:302` |
| `sensor.zemismart_smp01_energy_daily` | `www/dashboards/systems.yaml:757` |
| `sensor.zemismart_smp01_energy_monthly` | `www/dashboards/systems.yaml:1068` |
| `sensor.zemismart_smp01_power` | `automations.yaml:400`<br>`configuration.yaml:585` |
| `sensor.zemismart_smp01_power_sampled` | `configuration.yaml:115` |
| `sensor.zemismart_smp01_voltage` | `www/dashboards/systems.yaml:1049` |
| `sensor.zigbee2mqtt_cpu_percent` | `configuration.yaml:422`<br>`configuration.yaml:435` |
| `sensor.zigbee2mqtt_memory_percent` | `configuration.yaml:451`<br>`configuration.yaml:464` |
| `sun.sun` | `www/dashboards/climate.yaml:49` |
| `switch.3d_printer_plug` | `homekit.yaml:399`<br>`homekit.yaml:414`<br>`www/dashboards/home.yaml:982`<br>`yaha_cloud.yaml:92`<br>`yaha_cloud.yaml:464` |
| `switch.air_conditioner_system_relay` | `automations.yaml:993`<br>`automations.yaml:1028`<br>`automations.yaml:1055`<br>`automations.yaml:1081`<br>`www/dashboards/climate.yaml:538` |
| `switch.bathroom_bright_light` | `homekit.yaml:6`<br>`homekit.yaml:20`<br>`scenes.yaml:59`<br>`scenes.yaml:315`<br>`www/dashboards/home.yaml:1105`<br>`yaha_cloud.yaml:17`<br>`yaha_cloud.yaml:127` |
| `switch.bathroom_dimmed_light` | `homekit.yaml:5`<br>`homekit.yaml:18`<br>`scenes.yaml:61`<br>`scenes.yaml:317`<br>`www/dashboards/home.yaml:1100`<br>`yaha_cloud.yaml:16`<br>`yaha_cloud.yaml:123` |
| `switch.bathroom_sconce` | `homekit.yaml:7`<br>`homekit.yaml:22`<br>`scenes.yaml:63`<br>`scenes.yaml:319`<br>`www/dashboards/home.yaml:1110`<br>`yaha_cloud.yaml:18`<br>`yaha_cloud.yaml:131` |
| `switch.bedroom_air_conditioner` | `scenes.yaml:329` |
| `switch.bedroom_bright_light` | `homekit.yaml:66`<br>`homekit.yaml:95`<br>`scenes.yaml:23`<br>`scenes.yaml:97`<br>`scenes.yaml:160`<br>`scenes.yaml:219`<br>`scenes.yaml:293`<br>`www/dashboards/home.yaml:415`<br>`yaha_cloud.yaml:31`<br>`yaha_cloud.yaml:187` |
| `switch.bedroom_desktop_bright_light` | `homekit.yaml:64`<br>`homekit.yaml:91`<br>`scenes.yaml:19`<br>`scenes.yaml:93`<br>`scenes.yaml:156`<br>`scenes.yaml:215`<br>`scenes.yaml:289`<br>`www/dashboards/home.yaml:430`<br>`yaha_cloud.yaml:29`<br>`yaha_cloud.yaml:179` |
| `switch.bedroom_desktop_dimmed_light` | `homekit.yaml:63`<br>`homekit.yaml:89`<br>`scenes.yaml:21`<br>`scenes.yaml:95`<br>`scenes.yaml:158`<br>`scenes.yaml:217`<br>`scenes.yaml:291`<br>`www/dashboards/home.yaml:425`<br>`yaha_cloud.yaml:28`<br>`yaha_cloud.yaml:175` |
| `switch.bedroom_dimmed_light` | `homekit.yaml:65`<br>`homekit.yaml:93`<br>`scenes.yaml:31`<br>`scenes.yaml:101`<br>`scenes.yaml:162`<br>`scenes.yaml:227`<br>`scenes.yaml:301`<br>`www/dashboards/home.yaml:410`<br>`yaha_cloud.yaml:30`<br>`yaha_cloud.yaml:183` |
| `switch.bedroom_mirror_backlight` | `homekit.yaml:67`<br>`homekit.yaml:97`<br>`scenes.yaml:25`<br>`scenes.yaml:99`<br>`scenes.yaml:164`<br>`scenes.yaml:221`<br>`scenes.yaml:295`<br>`scripts.yaml:65`<br>`www/dashboards/home.yaml:420`<br>`yaha_cloud.yaml:32`<br>`yaha_cloud.yaml:191` |
| `switch.bedroom_track_l` | `homekit.yaml:68`<br>`homekit.yaml:99`<br>`www/dashboards/home.yaml:444`<br>`yaha_cloud.yaml:33`<br>`yaha_cloud.yaml:195` |
| `switch.bedroom_track_r` | `homekit.yaml:69`<br>`homekit.yaml:101`<br>`www/dashboards/home.yaml:449`<br>`yaha_cloud.yaml:34`<br>`yaha_cloud.yaml:199` |
| `switch.cat_feeder_1` | `automations.yaml:429` |
| `switch.cat_feeder_2` | `automations.yaml:431` |
| `switch.detskaia_haier_white_podsvetka` | `automations.yaml:1192`<br>`www/dashboards/climate.yaml:518` |
| `switch.dishwasher` | `automations.yaml:198`<br>`www/dashboards/home.yaml:76` |
| `switch.drying_machine` | `automations.yaml:197`<br>`www/dashboards/home.yaml:1267` |
| `switch.esp_pc_power` | `homekit.yaml:70`<br>`homekit.yaml:103`<br>`www/dashboards/home.yaml:435`<br>`yaha_cloud.yaml:35`<br>`yaha_cloud.yaml:207` |
| `switch.eversweet_3_pro_uvc_power` | `www/dashboards/systems.yaml:611` |
| `switch.fingerbot` | `configuration.yaml:823` |
| `switch.fireplace_plug` | `homekit.yaml:370`<br>`homekit.yaml:376`<br>`scripts.yaml:61`<br>`scripts.yaml:69`<br>`www/dashboards/climate.yaml:943`<br>`www/dashboards/home.yaml:1386`<br>`yaha_cloud.yaml:83`<br>`yaha_cloud.yaml:424` |
| `switch.fridge_socket` | `automations.yaml:195`<br>`www/dashboards/home.yaml:83` |
| `switch.gostinaia_haier_black_podsvetka` | `automations.yaml:1120`<br>`automations.yaml:1125`<br>`automations.yaml:1131`<br>`automations.yaml:1136`<br>`www/dashboards/climate.yaml:462` |
| `switch.hall_track_part_1` | `homekit.yaml:137`<br>`homekit.yaml:149`<br>`scenes.yaml:15`<br>`scenes.yaml:89`<br>`scenes.yaml:152`<br>`scenes.yaml:211`<br>`scenes.yaml:285`<br>`www/dashboards/home.yaml:875`<br>`yaha_cloud.yaml:44`<br>`yaha_cloud.yaml:248` |
| `switch.hall_track_part_2` | `homekit.yaml:138`<br>`homekit.yaml:151`<br>`scenes.yaml:17`<br>`scenes.yaml:91`<br>`scenes.yaml:154`<br>`scenes.yaml:213`<br>`scenes.yaml:287`<br>`www/dashboards/home.yaml:880`<br>`yaha_cloud.yaml:45`<br>`yaha_cloud.yaml:252` |
| `switch.hall_under_wardrobe_socket` | `homekit.yaml:139`<br>`homekit.yaml:153`<br>`www/dashboards/home.yaml:890`<br>`yaha_cloud.yaml:46`<br>`yaha_cloud.yaml:256` |
| `switch.hall_wardrobe_light` | `homekit.yaml:136`<br>`homekit.yaml:147`<br>`scenes.yaml:13`<br>`scenes.yaml:87`<br>`scenes.yaml:150`<br>`scenes.yaml:209`<br>`scenes.yaml:283`<br>`www/dashboards/home.yaml:885`<br>`yaha_cloud.yaml:43`<br>`yaha_cloud.yaml:244` |
| `switch.hdmi_hub` | `homekit.yaml:71`<br>`homekit.yaml:105`<br>`scenes.yaml:43`<br>`scenes.yaml:121`<br>`scenes.yaml:190`<br>`scenes.yaml:239`<br>`scenes.yaml:313`<br>`www/dashboards/home.yaml:454`<br>`yaha_cloud.yaml:36`<br>`yaha_cloud.yaml:211` |
| `switch.humidifier_system_control_switch_l1` | `homekit.yaml:262`<br>`homekit.yaml:281`<br>`scenes.yaml:333`<br>`scenes.yaml:345`<br>`www/dashboards/climate.yaml:381`<br>`www/dashboards/home.yaml:362`<br>`yaha_cloud.yaml:69`<br>`yaha_cloud.yaml:357` |
| `switch.humidifier_system_control_switch_l2` | `homekit.yaml:72`<br>`homekit.yaml:107`<br>`scenes.yaml:335`<br>`scenes.yaml:347`<br>`www/dashboards/climate.yaml:395`<br>`www/dashboards/home.yaml:635`<br>`yaha_cloud.yaml:37`<br>`yaha_cloud.yaml:203` |
| `switch.humidifier_system_control_switch_l3` | `homekit.yaml:179`<br>`homekit.yaml:192`<br>`scenes.yaml:337`<br>`scenes.yaml:349`<br>`www/dashboards/climate.yaml:409`<br>`www/dashboards/home.yaml:786`<br>`yaha_cloud.yaml:52`<br>`yaha_cloud.yaml:286` |
| `switch.humidifier_system_relay` | `www/dashboards/climate.yaml:416` |
| `switch.kids_room_air_conditioner` | `scenes.yaml:331` |
| `switch.kids_room_desktop_light` | `homekit.yaml:177`<br>`homekit.yaml:188`<br>`www/dashboards/home.yaml:743`<br>`yaha_cloud.yaml:50`<br>`yaha_cloud.yaml:278` |
| `switch.kids_room_light` | `homekit.yaml:176`<br>`homekit.yaml:186`<br>`www/dashboards/home.yaml:738`<br>`yaha_cloud.yaml:49`<br>`yaha_cloud.yaml:274` |
| `switch.kids_room_track` | `homekit.yaml:178`<br>`homekit.yaml:190`<br>`www/dashboards/home.yaml:748`<br>`yaha_cloud.yaml:51`<br>`yaha_cloud.yaml:282` |
| `switch.kitchen_dinner_table` | `homekit.yaml:216`<br>`homekit.yaml:227`<br>`scenes.yaml:7`<br>`scenes.yaml:81`<br>`scenes.yaml:144`<br>`scenes.yaml:203`<br>`scenes.yaml:255`<br>`scenes.yaml:277`<br>`www/dashboards/home.yaml:71`<br>`yaha_cloud.yaml:57`<br>`yaha_cloud.yaml:311` |
| `switch.kitchen_hood_fan` | `automations.yaml:753`<br>`configuration.yaml:906`<br>`configuration.yaml:916` |
| `switch.kitchen_hood_fan_ext` | `homekit.yaml:220`<br>`homekit.yaml:237`<br>`www/dashboards/home.yaml:65`<br>`yaha_cloud.yaml:60`<br>`yaha_cloud.yaml:323` |
| `switch.kitchen_hood_led` | `automations.yaml:740`<br>`configuration.yaml:1066`<br>`configuration.yaml:1076` |
| `switch.kitchen_led_light` | `homekit.yaml:217`<br>`homekit.yaml:229`<br>`scenes.yaml:9`<br>`scenes.yaml:83`<br>`scenes.yaml:146`<br>`scenes.yaml:205`<br>`scenes.yaml:257`<br>`scenes.yaml:279`<br>`www/dashboards/home.yaml:54`<br>`yaha_cloud.yaml:58`<br>`yaha_cloud.yaml:315` |
| `switch.kitchen_socket` | `homekit.yaml:218`<br>`homekit.yaml:231`<br>`scripts.yaml:95`<br>`scripts.yaml:118`<br>`www/dashboards/home.yaml:90`<br>`yaha_cloud.yaml:59`<br>`yaha_cloud.yaml:319` |
| `switch.kitchen_water_valve_close` | `automations.yaml:450`<br>`automations.yaml:453`<br>`configuration.yaml:722`<br>`configuration.yaml:778`<br>`scripts.yaml:37` |
| `switch.kitchen_water_valve_open` | `automations.yaml:448`<br>`automations.yaml:452`<br>`configuration.yaml:718`<br>`configuration.yaml:774`<br>`scripts.yaml:46` |
| `switch.kitchen_water_valve_switch` | `homekit.yaml:219`<br>`homekit.yaml:234` |
| `switch.laundry_light` | `homekit.yaml:313`<br>`homekit.yaml:326`<br>`scenes.yaml:65`<br>`scenes.yaml:321`<br>`www/dashboards/home.yaml:1255`<br>`yaha_cloud.yaml:76`<br>`yaha_cloud.yaml:392` |
| `switch.laundry_water_valve_close` | `automations.yaml:500`<br>`automations.yaml:503`<br>`configuration.yaml:758`<br>`configuration.yaml:797`<br>`scripts.yaml:13` |
| `switch.laundry_water_valve_open` | `automations.yaml:498`<br>`automations.yaml:502`<br>`configuration.yaml:754`<br>`configuration.yaml:793`<br>`scripts.yaml:22` |
| `switch.laundry_water_valve_switch` | `homekit.yaml:314`<br>`homekit.yaml:328` |
| `switch.living_room_air_conditioner` | `scenes.yaml:49`<br>`scenes.yaml:127`<br>`scenes.yaml:327` |
| `switch.living_room_behind_sofa_socket` | `homekit.yaml:261`<br>`homekit.yaml:278`<br>`www/dashboards/home.yaml:144`<br>`yaha_cloud.yaml:68`<br>`yaha_cloud.yaml:353` |
| `switch.living_room_bright_light` | `homekit.yaml:258`<br>`homekit.yaml:272`<br>`scenes.yaml:5`<br>`scenes.yaml:75`<br>`scenes.yaml:142`<br>`scenes.yaml:201`<br>`scenes.yaml:275`<br>`www/dashboards/home.yaml:134`<br>`yaha_cloud.yaml:65`<br>`yaha_cloud.yaml:341` |
| `switch.living_room_dimmed_light` | `homekit.yaml:259`<br>`homekit.yaml:274`<br>`scenes.yaml:35`<br>`scenes.yaml:77`<br>`scenes.yaml:182`<br>`scenes.yaml:231`<br>`scenes.yaml:259`<br>`scenes.yaml:305`<br>`www/dashboards/home.yaml:129`<br>`yaha_cloud.yaml:66`<br>`yaha_cloud.yaml:345` |
| `switch.living_room_track` | `homekit.yaml:260`<br>`homekit.yaml:276`<br>`scenes.yaml:37`<br>`scenes.yaml:79`<br>`scenes.yaml:184`<br>`scenes.yaml:233`<br>`scenes.yaml:307`<br>`www/dashboards/home.yaml:139`<br>`yaha_cloud.yaml:67`<br>`yaha_cloud.yaml:349` |
| `switch.oasis_power` | `automations.yaml:892`<br>`automations.yaml:917`<br>`homekit.yaml:371`<br>`homekit.yaml:379`<br>`scenes.yaml:339`<br>`scenes.yaml:351`<br>`www/dashboards/climate.yaml:229`<br>`www/dashboards/home.yaml:1353`<br>`yaha_cloud.yaml:84`<br>`yaha_cloud.yaml:428` |
| `switch.oasis_power_dummy` | `configuration.yaml:1148` |
| `switch.spalnia_haier_white_podsvetka` | `automations.yaml:1164`<br>`scenes.yaml:51`<br>`www/dashboards/climate.yaml:491` |
| `switch.store_room_light` | `homekit.yaml:396`<br>`homekit.yaml:407`<br>`scenes.yaml:67`<br>`scenes.yaml:135`<br>`scenes.yaml:323`<br>`www/dashboards/home.yaml:966`<br>`yaha_cloud.yaml:89`<br>`yaha_cloud.yaml:452` |
| `switch.store_room_socket` | `automations.yaml:547`<br>`automations.yaml:554`<br>`automations.yaml:558`<br>`homekit.yaml:398`<br>`homekit.yaml:411`<br>`www/dashboards/home.yaml:977`<br>`yaha_cloud.yaml:91`<br>`yaha_cloud.yaml:460` |
| `switch.store_room_table_light` | `homekit.yaml:397`<br>`homekit.yaml:409`<br>`scenes.yaml:69`<br>`scenes.yaml:137`<br>`scenes.yaml:325`<br>`www/dashboards/home.yaml:971`<br>`yaha_cloud.yaml:90`<br>`yaha_cloud.yaml:456` |
| `switch.ventilation_system_relay` | `www/dashboards/climate.yaml:263` |
| `switch.washing_machine` | `automations.yaml:196`<br>`www/dashboards/home.yaml:1260` |
| `switch.xgimi_horizon_ultra` | `homekit.yaml:263`<br>`homekit.yaml:284`<br>`scenes.yaml:249`<br>`scenes.yaml:269`<br>`www/dashboards/home.yaml:149`<br>`yaha_cloud.yaml:70`<br>`yaha_cloud.yaml:361` |
| `text.ir_remote_control_ir_code_to_send` | `configuration.yaml:978`<br>`configuration.yaml:987`<br>`configuration.yaml:996` |
| `timer.oasis_state_applying` | `automations.yaml:900`<br>`automations.yaml:912`<br>`automations.yaml:920`<br>`configuration.yaml:685`<br>`configuration.yaml:948`<br>`configuration.yaml:967` |
| `vacuum.roborock_robotic_vacuum_cleaner` | `www/dashboards/home.yaml:990` |
| `weather.black_river` | `www/dashboards/climate.yaml:15`<br>`www/dashboards/climate.yaml:25`<br>`www/dashboards/climate.yaml:135` |

2026-11-10: из актуального каталога исключены climate.rpi_cooling_system и switch.rpi_cooling_fan — конфигурация удалена, остаточные записи удалены после подтверждения владельца. Остальные записи отражают дату исходного обследования.
