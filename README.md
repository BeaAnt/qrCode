# qrCode    

VM Docker: 
1.Clone the project from git repository:        
git clone https://github.com/BeaAnt/qrCode.git    
cd qrCode 
2.Create a file named Dockerfile in the same folder as the project      
nano Dockerfile     
    FROM openjdk:8-jdk-alpine   
    ARG JAR_FILE=target/*.jar   
    COPY ${JAR_FILE} app.jar    
    ENTRYPOINT ["java","-jar","/app.jar"]   

3.Build the container image using the docker build command:     
docker build -t <nome image> .  
4.Start container using the docker run command and specify the name of the image we just created        
docker run -p 9000:8080 <nome image>   

5.open your web browser to:             
http://140.238.173.110:9000/qr/<string>
