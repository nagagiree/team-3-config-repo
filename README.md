# team-3-config-repo

=>#Spring Cloud Config Server:

-->In the development of an application, We create some n number of microservices and that microservices have some common properties...

-->When ever some changes are required to application.properties that you have to update all microservices involved in project...

-->Solution is spring cloud config server.,To manage common application properties of microservices in a git-repo & config server application
   will load them from git...

-->Make the microservices as config clints So.,that they can read common properties from config server...

Steps:-
1>Git account (github.com) vct...

2>Login,Create repo,Create new file application.properties and add common properties then commit...

3>Create new boot project for config server...

Note:-
*Once config server is started we can access common properties loaded from Git...Thru below url
          http://localhost:1111/ConfigServer/application-default.properties


=>#Spring Cloud Config clints:

-->To load common application properties from config server..,At that time of before application context is created...
   Mean by before context is created all common properties loaded from config server...

Steps:-
1>Add cloud dependancy,management,repository in pom.xml of maven project...

2>Add Config Clint and Actuator dependencies...

3>Remove all common application properties in application.properties..,If keep it no problem but more preority get bootstrap.properties file...

4>Create a new file bootstrap.properties for load common application properties from config server....

5>Enable Actuator endpoints...

6>Add SpringbootApplication class on top of class @RefreshScope...

Note:-
*When properties change in Git it is automatically updated in config server but not microservices(config clints)...

*To load or update the changes to microservices(config clints)..,
 Send a POST request thru Postman to the actuator endpoint...
          http://localhost:<port>/<context-path>/<actuator>/<refresh>    -->POST

*If spring cloud bus,RabbitSrver(Message Server),Eureka Server in real time intimate to microservice and that changes effected in microservices 1000 of microservices like this...














================================================nagagirigollapalli@gmail.com==========================================================















