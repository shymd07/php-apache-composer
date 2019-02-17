# php-apache-composer
### 신플 랜프 황경. * 바로 황경이 필요 할때 풀하는 래포지토리

***

- Apache: 2.4.25 (Debian)
- PHP: 7.2.15 
- Composer: 1.8.4
- mysql: 5.7.25 
(user:root password :root )

- - -

##### 더커 시작
```
docker-compose build
docker-compose up -d
```

##### 더카 컴퍼즈 바일 네용
```
version: '3'
services:
  app:
    build: ./docker/php
    volumes:
      - ./src:/var/www/html   <--- 더커하고 연결되있는 폴더 입니다. ./src에 index.php가 있음 
    ports:
      - 8888:80  <-- 활경에 맞춰서 수정 
  mysql:
    image: mysql:5.7
    environment:
      - MYSQL_ROOT_PASSWORD=root
    ports:
      - 3306:3306
    volumes:
      - dbdata:/var/lib/mysql
volumes:
  dbdata:
```

최소한 구선으로 만들어 있는 랜프황경. 파로 조사하고 싶을 때 나 다른 프로젝트에서
문제가 생겼을때 이걸 쓰고 테스토용으로 사용하면 됩니다.

2019-02-17 11:39
