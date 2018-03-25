# Docker image for TYPO3 CMS

Get the container from: https://hub.docker.com/r/saitho/apache-typo3/

* Compatibility verified with TYPO3 CMS 8.7 LTS and 9.1.0
* Comes with PHP 7.2.0 and an Apache server

## Sample docker-compose file

Put your TYPO3 project source into src/ directory.

```
version: '3'

services:
  typo3:
    container_name: typo3
    image: saitho/apache-typo3:latest
    ports:
      - "8080:80"
    volumes:
      - ./src:/var/www/html
    links:
      - database

  database:
    container_name: typo3-db
    image: mysql
    ports:
      - "27017:27017"
    environment:
      - MYSQL_ROOT_PASSWORD=typo3
```
