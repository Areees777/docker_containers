FROM apache/airflow:2.7.3
RUN pip install --upgrade pip
COPY requirements.txt .
RUN pip install -r requirements.txt
USER root
RUN apt-get update
RUN apt-get install wget
RUN apt-get install -y git
RUN apt-get install -y default-jdk
RUN apt-get install -y docker.io
RUN echo "JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64" >> /etc/environment && \
    echo "PATH=\$PATH:/usr/lib/jvm/java-11-openjdk-amd64/bin" >> /etc/environment

RUN source /etc/environment
RUN java -version
