"**brew/apt install postgresql**" - установка пакета PostgreSQL для MacOS/Linux <br/> 
"**brew services start postgresql**" - команда запуска процессов постгрес, до выполнения  этой команды при запросе psql выдавал ошибку No such file or directory
	Is the server running locally and accepting
	connections on Unix domain socket "/tmp/.s.PGSQL.5432"?<br/>
"**createdb**" - создать базу данных из вне<br/>
"**psql -l**" - список баз данных из вне<br/>
"**psql"** -  переход в консоль постгрес<br/>
# Внутриконсольные команды:<br/>
"**\q**" - выход из консоли постгрес<br/>
"**\l**" - список баз данных<br/>
"**create database name;**" -создать базу данных<br/>
"**\с database name**" - подключение к заданной базе данных<br/>
"**drop database name;**" - удаление базы данных<br/>
"**\du**" - просмотр ролей<br/>
"**create role name;**" - создание новой роли<br/>
"**drop role name;**" -   удаление роли<br/>
"**create table name (названия столбцов и указание их типа);**"- создание таблицы
https://www.tutorialspoint.com/postgresql/postgresql_data_types.htm - подсказка с типами полей
"**\dt**" - список всех таблиц в текущей базе данных<br/>
"**\d**" table name - просмотр  структуры  заданной таблицы<br/>
"**\dt*something**" - список всех таблиц содержащих something в имени<br/>
"**select * from table name;**" - просмотр содержимого таблицы<br/>
"**alter table name add column name type_of_column;**" - добавление поля в существующую таблицу<br/>
"**alter table name drop column name;**" - удаление заданного поля<br/>
"**drop table name;**" - удаляет таблицу полностью<br/>
"**truncate table name;**" - удаляет содержимое таблицы не меняя ее структуру<br/>
### simple insert
"**insert into tablename (имя поля, имя поля2) values ('вносимое значение', 'вносимое значение2');**"<br/>
### multiple insert
"**insert into tablename (имя поля) values ('значение'), ('значение');
сработает только при условии что в остальных полях не стоит ограничение NOT NULL
### insert from select
"**insert into tablename select * from tablename;**"
### ключевые условия структуры запроса select
"**-distinct**" - отбрасывает дубликаты оставляя только уникальные записи<br/>
"**select distinct * from table name;**"<br/>
"**-where**" - дополнительный фильтр по любому из полей<br/>
"**select namecolumn/tablename from tablename where condition;**"<br/>
https://postgrespro.ru/docs/postgresql/11/ - подробная документация
https://metanit.com/sql/postgresql/4.5.php - подробное описание агрегатных функций
### изменение значений в поле
"**UPDATE tablename SET columnname = value WHERE id = # ;**"(в данном случае это указатель строки по айди)<br/> 
"**pg_dump dbname > filename**" - команда для сохранения базы данных в текстовом файле
чтобы выгрузить базу данных из файла dump нужно создать пустую базу данных и воспользоваться командой  psql dbname < filename(дамп файл)
# JOINS
форма записи: SELECT поля которые мы желаем вывести через запятую FROM имя таблицы1 INNER(или другое) JOIN имя таблицы2 on(критерии по которым идет сравнение по таблицам.типа имя таблицы1.ключ=имя таблицы2.ключ)
 
например select name, title from books inner join authors on (authors.id = books.genre_id);</br>
ссылка с примерами JOINS http://www.postgresqltutorial.com/postgresql-joins/

