# Relaxing Edges
```java
key[v] <- min(key[v],key[u]+weight(u,v))
```
Code above is for *relaxing* the edge. As the edge was 'tight' with a lot of weight, this reduces the key[v] thus *relaxing*.
![[Edge Relaxation|600]]
