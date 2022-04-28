# run-kibana-locally-docker on mac
Steps to Run Kibana locally with docker

## Run Elasticsearch
1. You should have docker installed and running
2. Open terminal 
3. Creat new network for docker and kibana
  ```
  RUN -> docker network create elastic
  ```
4. Start elasic in Docker
```
RUN -> docker run --name es01 --net elastic -p 9200:9200 -p 9300:9300 -it docker.elastic.co/elasticsearch/elasticsearch:8.1.3
```
5. This will create all configurations and user elastic by default 
6. From the logs in terminal copy password for the user and token, enrollment key is needed when you run kibana

## Run Kibana
1. Open another terminal 
2. Run kibana 
```
RUN-> docker run --name kib-01 --net elastic -p 5601:5601 docker.elastic.co/kibana/kibana:8.1.3
```
3. At the end you would see url which will be used for running kibana dashboard on UI, copy and paste it on the brower
4. On browser, username and enrollment key/token will be asked.
5. username will be elasic and past enrollment token
6. Play with kibana
