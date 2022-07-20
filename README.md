helm install local-confluent-kafka helm/cp-helm-charts --version 0.6.0

helm uninstall local-confluent-kafka

kubectl get pods

kubectl apply -f kafka-client.yml

kubectl delete -f kafka-client.yml

kubectl exec -it kafka-client -- /bin/bash

kafka-topics --zookeeper local-confluent-kafka-cp-zookeeper-headless:2181 --topic customer --create --partitions 3
--replication-factor 3 --if-not-exists

kafka-topics --zookeeper local-confluent-kafka-cp-zookeeper-headless:2181 --list
