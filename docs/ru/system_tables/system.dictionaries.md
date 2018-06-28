# system.dictionaries

Содержит информацию о внешних словарях.

Столбцы:

- `name String` — Имя словаря.
- `type String` — Тип словаря: Flat, Hashed, Cache.
- `origin String` — Путь к конфигурационному файлу, в котором описан словарь.
- `attribute.names Array(String)` — Массив имён атрибутов, предоставляемых словарём.
- `attribute.types Array(String)` — Соответствующий массив типов атрибутов, предоставляемых словарём.
- `has_hierarchy UInt8` — Является ли словарь иерархическим.
- `bytes_allocated UInt64` — Количество оперативной памяти, которое использует словарь.
- `hit_rate Float64` — Для cache-словарей - доля использований, для которых значение было в кэше.
- `element_count UInt64` — Количество хранящихся в словаре элементов.
- `load_factor Float64` — Доля заполненности словаря (для hashed словаря - доля заполнения хэш-таблицы).
- `creation_time DateTime` — Время создания или последней успешной перезагрузки словаря.
- `last_exception String` — Текст ошибки, возникшей при создании или перезагрузке словаря, если словарь не удалось создать.
- `source String` - Текст, описывающий источник данных для словаря.


Заметим, что количество оперативной памяти, которое использует словарь, не является пропорциональным количеству элементов, хранящихся в словаре. Так, для flat и cached словарей, все ячейки памяти выделяются заранее, независимо от реальной заполненности словаря.