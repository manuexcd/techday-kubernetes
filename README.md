# Taller TechDay Kubernetes

El objetivo es montar la siguiente arquitectura con microservicios:

[![N|Solid](https://i.ibb.co/sQR5pRz/Untitled-Diagram-4.png)](https://nodesource.com/products/nsolid)

- **msjava**: microservicio principal desarrollado en Java+Spring que se va a comunicar con los otros dos microservicios.
La comunicación con el *msjavaconsumer* será mediante el uso de una cola RabbitMQ y la comunicación con el *msjavaconsumer* con
una llamada REST usando RestTemplate. Los datos se persisten en una BD relacional, en este caso MariaDB.
- **msjavaconsumer**: microservicio desarrollado en Java+Spring. Su función es consumir los mensajes que el msjava envía a
la cola RabbitMQ. Los datos se persisten en una BD relacional, en este caso PostgreSQL.
- **mskotlin**: microservicio desarrollado en Kotlin+Spring. Los datos se persisten en una BD no relacional,
en este caso MongoDB.

Los tres microservicios tienen la misma funcionalidad, un CRUD de coches.
