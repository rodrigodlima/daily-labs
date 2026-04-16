# Java notes

Short, practical notes collected while studying and testing.

## Run single-file source (JEP 330)

```java
java Hello.java
```

## List JVM flags in use

```java
java -XX:+PrintFlagsFinal -version | grep -i heap
```
