# qrCode    

VM Docker:       
1.Clone the project from git repository:        
git clone https://github.com/BeaAnt/qrCode.git    
cd qrCode       
2. build the project:       
mvn clean package       
3.Create a file named Dockerfile in the same folder as the project      
nano Dockerfile     
    FROM openjdk:8-jdk-alpine   
    ARG JAR_FILE=target/*.jar   
    COPY ${JAR_FILE} app.jar    
    ENTRYPOINT ["java","-jar","/app.jar"]   

4.Build the container image using the docker build command:          
docker build -t nomeimage .  
5.open a port       
sudo firewall-cmd --permanent --add-port=9001/tcp       
6.Start container using the docker run command and specify the name of the image we just created                
docker run -p 9001:8080 nomeimage         

7.open your web browser to:                  
http://140.238.214.120:9001/qr/samestring       
8.To stop the container, press ctrl-c.      

path of microservices:     
qrCode/src/main/java/com/jsoup/controller/QrController
