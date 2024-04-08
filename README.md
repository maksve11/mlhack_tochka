# mlhack_tochka
ml hackaton for bank Tochka

## Описание задачи
Научиться предсказывать лучшие сочетания "продавец - потенциальный клиент" по данным о продавцах и клиентах.

## Метрика
F1 score

## Формат отправки ответа
- id,target
- 21ea07a7-4c9c-4b9a-b0ae-921e7e562312,0
- 63f622c9-e4f6-4ec1-bb92-c551296ea8e9,1
- c26e5b5e-f56d-48aa-89dc-711af7f9510e,0

Файл результатов - submission.csv

## О данных
Архив с данными содержит следующие файлы:
- train.tar.gz
- test.tar.gz
- example.ipynb
- sample_submission.csv

## Описание фичей
ids_target

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- timestamp - время взятия карточки клиента в работу продавцом
- client_id - идентификатор клиента
- seller_id - идентификатор продавца
- target - целевая перменная (купил ли клиент продукт или нет)

prelead_features_user_info

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- role - Роль продавца
- division - регион в котором работает продавец
- position - должность в компании
- grade - уровень работника
- is_teamlead - является ли тимлидом
- teamid - идентификатор команды
- hypothesisid - идентификатор гипотезы, по которой проходит работа
- employed_days - количество дней с приема на работу
- seller_gender - пол продавца

prelead_features_client_history

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- days_since_last_take - количество дней с прошлого взятия в работу
- wrong_phone_last_time - был ли неправильный номер в последний раз
- has_new_phones - есть новый номер телефона
- cnt_takes - количество взятий в работу
- cnt_not_sell - количество непродаж

prelead_features_client_gender

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- client_gender - пол клиента

prelead_features_contractors_banks

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- tochka_contractor_bank_top_1 - топ 1 банк (по количеству транзакций) у клиента

prelead_features_contractors_directional

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- tochka_contractors_n_incoming - Количество уникальных компаний от которых поступают входящие платежи
- tochka_contractors_count_sum_rub_incoming - количество входящих платежей клиента
- tochka_contractors_avg_sum_rub_incoming - средний размер входящих платежа клиента
- tochka_contractors_n_outgoing - Количество исходящих платежей
- tochka_contractors_count_sum_rub_outgoing - количество уникальных компаний к которым идут исходящие платежи
- tochka_contractors_avg_sum_rub_outgoing - средний размер исходящих платежей клиента

prelead_features_goszakupki

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- goszakupki_winner_sum - сумма тендеров, в которых клиент победил
- goszakupki_winner_count - количество тендеров, в которых клиент победил
- goszakupki_total_sum - сумма тендеров, в которых клиент участвовал
- goszakupki_total_count - количество тендеров, в которых клиент участвовал

prelead_features_revenue

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- revenue - объем выручки

prelead_features_time_features

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- time_tz_diff - разница между часовым поясом клиента и продавца

prelead_features_holding

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- cnt_holdings - количество компаний в холдинге
- days_since_ors_avg - средний срок с открытия расчетного счета
- is_youngest_in_holding - самая молодая компания в холдинге
- is_oldest_in_holding - самая старая компания в холдинге
- is_biggest_in_holding - самая большая компания в холдинге
- is_smallest_in_holding - самая маленькая компания в холдинге
- holding_revenue_avg - средняя выручка холдинга
- holding_cnt_takes - количество взятий в работу компаний из холдинга
- holding_cnt_not_sell - количество неуспехов (непродаж)
- holding_avg_days_since_take - среднее число дней с взятия компаний из холдинга

prelead_features_egrul

- id - ключ, по которому соединяются все таблицы - уникальный для тройки (продавец, клиент, ts)
- egrul_kind - ИП или ЮЛ
- egrul_business_type - тип деятальности
- egrul_region - регион регистрации
- egrul_reg_months_ago - срок с момента регистрации
