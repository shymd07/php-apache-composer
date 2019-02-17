# php-apache-composer
### 도커 컴포즈로 신플 랜프 개발 환경 구선하기  * 바로 환경이 필요 할때 풀하는 래포지토리

도커 하고 도커 컴포즈가 이미 설치되있는 전체

***

- Apache: 2.4.25 (Debian)
- PHP: 7.2.15 
- Composer: 1.8.4
- mysql: 5.7.25 
(user:root password :root )

- - -

##### 도커 시작
```
docker-compose build
docker-compose up -d
```

##### 도카 컴포즈 파일 내용
```
version: '3'
services:
  app:
    build: ./docker/php
    volumes:
      - ./src:/var/www/html   <--- 더커하고 연결되있는 폴더 입니다. ./src에 index.php가 있음 
    ports:
      - 8888:80  <-- 환경에 맞춰서 수정 
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

최소한 구선으로 만들어 있는 랜프환경. 파로 조사 하고 싶을 때나 다른 프로젝트에서
문제가 생겼을 때 이걸 쓰고 테스트용으로 사용하면 됩니다.

2019-02-17 11:39
