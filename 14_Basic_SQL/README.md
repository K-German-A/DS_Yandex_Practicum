# Проект «Базовый SQL»

## Описание проекта

Нужно проанализировать данные о фондах и инвестициях и написать запросы к базе.

База данных хранит информацию о венчурных фондах и инвестициях в компании-стартапы. Эта база данных основана на датасете Startup Investments, опубликованном на популярной платформе для соревнований по исследованию данных Kaggle. 


### Таблица "acquisition"

- **id**: Идентификатор или уникальный номер покупки (первичный ключ)
- **acquiring_company_id**: Идентификатор компании-покупателя (внешний ключ, ссылается на таблицу company)
- **acquired_company_id**: Идентификатор компании, которую покупают (внешний ключ, ссылается на таблицу company)
- **term_code**: Способ оплаты сделки (cash, stock, cash_and_stock)
- **price_amount**: Сумма покупки в долларах
- **acquired_at**: Дата совершения сделки
- **created_at**: Дата и время создания записи в таблице
- **updated_at**: Дата и время обновления записи в таблице

### Таблица "company"

- **id**: Идентификатор или уникальный номер компании (первичный ключ)
- **name**: Название компании
- **category_code**: Категория деятельности компании
- **status**: Статус компании (acquired, operating, ipo, closed)
- **founded_at**: Дата основания компании
- **closed_at**: Дата закрытия компании
- **domain**: Домен сайта компании
- **network_username**: Профиль фонда в корпоративной сети биржи
- **country_code**: Код страны
- **investment_rounds**: Число раундов, в которых компания участвовала как инвестор
- **funding_rounds**: Число раундов, в которых компания привлекала инвестиции
- **funding_total**: Сумма привлечённых инвестиций в долларах
- **milestones**: Количество важных этапов в истории компании
- **created_at**: Дата и время создания записи в таблице
- **updated_at**: Дата и время обновления записи в таблице

### Таблица "education"

- **id**: Уникальный номер записи с информацией об образовании (первичный ключ)
- **person_id**: Идентификатор человека (внешний ключ, ссылается на таблицу people)
- **degree_type**: Учебная степень (BA, MS)
- **instituition**: Учебное заведение
- **graduated_at**: Дата завершения обучения
- **created_at**: Дата и время создания записи в таблице
- **updated_at**: Дата и время обновления записи в таблице

### Таблица "fund"

- **id**: Уникальный номер венчурного фонда (первичный ключ)
- **name**: Название венчурного фонда
- **founded_at**: Дата основания фонда
- **domain**: Домен сайта фонда
- **network_username**: Профиль фонда в корпоративной сети биржи
- **country_code**: Код страны фонда
- **investment_rounds**: Число инвестиционных раундов, в которых фонд принимал участие
- **invested_companies**: Число компаний, в которые инвестировал фонд
- **milestones**: Количество важных этапов в истории фонда
- **created_at**: Дата и время создания записи в таблице
- **updated_at**: Дата и время обновления записи в таблице

### Таблица "funding_round"

- **id**: Уникальный номер инвестиционного раунда (первичный ключ)
- **company_id**: Уникальный номер компании, участвовавшей в инвестиционном раунде (внешний ключ, ссылается на таблицу company)
- **funded_at**: Дата проведения раунда
- **funding_round_type**: Тип инвестиционного раунда (venture, angel, series_a)
- **raised_amount**: Сумма инвестиций в долларах
- **pre_money_valuation**: Предварительная оценка стоимости компании в долларах
- **participants**: Количество участников инвестиционного раунда
- **is_first_round**: Является ли этот раунд первым для компании
- **is_last_round**: Является ли этот раунд последним для компании
- **created_at**: Дата и время создания записи в таблице
- **updated_at**: Дата и время обновления записи в таблице

### Таблица "investment"

- **id**: Уникальный номер инвестиции (первичный ключ)
- **funding_round_id**: Уникальный номер раунда инвестиции (внешний ключ, ссылается на таблицу funding_round)
- **company_id**: Уникальный номер компании-стартапа, в которую инвестируют (внешний ключ, ссылается на таблицу company)
- **fund_id**: Уникальный номер фонда, инвестирующего в компанию-стартап (внешний ключ, ссылается на таблицу fund)
- **created_at**: Дата и время создания записи в таблице
- **updated_at**: Дата и время обновления записи в таблице

### Таблица "people"

- **id**: Уникальный номер сотрудника (первичный ключ)
- **first_name**: Имя сотрудника
- **last_name**: Фамилия сотрудника
- **company_id**: Уникальный номер компании-стартапа (внешний ключ, ссылается на таблицу company)
- **network_username**: Профиль фонда в корпоративной сети биржи
- **created_at**: Дата и время создания записи в таблице
- **updated_at**: Дата и время обновления записи в таблице
