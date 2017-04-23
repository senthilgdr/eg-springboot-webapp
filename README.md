# Lessons Learnt

## Step 1: Add servlet Dependency jars
	<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>javax.servlet-api</artifactId>
			<version>3.1.0</version>
		</dependency>
    
## Step 2: Add Spring boot mvc jar

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>1.5.3.RELEASE</version>
	</parent>

<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<dependency>
    
    @SpringBootApplication
public class Application {

	public static void main(String[] args) {
		SpringApplication.run(Application.class, args);
	}
}

## Step 3: Add HomeController
package com.senthil;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HomeController {

	@GetMapping
	public String index() {
		System.out.println("HomeCotroller");
		return "index.jsp";
	}

}

## Test: http://localhost:8080

## Page Error:
Whitelabel Error Page

This application has no explicit mapping for /error, so you are seeing this as a fallback.

Sun Apr 23 19:19:26 IST 2017
There was an unexpected error (type=Internal Server Error, status=500).
Circular view path [index.jsp]: would dispatch back to the current handler URL [/index.jsp] again. Check your ViewResolver setup! (Hint: This may be the result of an unspecified view, due to default view name generation.)



## Solution: Add Tomcat Jasper and JSTL jar

		<dependency>
			<groupId>org.apache.tomcat.embed</groupId>
			<artifactId>tomcat-embed-jasper</artifactId>
			<scope>provided</scope>
		</dependency>
		<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>jstl</artifactId>
			<version>1.2</version>
		</dependency>


Test URL: http://localhost:8080

Output:
Hello World!
