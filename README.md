# Kafka Producer Consumer REST
    cd kafkaOdev
    docker-compose up 
    docker pull wurstmeister/kafka(veya sudeeyuksek/kafka)
    docker pull wurstmeister/zookeeper(veya sudeeyuksek/kafka)
    docker exec –it kafka /bin/sh
    cd opt/kafka_version/bin/
    kafka-topics.sh –create –zookeeper zookeeper:2181 –replication-factor 1 –partitions 1 –topic first_kafka_topic 
    docker-compose –f docker-compose.yml up –d

Projede Kafka Consumer ve Producer okuma yazma işlemleri için kullanılmıştır.
Spring Boot ve Kafka Streaming Platform,  Docker imajıyla entegre edilmiştir.
  Uygulamada, Kafka'yı Docker Container'da çalıştırıyoruz ve Spring REST API ile üreticiyi (producer) çağırmaya ve kafka topic’e mesaj yazmaya çalışıyoruz ve mesaj kafka topic’e ulaştığında, Kafka tüketicisi (consumer) mesajı kafka topic’ten seri hale getirerek okur ve mesajı konsola yazdırmaktadır.Spring, kafka konularından gelen mesajları kolay bir şekilde tüketmek için kafka dinleyici şablonu sağlar.

Postman üzerinden mesajınızı yollayıp, konsol üzerinde görüntüleyerek test edilmiştir.
    <P>POST: http://localhost:8081/publish?message=Merhaba nasılsın ??<P>

