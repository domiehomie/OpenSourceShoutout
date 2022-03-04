# [Caffeine](https://github.com/ben)

if you're ever going to be caching something at all in java, check out https://github.com/ben-manes/caffeine
It boasts a highly performant and customizable API to use and customize your caches. very useful indeed! 

## Example

```java
LoadingCache<Key, Graph> graphs = Caffeine.newBuilder()
    .maximumSize(10_000)
    .expireAfterWrite(Duration.ofMinutes(5))
    .refreshAfterWrite(Duration.ofMinutes(1))
    .build(key -> createExpensiveGraph(key));
```