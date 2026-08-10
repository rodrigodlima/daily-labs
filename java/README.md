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

## Records

```java
record Point(int x, int y) {}
```

## Virtual threads

```java
try (var ex = Executors.newVirtualThreadPerTaskExecutor()) {
    ex.submit(() -> doWork());
}
```

## Pattern matching for switch

```java
String d = switch (o) {
    case Integer i -> "int " + i;
    case String s -> "str " + s;
    default -> "other";
};
```

## Text blocks

```java
String json = """
    {"name": "rodrigo"}
    """;
```

## Sealed interfaces

```java
sealed interface Shape permits Circle, Square {}
```

## Streams grouping

```java
Map<String, Long> c = list.stream()
    .collect(Collectors.groupingBy(User::city, Collectors.counting()));
```

## Optional chain

```java
String city = Optional.ofNullable(user)
    .map(User::address)
    .map(Address::city)
    .orElse("unknown");
```

## Heap dump of a running JVM

```java
jcmd <pid> GC.heap_dump /tmp/heap.hprof
```

## HttpClient GET

```java
var client = HttpClient.newHttpClient();
var req = HttpRequest.newBuilder(URI.create(url)).build();
var body = client.send(req, BodyHandlers.ofString()).body();
```

## Immutable collections

```java
var list = List.of(1, 2, 3);
var map = Map.of("a", 1);
```

## Try-with-resources

```java
try (var reader = Files.newBufferedReader(path)) {
    return reader.readLine();
}
```

## JFR recording

```java
java -XX:StartFlightRecording=duration=60s,filename=rec.jfr -jar app.jar
```
