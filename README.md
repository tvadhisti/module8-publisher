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

# Monitoring Chart
![image](https://github.com/tvadhisti/module8-publisher/assets/127074983/5771abdd-ff8d-4f19-80fe-74798ff84fbb)


