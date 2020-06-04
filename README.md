# kafka-elasticsearch-twitter
Kafka Pipeline transforming twitter feeds based on keywords and users followers' count to local elastic search server in real time

## Demo

[![](http://img.youtube.com/vi/gR1_UEMNBfk/0.jpg)](http://www.youtube.com/watch?v=gR1_UEMNBfk "Kafka Demo")

### Prerequisites

Platform requirement

```
Java 8
Kafka
ElasticSearch
```

### Installing

A step by step series of examples that tell you how to get a development env running


Install Java SE 8
```bash
brew cask install java8
```

Or lastest Java Version
```
brew cask install java
```

Install Kafka
[Kafka Documentation in](https://www.confluent.io/download/?utm_medium=sem&utm_source=google&utm_campaign=ch.sem_br.nonbrand_tp.prs_tgt.kafka_mt.xct_rgn.namer_lng.eng_dv.all&utm_term=kafka%20installation&creative=&device=c&placement=&gclid=CjwKCAjwt-L2BRA_EiwAacX32cC5TyzIJKxhAs7TYddE-QCUCxrYQ49hdoveKMd_-lnLdMfYdurFhxoCJToQAvD_BwE)
Or with Docker and quick provisioning
[Kafka Stack With Docker] (https://github.com/simplesteph/kafka-stack-docker-compose)

If you chose to install Kafka with second methods:
Change the directory into the cloned github
```
cd kafka-stack-docker-compose
```
Bring up the docker container
```bash
docker-compose -f zk-single-kafka-single.yml up
```

Bring down the docker container when you all down
```bash
docker-compose -f zk-single-kafka-single.yml down
```

Install Elastic Search: Follow this installation guide [Elastic Search Installation](https://www.elastic.co/guide/en/elasticsearch/reference/current/getting-started-install.html)

### Usage

1. Open the project with your favourite Java IDE (Eclipse, Netbeans, IntelliJ, ...)
2. Obtained Twitter Developer Token [Twitter Developer Dashboard](https://developer.twitter.com/en)
3. Placed the associated tokens into the kafka-producer-twitter module.
4. Run the kafka-producer-module Main method to run the [Kafka Producer](https://docs.confluent.io/current/clients/producer.html)
5. After getting ElasticSearch up on port 9200, run either kafka-consumer-elasticsearch to consume every tweets or kafka-streams-filter-tweets module to consume on specific conditions (see the code to modify behaviour)
6. Then you can test by make GET request to endpoints localhost:9200/twitter/_search to query all the consumed data. See [Elastic Search Documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/getting-started-index.html) for further information


## Built With

* [Kafka](https://kafka.apache.org/) - Real-time data pipelines and streaming apps
* [Maven](https://maven.apache.org/) - Dependency Management
* [Elastic Search](https://www.elastic.co/) - Searching Engine Built-in Server to provide quick indexing.

## Authors

* **Nhan Le** - *Initial work* - [Nhan Le](https://github.com/NLe1)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Amazing course on Kafka [Kafka Beginner](https://www.linkedin.com/learning/learn-apache-kafka-for-beginners)
