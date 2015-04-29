This project is about creating a pipeline with two Logstash, one sending the stdin to RabbitMQ and one consuming the logs and sending them to stdout.


To restart my RabbitMQ on Windows, I had to make the following commands:
```
SET HOMEDRIVE=C:
rabbitmq-plugins.bat enable rabbitmq_management
rabbitmq-service.bat stop
rabbitmq-service.bat install
rabbitmq-service.bat start
```

Let's assume the RabbitMQ is running.
Go in the projects repertory.

In command prompt one and launch the consumer instance of Logstash:
``` 
cd logstash-consumer/bin
logstash agent -f config.conf 
```

In command promp two and launch the producer instance of Logstash:
```
cd ../../logstash-producer/bin directory
logstash agent -f config.conf
test <return>
```

Go in command prompt one, you should see a log appear with the "test" message.
