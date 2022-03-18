# haproxy

CREATE USER 'repl'@'%';
GRANT REPLICATION SLAVE ON *.* TO  'repl'@'%' IDENTIFIED BY 'repl';
flush privileges;
show slave status \G;

docker-compose exec mysqlslave mysql -uroot -p100861 -e 'show slave status \G'
