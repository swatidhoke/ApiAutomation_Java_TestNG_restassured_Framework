<h4>API Automation Framework</h4>
This project is an API automation framework built using Java, TestNG, and RestAssured. It provides a structured approach to automate the testing of RESTful APIs.

Project Structure
```
.
├── src
│   ├── main
│   │   └── java
│   │       └── com
│   │           └── restassured
│   │               └── api
│   │                   ├── requests      # API request classes
│   │                   ├── responses     # API response classes
│   │                   └── utils         # Utility classes
│   ├── test
│   │   └── java
│   │       └── com
│   │           └── restassured
│   │               └── api
│   │                   └── tests        # Test classes
├── pom.xml
└── README.md
```

<h2>Dependencies</h2>

This project uses the following dependencies:

RestAssured: For making HTTP requests and validating API responses.
TestNG: For structuring and managing test cases.
SLF4J: For logging.
Maven Configuration
Ensure your pom.xml includes the following dependencies:

xml
```
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.restassured</groupId>
    <artifactId>ApiAutomation_Java_TestNG_restassured_Framework</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>jar</packaging>

    <properties>
        <java.version>11</java.version>
        <restassured.version>5.3.0</restassured.version>
        <testng.version>7.8.0</testng.version>
    </properties>

    <dependencies>
        <!-- RestAssured for API Testing -->
        <dependency>
            <groupId>io.rest-assured</groupId>
            <artifactId>rest-assured</artifactId>
            <version>${restassured.version}</version>
            <scope>test</scope>
        </dependency>

        <!-- TestNG for Test Management -->
        <dependency>
            <groupId>org.testng</groupId>
            <artifactId>testng</artifactId>
            <version>${testng.version}</version>
            <scope>test</scope>
        </dependency>

        <!-- SLF4J for Logging -->
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-api</artifactId>
            <version>2.0.0</version>
        </dependency>
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-simple</artifactId>
            <version>2.0.0</version>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <!-- Maven Compiler Plugin -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>${java.version}</source>
                    <target>${java.version}</target>
                </configuration>
            </plugin>

            <!-- Maven Surefire Plugin for Running Tests -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-surefire-plugin</artifactId>
                <version>3.0.0-M5</version>
            </plugin>
        </plugins>
    </build>
</project>
```

<h2>Project Setup</h2>
1. Clone the Repository
 
git clone https://github.com/swatidhoke/ApiAutomation_Java_TestNG_restassured_Framework.git

cd ApiAutomation_Java_TestNG_restassured_Framework

2. Install Dependencies

Make sure Maven is installed and run:

mvn clean install

<h2>Configuration</h2>
Logging Configuration
The project uses SLF4J for logging. By default, it uses slf4j-simple for simplicity. You can customize logging configuration as needed.

TestNG Configuration
TestNG configurations are managed through the testng.xml file located in the src/test/resources directory.

API Endpoints and Data
Update the API endpoint URLs and test data in the request classes as needed. Ensure that your tests have the correct endpoint URLs and authentication tokens if required.

<h2>Running Tests</h2>
To execute the tests, use the following Maven command:

mvn test
Test results will be available in the target/surefire-reports directory.

<h2>Example Test Case</h2>
Here's a simple example of a test case using RestAssured:
Example (GetRequestTest.java):

```
package com.restassured.api.tests;

import com.restassured.api.requests.GetRequest;
import com.restassured.api.responses.GetResponse;
import org.testng.Assert;
import org.testng.annotations.Test;

public class GetRequestTest {

    @Test
    public void testGetRequest() {
        GetRequest getRequest = new GetRequest();
        GetResponse response = new GetResponse(getRequest.get("/endpoint"));

        Assert.assertEquals(response.getStatusCode(), 200);
        Assert.assertTrue(response.getResponseBody().contains("expectedValue"));
    }
}
```

<h2>Contributing</h2>
To contribute to this project:

Fork the repository.

Create a new branch (git checkout -b feature-branch).

Commit your changes (git commit -am 'Add new feature').

Push the branch (git push origin feature-branch).

Create a new Pull Request.

