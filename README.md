# Reflection 1

1. How many messages does your publisher program send in one run?

The program sends five messages in one run. Each message is about a new user that has been added, including their ID and name. The messages are sent sequentially, and each one is triggered by the publish_event function call within the main function of the program.
```
    _ = p.publish_event("user_created".to_owned(),
        UserCreatedEventMessage { user_id: "1".to_owned(), user_name:"2206046840-Amir".to_owned() });
    _ = p.publish_event("user_created".to_owned(),
        UserCreatedEventMessage { user_id: "2".to_owned(), user_name:"2206046840-Budi".to_owned() });
    _ = p.publish_event("user_created".to_owned(),
        UserCreatedEventMessage { user_id: "3".to_owned(), user_name:"2206046840-Cica".to_owned() });
    _ = p.publish_event("user_created".to_owned(),
        UserCreatedEventMessage { user_id: "4".to_owned(), user_name:"2206046840-Dira".to_owned() });
    _ = p.publish_event("user_created".to_owned(),
        UserCreatedEventMessage { user_id: "5".to_owned(), user_name:"2206046840-Emir".to_owned() });
```

2. What does the URL "amqp://guest:guest@localhost:5672" mean?

Both the subscriber and publisher are connected to the same AMQP message broker using the URL "amqp://guest:guest@localhost:5672". By using this method, both the subscriber and publisher can send and receive messages to each other through the broker.

# Running RabbitMQ 

![messageImage_1713898592841](https://github.com/tvadhisti/module8-publisher/assets/127074983/e50f6307-833c-408b-8ab4-b49bdbe82d22)

# Console
![image](https://github.com/tvadhisti/module8-publisher/assets/127074983/8a478bc2-b790-4ec6-91ae-cad195f3039e)

The subscriber and publisher applications communicate using the AMQP protocol, connecting via the URI amqp://guest:guest@localhost:5672. The publisher application creates instances of user_created events and dispatches them to the message broker. The subscriber application is designed to listen for these user_created events, receiving them through the broker.

As the publisher executes, it creates multiple user_created event messages, each containing a unique user ID and name. These messages are sent sequentially to the broker, which then routes them to the appropriate queue.

On the other side, the subscriber continuously monitors this queue. When a user_created message arrives, the subscriber retrieves it and proceeds to execute its programmed behavior, which in this case is printing out the message details. This demonstrates the real-time messaging capabilities between the two applications, where one actively publishes data and the other responds by processing that data as it is received.

# Monitoring Chart
![image](https://github.com/tvadhisti/module8-publisher/assets/127074983/5771abdd-ff8d-4f19-80fe-74798ff84fbb)
The spikes on the second chart, which track message rates, correlate directly to our activity with the publisher. When we run the publisher, it sends out messages to the queue, which are then reflected as spikes in the message rates on the chart. Each spike represents a burst of activity where messages are published. If we run the publisher multiple times in succession, we will see multiple spikes corresponding to each run. This visual representation helps us understand the throughput of the system and the publisher's activity over time. By observing these spikes, we can gauge the effectiveness of the publishing process and make adjustments to optimize message flow if needed.

