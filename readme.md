## Tweet Streaming - Let's get tweets of current trending topics in Indonesia
On this repo, we would like to stream tweets which contain a key-words that we would like to stream and extract the data. If you like to clone this repo and try to stream the tweets in your local PC, please make sure that you have or installed the requirement.

### Requirement as follows (A - C):
##### Requirement A. Do not forget to get your Twitter API token :
1. Login or sign up to `https://developer.twitter.com`
2. On projects & apps click add app > choose staging (Follow the steps until it is done)
3. Go to app setting
4. On key and tokens : 
    - Regenerate Consumer Keys
    - Regenerate Access token and secrets

##### Requirement B. Create  `.env` files contain BEARER_TOKEN : 
1. BEARER_TOKEN=<bearer token>

##### Requirement C. Do not forget to install the required python library :
1. confluent-kafka==1.9.2
2. tweepy==4.12.1

### STEP : 
1. in your terminal run `docker-compose up -d`
2. check kafka-topics in Docker Desktop, in broker terminal run `kafka-topics --bootstrap-server localhost:9092 --list` .Kafka topics should be none
3. run `stream_topic.py` in VCode terminal
4. check again kafka-topics in Docker Desktop, in terminal run `kafka-topics --bootstrap-server localhost:9092 --list` . twitter_topics should be there
5. In VSCode terminal run `docker exec -it broker /bin/bash` and `kafka-console-consumer --bootstrap-server localhost:9092 --topic twitter_topic --from-beginning`






