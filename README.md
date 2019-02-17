# php-apache-composer
### 신플 랜프 황경. * 바로 황경이 필요 할때 풀하는 래포지토리


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
      - ./src:/var/www/html
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
