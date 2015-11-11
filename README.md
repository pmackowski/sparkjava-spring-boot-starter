# sparkjava-spring-boot-starter

Project is currently not available in a public Maven repository.

After cloning and installing locally:

    mvn clean install

add following dependency:

```xml
    <dependency>
        <groupId>pl.coffeecode.boot</groupId>
        <artifactId>sparkjava-spring-boot-starter</artifactId>
        <version>1.0</version>
    </dependency>
```

Getting started
---------------

```java
import static spark.Spark.*;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.core.annotation.Order;
import org.springframework.stereotype.Component;
import pl.coffeecode.boot.sparkjava.Spark;

@Component
@Order(value=1)
public class HelloSpark implements Spark {

    @Autowired
    private HelloWorldService helloWorldService;

    @Override
    public void register() {
        get("/hello", (request, response) -> helloWorldService.hello() );
    }

}
```


