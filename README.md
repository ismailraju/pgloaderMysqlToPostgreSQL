# pgloaderMysqlToPostgreSQL



## Mysql( 10.4.11-MariaDB,windows 10 )

create user 'pgloader'@'%' identified by '1234';
grant all privileges on *.* to 'pgloader'@'%' with grant option;
flush privileges;


## PostgreSQL( PostgreSQL 10.4 on x86_64-pc-mingw64, compiled by gcc.exe (Rev5, Built by MSYS2 project) 4.9.2, 64-bit,windows 10)


CREATE DATABASE source_db;
GRANT CONNECT ON DATABASE source_db TO postgres;
GRANT ALL PRIVILEGES ON DATABASE source_db TO postgres;




## Docker (windows desktop Docker version 19.03.8,windows 10 )



$ docker pull dimitri/pgloader
$ docker run --rm --name pgloader dimitri/pgloader:latest pgloader --version
$ docker run --rm --name pgloader dimitri/pgloader:latest pgloader --help


## Migration Using pgloader

docker run --rm --name pgloader dimitri/pgloader:latest pgloader --debug mysql://pgloader:1234@host.docker.internal:3306/moe_dev2 postgresql://postgres:''@host.docker.internal:5432/source_db




