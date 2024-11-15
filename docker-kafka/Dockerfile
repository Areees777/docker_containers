FROM bitnami/kafka:latest

USER root

# Instalar Python 3
RUN apt-get update && apt-get install -y python3 python3-pip

# Instalar kafka-python si es necesario
RUN apt-get install -y python3-kafka
