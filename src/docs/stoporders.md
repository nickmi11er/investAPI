

 <!-- range HasServices -->






# StopOrdersService
Сервис предназначен для работы со стоп-заявками:</br> **1**.
выставление;</br> **2**. отмена;</br> **3**. получение списка стоп-заявок.

##Методы сервиса


### PostStopOrder
Метод выставления стоп-заявки

- Тело запроса — [PostStopOrderRequest](#poststoporderrequest)

- Тело ответа — [PostStopOrderResponse](#poststoporderresponse)


### GetStopOrders
Метод получения списка активных стоп заявок по счёту

- Тело запроса — [GetStopOrdersRequest](#getstopordersrequest)

- Тело ответа — [GetStopOrdersResponse](#getstopordersresponse)


### CancelStopOrder
Метод отмены стоп-заявки

- Тело запроса — [CancelStopOrderRequest](#cancelstoporderrequest)

- Тело ответа — [CancelStopOrderResponse](#cancelstoporderresponse)

 <!-- range .Methods -->
 <!-- range .Services -->

##Сообщения методов



### PostStopOrderRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| figi |  [string](#string) | Figi-идентификатор инструмента |
| quantity |  [float](#float) | Количество лотов |
| price |  [MoneyValue](#moneyvalue) | Цена лота |
| stop_price |  [MoneyValue](#moneyvalue) | Стоп-цена заявки |
| direction |  [StopOrderDirection](#stoporderdirection) | Направление операции |
| account_id |  [string](#string) | Номер счёта |
| expiration_type |  [StopOrderExpirationType](#stoporderexpirationtype) | Тип экспирации заявки |
| stop_order_type |  [StopOrderType](#stopordertype) | Тип заявки |
| expire_date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата и время окончания действия стоп-заявки в часовом поясе UTC. **Для ExpirationType = GoodTillDate заполнение обязательно**. |
 <!-- end Fields -->
 <!-- end HasFields -->


### PostStopOrderResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| stop_order_id |  [string](#string) | Уникальный идентификатор стоп-заявки. |
 <!-- end Fields -->
 <!-- end HasFields -->


### GetStopOrdersRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| account_id |  [string](#string) | Идентификатор счёта клиента |
 <!-- end Fields -->
 <!-- end HasFields -->


### GetStopOrdersResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| stop_orders | Массив объектов [StopOrder](#stoporder) | Массив стоп-заявок по счёту |
 <!-- end Fields -->
 <!-- end HasFields -->


### CancelStopOrderRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| account_id |  [string](#string) | Идентификатор счёта клиента |
| stop_order_id |  [string](#string) | Уникальный идентификатор стоп-заявки. |
 <!-- end Fields -->
 <!-- end HasFields -->


### CancelStopOrderResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| time |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Время отмены заявки в часовом поясе UTC |
 <!-- end Fields -->
 <!-- end HasFields -->


### StopOrder



| Field | Type | Description |
| ----- | ---- | ----------- |
| stop_order_id |  [string](#string) | Идентификатор-идентификатор стоп-заявки |
| lots_requested |  [float](#float) | Запрошено лотов |
| figi |  [string](#string) | Figi-идентификатор инструмента |
| direction |  [StopOrderDirection](#stoporderdirection) | Направление операции |
| currency |  [string](#string) | Валюта стоп-заявки |
| order_type |  [StopOrderType](#stopordertype) | Тип стоп-заявки |
| create_date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата и время выставления заявки в часовом поясе UTC |
| activation_date_time |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата и время конвертации стоп-заявки в биржевую в часовом поясе UTC |
| expiration_time |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата и время снятия заявки в часовом поясе UTC |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

## Enums


### StopOrderDirection
Направление операции

| Name | Number | Description |
| ---- | ------ | ----------- |
| STOP_ORDER_DIRECTION_UNSPECIFIED | 0 | Значение не указано |
| STOP_ORDER_DIRECTION_BUY | 1 | Покупка |
| STOP_ORDER_DIRECTION_SELL | 2 | Продажа |




### StopOrderExpirationType


| Name | Number | Description |
| ---- | ------ | ----------- |
| STOP_ORDER_EXPIRATION_TYPE_UNSPECIFIED | 0 | Значение не указано. |
| STOP_ORDER_EXPIRATION_TYPE_GOOD_TILL_CANCEL | 1 | Действительно до отмены. |
| STOP_ORDER_EXPIRATION_TYPE_GOOD_TILL_DATE | 2 | Действительно до даты снятия. |




### StopOrderType


| Name | Number | Description |
| ---- | ------ | ----------- |
| STOP_ORDER_TYPE_UNSPECIFIED | 0 | Значение не указано |
| STOP_ORDER_TYPE_TAKE_PROFIT | 1 | Take-profit заявка |
| STOP_ORDER_TYPE_STOP_LOSS | 2 | Stop-loss заявка |
| STOP_ORDER_TYPE_STOP_LIMIT | 3 | Stop-limit заявка |


 <!-- range .Enums -->
 <!-- range HasServices -->
 <!-- range .Files -->

## Нестандартные типы данных

### MoneyValue
Денежная сумма в определенной валюте

| Field | Type | Description |
| ----- | ---- | ----------- |
| currency |  [string](#string) | Строковый ISO-код валюты |
| units |  [int64](#int64) | Целая часть суммы, может быть отрицательным числом |
| nano |  [int32](#int32) | Дробная часть суммы, может быть отрицательным числом |


### Quotation
Котировка - денежная сумма без указания валюты

| Field | Type | Description |
| ----- | ---- | ----------- |
| units |  [int64](#int64) | Целая часть суммы, может быть отрицательным числом |
| nano |  [int32](#int32) | Дробная часть суммы, может быть отрицательным числом |
