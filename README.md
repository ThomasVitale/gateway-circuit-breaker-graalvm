# Sample for native compilation with Spring Cloud Gateway and Circuit Breaker

Run the application on the JVM:

```shell
./gradlew bootRun
```

Verify the application works correctly:

```shell
http :8080/demo/get
```

Use a GraalVM distribution:

```shell
sdk use java 22.3.r17-grl
```

Ensure you have the native-image module installed:

```shell
gu install native-image
```

Compile the Spring Boot application to a native executable:

```shell
cd demo
./gradlew nativeCompile
```

Try running the application native executable:

```shell
./build/native/nativeCompile/demo
```

The application startup will fail with the following error:

```shell
***************************
APPLICATION FAILED TO START
***************************

Description:

Failed to bind properties under '' to org.springframework.cloud.gateway.filter.factory.SpringCloudCircuitBreakerFilterFactory$Config:

    Reason: java.lang.NoSuchMethodException: org.springframework.cloud.gateway.filter.factory.SpringCloudCircuitBreakerFilterFactory$Config.<init>()

Action:

Update your application's configuration
```
