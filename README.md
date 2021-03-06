# id

### Introduction

It is a distributed ID generator powered by the algorithm of [snowflake](https://github.com/twitter-archive/snowflake), which can:

- generate 53-bit integer (JavaScript comparable)  as unique ID ascending by time
- support at most 16 distributed nodes (4 data centers, each contains 4 machines)
- at most generate 256 unique IDs at the same milliseconds from each node

### Demo

https://id.zzc.icu/

### Run

Execute following commands to compile and run.

``` bash
./mvnw clean && ./mvnw package -Dmaven.test.skip=true # macOS and Linux only
./mvnw.cmd clean && ./mvnw.cmd package -Dmaven.test.skip=true # Windows only

java -jar ./target/id.jar
```

### Config

The default config file `application.properties` is like:

```
server.port=8004
snowflake.twepoch=1596240000000
snowflake.datacenterId=0
snowflake.workerId=0
```

See [additional-spring-configuration-metadata.json](./src/main/resources/META-INF/additional-spring-configuration-metadata.json) for more details.

Place user-defined config file at path `./target/config/application.properties` to override the default one.

### Docker

See [Docker.md](./Docker.md) for details.

### Develop

Execute following commands before making any change.

``` bash
git config --local core.autocrlf input
git config --local core.safecrlf true
```

### Reference

- https://github.com/twitter-archive/snowflake
- https://developer.twitter.com/en/docs/basics/twitter-ids
- https://www.cnblogs.com/relucent/p/4955340.html
- https://juejin.im/post/6844903562007314440
- https://segmentfault.com/a/1190000011282426

### Others

- All code files are edited by [IntelliJ IDEA](https://www.jetbrains.com/idea/).
- All ".md" files are edited by [Typora](http://typora.io/).
- The style of all ".md" files is [Github Flavored Markdown](https://guides.github.com/features/mastering-markdown/#GitHub-flavored-markdown).
- There is a LF (Linux) at the end of each line.