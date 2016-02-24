FROM java:8
COPY . /opt/aplikasi
WORKDIR /opt/aplikasi
RUN mkdir /opt/aplikasi/bin
RUN javac src/com/belajar/docker/Halo.java -d bin
CMD ["java", "-classpath", "/opt/aplikasi/bin", "com.belajar.docker.Halo"]
