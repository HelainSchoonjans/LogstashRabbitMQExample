This project is about creating a pipeline with two Logstash, one sending the stdin to RabbitMQ and one consuming the logs and sending them to stdout.


To restart my RabbitMQ on Windows, I had to make the following commands:
SET HOMEDRIVE=C:
rabbitmq-plugins.bat enable rabbitmq_management
rabbitmq-service.bat stop
rabbitmq-service.bat install
rabbitmq-service.bat start
as said on stack overflow: http://stackoverflow.com/questions/18661791/failed-to-start-rabbitmq-management-plugin-on-windows/24740923#24740923


Let's assume the RabbitMQ is running.
Go in the projects repertory.
Launch both Logstashes:
In command prompt one:
Go in the logstash-consumer/bin directory and type:
logstash agent -f config.conf

In command promp two:
Go in the logstash-producer/bin directory and type:
logstash agent -f config.conf
test <return>



Go in command prompt one, you should see a log appear with the "test" message.