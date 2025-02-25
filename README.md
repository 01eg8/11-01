Домашнее задание к занятию «Базы данных, их типы» Макин Олег

Задание 1. СУБД

Кейс

Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для каждой предметной области.

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?

1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.
1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы?
1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.
1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?
1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.
1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это реализовать?
1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.
1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД логистов?
1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.
2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.
3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.
На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?


### Задание 1

1.1 Для решения данной задачи подойдут реляционные СУБД (например, PostgreSQL, MySQL, Microsoft SQL Server). 
- Реляционные базы данных обеспечивают строгую целостность данных благодаря использованию схемы, ограничений и транзакций. Они хорошо подходят для структурированных данных, что важно для финансовых отчётов.
- Многие реляционные СУБД поддерживают сложные SQL-запросы, что позволяет выполнять глубокий анализ данных и генерировать отчёты.
1.1* Для ускорения работы нужно использовать API, такие как Apache Kafka или Apache Spark. Они могут помочь в распределении нагрузки и ускорении обработки данных.
1.2 Для решения данной задачи подойдут гибридные СУБД (PostgreSQL с расширениями для работы с JSON).
1.2* Для этой задачи нужно использовать PostgreSQL. Она поддерживает хранение JSON и JSONB, что позволяет эффективно работать как с структурированными, так и с неструктурированными данными. Это делает её хорошим выбором для проектов, где требуется гибкость в хранении данных.
1.3 Для решения данной задачи удобнее всего использовать MongoDB. Она хорошо подходит для хранения неструктурированных и полуструктурированных данных, что может быть полезно для хранения обучающих материалов, которые могут иметь различные форматы (текст, изображения, видео и т.д.).
1.3* Для решения данной задачи также можно использовать PostgreSQL. PostgreSQL поддерживает работу с различными типами данных, включая JSON и JSONB. Это позволяет хранить неструктурированные и полуструктурированные данные, что может быть полезно для обучающих материалов, которые могут содержать текст, изображения или другие форматы. PostgreSQL является реляционной СУБД, что позволяет легко организовать данные в таблицы с четко определенными таблицами и связями между ними. Это подходит для хранения структурированной информации, такой как корпоративные нормы и правила.
1.4 Для решения данной задачи подойдет PostgreSQL с расширением PostGIS. PostgreSQL вместе с расширением PostGIS предоставляет мощные возможности для обработки географических данных и работы с пространственными запросами. Вы сможете выполнять сложные запросы для определения маршрутов, расстояний и т.д. Также можно использовать MongoDB. MongoDB поддерживает геопространственные индексы и запросы, что позволяет эффективно работать с неструктурированными данными и выполнять запросы на определение ближайших точек, маршрутов и т.д.
1.4* Можно объединить СУБД Департамент логистики и отдел закупок. Плюсы такого решения 
- Объединение данных из разных отделов в одной базе данных может помочь избежать дублирования информации и обеспечить целостность данных.
- Один источник данных упрощает доступ к информации для всех заинтересованных сторон, что может повысить эффективность работы.
- Поддержка одной базы данных может быть менее затратной, чем поддержка нескольких, особенно если речь идет о лицензиях, хостинге и администрировании.
Минусы такого решения
- С увеличением объема данных и количества пользователей может возникнуть сложность в управлении правами доступа и безопасностью.
- Если объем данных и количество запросов значительно увеличится, это может повлиять на производительность системы.
1.5* Для данного задания подойдет PostgreSQL с некоторыми расширениями.

### Задание 2

2.1 Идентификация пользователя. Выбор способа пополнения. Ввод данных для транзакции. Проверка данных. Обработка транзакции. Подтверждение и завершение транзакции.
2.1* При выполнения условия по балансу уходит команда в банк. Создается команда на пополнение счета. Банк пополняет счет. Проверка и завершении транзакции.

### Задание 3

3.1
- SQL-системы используют фиксированную схему данных, что обеспечивает строгую структуру и целостность данных. Это позволяет легко управлять и поддерживать данные, а также гарантирует, что все записи соответствуют заданным правилам.
- SQL предоставляет мощный язык запросов, который позволяет выполнять сложные операции, такие как объединение таблиц, группировка и агрегация данных. Это делает SQL-системы более подходящими для аналитических задач и отчетности.
- SQL является стандартным языком для работы с реляционными базами данных, что делает его широко распространенным и понятным для разработчиков. Это упрощает обучение и позволяет легко находить специалистов с необходимыми навыками.
- SQL-системы имеют богатую экосистему инструментов для управления, мониторинга и оптимизации баз данных. Существует множество готовых решений для резервного копирования, восстановления, миграции и анализа данных, что упрощает работу с базами данных.
- SQL-системы предлагают продвинутые механизмы управления доступом и аутентификации, что позволяет контролировать, кто может видеть и изменять данные. Это особенно важно для приложений, работающих с конфиденциальной информацией.
3.2
- NewSQL-системы используют SQL как язык запросов, что облегчает переход для разработчиков, знакомых с традиционными реляционными базами данных. Это позволяет использовать существующие навыки и инструменты, что упрощает разработку и поддержку приложений.
- NewSQL-системы оптимизированы для работы с большими объемами данных и могут обеспечивать высокую производительность при выполнении сложных запросов. Это достигается за счет использования современных технологий, таких как распределенные вычисления и кэширование.

### Задание 4

Для решения такого задания надо учитывать эти критерии:
- Объем и структура данных: Если данные имеют сложные взаимосвязи и требуют строгой схемы, то лучше выбрать реляционную СУБД (например, NewSQL). Если данные менее структурированы или разнообразны, то NoSQL может быть более подходящим.
- Требования к производительности: Если приложение требует высокой производительности и низкой задержки, NewSQL-системы могут обеспечить необходимую производительность благодаря горизонтальному масштабированию и оптимизации запросов.
- Надежность и целостность данных: Если критически важна целостность данных (например, в финансовых приложениях), то стоит рассмотреть реляционные базы данных или NewSQL, которые поддерживают ACID-принципы.

Если важна высокая производительность и надежность, NewSQL с использованием Spark может быть оптимальным решением. 
Если же требуется работа с неструктурированными данными и высокая гибкость, то NoSQL с моделью MapReduce может быть более подходящим выбором.
