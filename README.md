### Using Apache Kafka and Confluent Schema Registry to stream data into Google BigQuery

This project includes the dataset and the script needed to load the source data into the Kafka topic.
Messages from the file are serialized into Avro format, then sent into the Kafka Topic by the producer.
The consumer will consume the messages and deserialize it into its original format.
The deserialized messages are then loaded into your Google BigQuery table.

##### enter the directory
```bash
cd kafka-avro-bigquery
```

##### Create Kafka stacks with Docker Compose
```bash
sudo docker-compose up
```

```

##### Install required Python packages
```bash
pip install -r requirements.txt
```

##### Run the producer to stream the data into the Kafka topic
```bash
python3 producer.py
```

##### Run the consumer to consume the data from Kafka topic and load them into BigQuery
```bash
python3 consumer.py
```

##### Open Confluent Control Center to monitor topic and schema registry
```
localhost:9021
```
![Screenshot (174)](https://user-images.githubusercontent.com/108534539/227703985-c18170a5-03e2-4eb8-a91e-f8434fb94cef.png)


##### Producer succesfully produce data
![Screenshot (176)](https://user-images.githubusercontent.com/108534539/227703990-058496f3-c422-43c1-9d8b-5ae741d204c1.png)

##### Consumer successfully consume data
![Screenshot (177)](https://user-images.githubusercontent.com/108534539/227704003-45971398-f4f4-4539-8e0c-8c8933bb6df0.png)

##### Result in BigQuery
![Screenshot (175)](https://user-images.githubusercontent.com/108534539/227704041-e52de7fa-450e-445b-bf41-a9f44329ab86.png)

