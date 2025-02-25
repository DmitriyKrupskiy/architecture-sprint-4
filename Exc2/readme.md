МОниторинг:
1. USE стартегию предлагаю использовать в части мониторинга использования RAM
при выделении сервисов для расчетов стоимости изделия. Насколько сервер загружен воркерами и требуется ли вертикальное масштабирование.
2. RED. Данный метод планирую использовать для мониторинга запросов К API системы со стороны Пользователей. 
3. Четыре золотых сигнала от Google уместен для монитороинга межсервисного/интеграционного взаимодейтсвия с использованием 
брокера сообщений, 
мониторинг ошибок при обработке соощений из очереди.
   Мотивация: 
1. Подключение и настройка мониторинга в системе даст информацию об узких метах в производительности системы, о насыщенности системы.
Мониторинг Серверов RAM, CPU, DISK. Достаточно ли ресурсов "железа" для обеспечения бесперебойной работы системы.
Эффективное и рациональное использования ресурво серверов. 
Мониторинг запросов К API системы со стороны Пользователей и время работы их выполнения.
Бизнес метрики, которые будут отслеживать сколько времени находился заказ в определенном статусе.
   Подключение и настройка мониторинга обеспечит команду сопровождения графическими иструментами и позволит заблаговременно
реагировать на возникшие проблемы в системе, напрмер:
при возникновении ошибок при обработке очереди сообщений инженер сможет оперативно выявить причину ошибок устранить или
указать на ее источник.
В итоге, повышение надежности работы системы обеспечивает бесперебойный бизнес процесс, и недопущение упущенной выгоды
из-за потерянных заказов по причине их долгой обработки.
Метрики:
Метрики для мониторинга наполнения очереди и ошибок при их обработке:
   Number of dead-letter-exchange letters in RabbitMQ
   Number of message in flight in RabbitMQ

Метрики для мониторинга нагрузки на API:
   Number of requests (RPS) for internet shop API Ярлык method_api_name, service_name
   Number of requests (RPS) for CRM API Ярлык method_api_name, service_name
   Number of requests (RPS) for MES API Ярлык method_api_name, service_name
   Number of requests (RPS) per user for internet shop API Ярлык user_login
   Number of requests (RPS) per user for CRM API Ярлык user_login
   Number of requests (RPS) per user for MES API Ярлык user_login
Метрики использования RAM и CPU приложениями и БД:
   CPU % for shop API Ярлык service_name
   CPU % for CRM API Ярлык service_name
   CPU % for MES API Ярлык service_name
   Memory Utilisation for shop API Ярлык service_name
   Memory Utilisation for CRM API Ярлык service_name
   Memory Utilisation for MES API Ярлык service_name
   Memory Utilisation for shop db instance Ярлык instance_id
   Memory Utilisation for MES db instance Ярлык instance_id
   Number of connections for shop db instance Ярлык instance_id
   Number of connections for MES db instance Ярлык instance_id

Метрики показывающие время выполнения запроса:

   Response time (latency) for shop API. Ярлык method_api_name, service_name
   Response time (latency) for CRM API Ярлык method_api_name, service_name
   Response time (latency) for MES API Ярлык method_api_name, service_name

Метрики для мониторинга использования дискового пространства:

   Size of S3 storage
   Size of shop db instance
   Size of MES db instance

Метрики показывающие запросы выполнившиеся с ошибкой:
   Number of HTTP 500 for shop API Ярлык method_api_name, service_name
   Number of HTTP 500 for CRM API Ярлык method_api_name, service_name
   Number of HTTP 500 for MES API Ярлык method_api_name, service_name
   Number of HTTP 500 for shop API   Ярлык method_api_name, service_name

Метрики показывающие сколько в данный момент открытых пользоавтельских сесий:
   Number of simultanious sessions for shop API Ярлык user_id, service_name
   Number of simultanious sessions for CRM API Ярлык user_id, service_name
   Number of simultanious sessions for MES API Ярлык user_id, service_name

Бизнес-метрика показывающая сколько времени заказ прибывает в статусе:
   Time status execution Ярлык заказ_ИД, статус_имя


План действий:
1. Установка , настройка хранилища для храниения метрик и стэк-трейсов. Предлагается Prometeus
2. Установка и настройка Сборщика метрик, предлагается использовать Otel протокол
3. Подключение в сервисы функционала обеспечивающего сбор метрик. Предлагается использовать библиотеки Prometeus
4. Подключение Stack Tracing для отслеживания цепоки вызовов запросов. Jaeger
5. Установка и настройка инструмента для просмотра метрик в графическом представлении. Предлагается Grafana.








