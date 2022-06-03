# Kafka Producer Consumer REST
    

 -   Projede Kafka Consumer ve Producer okuma yazma işlemleri için kullanılmıştır.
 - Spring Boot ve Kafka Streaming Platform,  Docker imajıyla entegre
   edilmiştir.
   
 -  Uygulamada, Kafka'yı Docker Container'da çalıştırıyoruz ve Spring REST API ile üreticiyi (producer) çağırmaya ve kafka topic’e mesaj yazmaya çalışıyoruz ve mesaj  -kafka topic’e ulaştığında, Kafka tüketicisi (consumer) mesajı kafka topic’ten seri hale getirerek okur ve mesajı konsola yazdırmaktadır.
 - Spring, kafka konularından gelen mesajları kolay bir şekilde tüketmek için kafka dinleyici şablonu sağlar.

 - Postman üzerinden mesajınızı yollayıp, konsol üzerinde görüntüleyerek test edilmiştir:
 <br> **POST: http://localhost:8081/publish?message=Merhaba nasılsın ??**</br>



Proje dizinine ulaşılır:   

     cd kafkaOdev

Docker compose ayaklandırılır:

    docker-compose up 
İmajlar dockerhub'tan pull edilir:

    docker pull wurstmeister/kafka(veya sudeeyuksek/kafka)
    docker pull wurstmeister/zookeeper(veya sudeeyuksek/kafka)

Zookeeper ve Kafka Topic oluşturulur:
       

    docker exec –it kafka /bin/sh
    cd opt/kafka_version/bin/
    kafka-topics.sh –create –zookeeper zookeeper:2181 –replication-factor 1 –partitions 1 –topic first_kafka_topic

 Projeye ait Dockerfile çalıştırılır.
        
        docker-compose –f docker-compose.yml up –d
