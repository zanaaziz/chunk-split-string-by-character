# Splitting Strings Into Chunks of a Given Size by Character
This code allows you to format a large piece of string data into streamable chunks split at certain character(s).

It's typically useful for streaming large commands/data to devices that you have a limited amount of input available at once.

## Parameters
```java
String data, String characters, int chunk_size
```

- `data` is the original string you'd like to format.
- `characters` is the character(s) you want to split by.
- `chunk_size` is the maximum size per chunk of data you want to set.

## Typical Use
```java
int chunk_index = 1;
for(String chunk : chunkifyStringByCharacters(large_piece_of_data, ";", 64)){
  System.out.println("Chunk #" + chunk_index + " [" + chunk.getBytes().length + "] - " + chunk);
  // do something with the current chunk...
  chunk_index += 1;
}
```

## Result
```
Chunk #1 [52] - PU4365,11382;PD10912,11382;PD10912,4553;PD4365,4553;
Chunk #2 [61] - PD4365,11382;PU4365,4553;PD4376,4552;PD4387,4552;PD4399,4551;
Chunk #3 [60] - PD4410,4549;PD4421,4547;PD4433,4544;PD4444,4541;PD4455,4538;
Chunk #4 [60] - PD4467,4534;PD4478,4530;PD4488,4525;PD4499,4520;PD4509,4514;
...
```
