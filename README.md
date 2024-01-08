# SpringbootOauth2

## Steps
### 1.
Create a Spring boot project
### 2.
Add starter web and spring-boot-starter-thymeleaf dependency for html page render
### 3.
Add index.html page  
Run the application http://localhost:8080/  
It will render the html content  
(no authorization)
### 4.
Add security dependencies  

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-oauth2-client</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-oauth2-resource-server</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-security</artifactId>
		</dependency> 

### 5.
  Run the application http://localhost:8080/
  It will render to login page
### 6. 
   Login your github account. Under application create client id and client secret.
### 7.
   Update below in application.properties file
   spring.security.oauth2.client.registration.github.client-id=Your github client id
   spring.security.oauth2.client.registration.github.client-secret=Your github client secret

### 9.
Run the application http://localhost:8080/
  It will render to login page for github login. Once login complete it will render the html content

## Flow 
1- Uer(Client) request for page (http://localhost:8080/)
2- Ask for github login
3- Connect with Authentication server by using client-id and secret
4- Connect with Authorization server by using client-id and secret
5- Authorization server return Access token to client
6- Client send that Access token to Resource Server
7- Resource server validate Access token received from client 
8- Resource server send User details to Client, if receive a valid Access token
9- Now client get the permission to render the page(index.html)

  
