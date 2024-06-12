- **Jak zjistit [[timezone]]**
  collapsed:: true
	- ```sql
	  SELECT @@global.time_zone, @@session.time_zone;
	  ```
	- Pokud vrátí "SYSTEM", přebírá se z operačního systému (PHP atd.)
- **Nastavení max_allowed_packet**
	- Zobrazení aktuálního limitu
		- ```sql
		  SHOW VARIABLES LIKE 'max_allowed_packet';
		  ```
	- Změna limitu - dočasná:
		- ```sql
		  SET GLOBAL max_allowed_packet=16777216;	
		  ```
	- Změna limitu trvalá - v souboru /etc/mysql/mariadb.conf.d/50-server.cnf doplnit do sekce mysqld:
		- ```
		  max_allowed_packet=100M
		  ```
- **Strict mode**
	- Ověření jestli je strict mode zapnutý
	  collapsed:: true
		- ```sql
		  SELECT @@GLOBAL.sql_mode
		  ```
	- Pokud je zapnutý, výstup bude následující:
	  collapsed:: true
		- ```
		  STRICT_TRANS_TABLES,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION
		  ```
	- Vypnutí strict mode v konzoli
	  collapsed:: true
		- ```sql
		  SET GLOBAL sql_mode = 'NO_ENGINE_SUBSTITUTION';
		  ```
	- Vypnutí strict mode napořád
	  collapsed:: true
		- Do souboru /etc/mysql/mariadb.conf.d/50-server.conf stačí doplnit řádek (do sekce mysqld):
		- ```
		  sql_mode=NO_ENGINE_SUBSTITUTION
		  ```
- **Chyba Row size too large**
	- V souboru /etc/mysql/mariadb.conf.d/50-server.cnf doplnit do sekce mysqld:
		- ```
		  innodb_file_per_table=1
		  innodb_file_format = Barracuda
		  innodb_strict_mode=0
		  ```
-
-