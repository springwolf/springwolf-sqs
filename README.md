![version](https://img.shields.io/github/v/release/springwolf/springwolf-sqs)
![springwolf-core](https://github.com/springwolf/springwolf-sqs/workflows/springwolf-sqs/badge.svg)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

# Springwolf SQS Plugin
##### Automated documentation for Spring Boot application with SQS consumers

### Table Of Contents
- [About](#about)
- [Usage](#usage)
  - [Dependencies](#dependencies)
  - [Configuration class](#configuration-class)
- [Verify](#verify)
- [Example Project](#example-project)

### About
This plugin generates an [AsyncAPI document](https://www.asyncapi.com/) from `@SqsListener` methods.
For more information, check out [springwolf-core](https://github.com/springwolf/springwolf-core).

### Usage
Add the following dependencies and configuration class to enable this plugin.

#### Dependencies
```groovy
repositories {
    jcenter()
}
dependencies {
    // Provides the documentation API    
    implementation 'io.github.stavshamir:springwolf-sqs:0.1.0'
    
    // Provides the UI - optional (recommended)
    runtimeOnly 'io.github.stavshamir:springwolf-ui:0.0.2'
}
```

### Configuration class
Add a configuration class and provide a `SqsProtocolConfiguration` bean and a `AsyncApiDocket` bean:
```java
@Configuration
@EnableAsyncApi
public class AsyncApiConfiguration {
}
```
The basePackage field must be set with the name of the package containing the classes to be scanned for `@SqsListener`
annotated methods.

#### Verify
If you have included the UI dependency, access it with the following url: `localhost:8080/asyncapi-ui.html`.
If not, try the following endpoint: `localhost:8080/asyncapi/docs`.


### Example Project
See [springwolf-sqs-example](https://github.com/springwolf/springwolf-sqs/springwolf-sqs-example).
