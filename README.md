# Spring Cloud GCP for Cloud Logging Getting Started

Cloud Logging is part of the Google Cloud's operations suite of products. It includes storage for logs, a user interface called the Logs Explorer, and an API to manage logs programmatically. Logging lets you read and write log entries, query your logs, and control how you route and use your logs.

## Description
### Dependency
- com.google.cloud
  - `spring-cloud-gcp-starter-logging`

### Set up for GCP project ID and Credentials 
```shell script
$ gcloud config set project [YOUR_PROJECT_ID]
$ gcloud auth application-default login
```

### Logback Configuration
Logback is the most widely used logging frameworks.
Logback is a replacement for its predecessor, Log4j.
Logback offers a faster implementation than Log4j, provides more options for configuration, and more flexibility in archiving old log files.


```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <include resource="org/springframework/boot/logging/logback/defaults.xml"/>
    <include resource="com/google/cloud/spring/logging/logback-appender.xml" />
    <appender name="STDOUT" class="ch.qos.logback.core.ConsoleAppender">
        <encoder>
            <pattern>
                %d{dd-MM-yyyy HH:mm:ss.SSS} %magenta([%-15.15thread]) %highlight(%-5level) %yellow(%-40.40C{40}) - %msg%n%throwable
            </pattern>
        </encoder>
    </appender>

    <root level="INFO">
        <appender-ref ref="STDOUT" />
        <appender-ref ref="STACKDRIVER" />
    </root>
</configuration>
```

## Demo

## Features

- feature:1
- feature:2

## Requirement

## Usage

## Installation

## Licence

Released under the [MIT license](https://gist.githubusercontent.com/shinyay/56e54ee4c0e22db8211e05e70a63247e/raw/34c6fdd50d54aa8e23560c296424aeb61599aa71/LICENSE)

## Author

[shinyay](https://github.com/shinyay)
