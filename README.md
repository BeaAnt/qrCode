# qrCode    

VM Docker:    
git clone https://github.com/BeaAnt/qrCode.git    
cd qrCode   
nano Dockerfile
    FROM openjdk:8-jdk-alpine   
    ARG JAR_FILE=target/*.jar   
    COPY ${JAR_FILE} app.jar    
    ENTRYPOINT ["java","-jar","/app.jar"]   
    
docker build -t <nome image>   
docker run -p 9000:8080 <nome image>   

per chiamare il servizio url:
http://140.238.173.110:9000/qr/<string>
