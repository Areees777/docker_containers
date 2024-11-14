# Usar una imagen base que tenga Ubuntu (puedes usar la misma que estás usando en docker-compose)
FROM zoltannz/hadoop-ubuntu:2.8.1

# Actualizar los repositorios e instalar dependencias necesarias
RUN apt-get update && apt-get install -y \
    wget \
    tar \
    openjdk-8-jdk \
    && rm -rf /var/lib/apt/lists/*

COPY hadoop-2.8.1.tar.gz /opt/hadoop-2.8.1.tar.gz

# Descargar e instalar Hadoop
RUN tar -xzvf /opt/hadoop-2.8.1.tar.gz -C /opt
RUN mv /opt/hadoop-2.8.1 /usr/local/hadoop

# Configurar variables de entorno para Hadoop
RUN export HADOOP_HOME=/usr/local/hadoop
RUN export HADOOP_HOME=/usr/local/hadoop
RUN export HADOOP_INSTALL=$HADOOP_HOME
RUN export HADOOP_MAPRED_HOME=$HADOOP_HOME
RUN export HADOOP_COMMON_HOME=$HADOOP_HOME
RUN export HADOOP_HDFS_HOME=$HADOOP_HOME
RUN export YARN_HOME=$HADOOP_HOME
RUN export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native
RUN export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin
RUN source ~/.bashrc


# Comando por defecto para el contenedor
CMD ["/bin/bash", "-c", "/etc/bootstrap.sh -bash && tail -f /dev/null"]