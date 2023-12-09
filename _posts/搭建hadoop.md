---
layout: post
title: hadoop搭建
categories: [docker-compose搭建hadoop]
description: hadoop
keywords: hadoop,docker
---

# Hadoop搭建

**编写docker-compose.yml**

*如果是mac m2系统的小伙伴需要增加：platform: linux/x86_64 跟 image 同级*

```yaml
version: '3'

services:
  hadoop:
    image: apache/hadoop:3
    container_name: hadoop-container
    ports:
      - "50070:50070"
    expose:
      - "50070"
    networks:
      - big_data_network

  hive:
    image: apache/hive:3.1.2
    container_name: hive-container
    depends_on:
      - hadoop
    ports:
      - "10000:10000"
    expose:
      - "10000"
    environment:
      HIVE_CORE_CONF_javax_jdo_option_ConnectionURL: jdbc:derby://hive-metastore:1527/metastore_db;create=true
    networks:
      - big_data_network

  flink:
    image: bitnami/flink:1.14.0-r1
    container_name: flink-container
    ports:
      - "8081:8081"
    expose:
      - "8081"
    networks:
      - big_data_network

  kafka:
    image: bitnami/kafka:2.8.0-r0
    container_name: kafka-container
    ports:
      - "9092:9092"
    expose:
      - "9092"
    environment:
      KAFKA_ADVERTISED_LISTENERS: INSIDE://kafka:9092,OUTSIDE://localhost:9092
      KAFKA_LISTENER_SECURITY_PROTOCOL_MAP: INSIDE:PLAINTEXT,OUTSIDE:PLAINTEXT
      KAFKA_LISTENERS: INSIDE://0.0.0.0:9092,OUTSIDE://0.0.0.0:9092
      KAFKA_INTER_BROKER_LISTENER_NAME: INSIDE
      KAFKA_ZOOKEEPER_CONNECT: zookeeper:2181
    depends_on:
      - zookeeper
    networks:
      - big_data_network

  zookeeper:
    image: bitnami/zookeeper:3.7.0-r1
    container_name: zookeeper-container
    ports:
      - "2181:2181"
    expose:
      - "2181"
    networks:
      - big_data_network

networks:
  big_data_network:
    driver: bridge

```

**创建网络**

```sh
docker network create big_data_network

b3ff77b82806a38a91e340a04e2947c303a879c159ccceb7a23fe85599938945
```

