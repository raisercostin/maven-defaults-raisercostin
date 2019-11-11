[![Download](https://api.bintray.com/packages/raisercostin/maven/maven-defaults-raisercostin/images/download.svg)](https://bintray.com/raisercostin/maven/maven-defaults-raisercostin/_latestVersion)


# Usage

Include this pom as parent.

```xml
<project>
  <modelVersion>4.0.0</modelVersion>
  <parent>
    <groupId>org.raisercostin</groupId>
    <artifactId>maven-defaults-raisercostin</artifactId>
    <version>1.0</version>
  </parent>
  ...
</project>
``` 

No need to include a repository as is available at https://jcenter.bintray.com/org/raisercostin/maven-defaults-raisercostin/

# Features
- Support for scala if src/main/scala exists
- Support for kotlin if src/main/kotlin exists

# Development
- To release `mvn release:prepare release:perform -DskipTests=true -Prelease -Darguments="-DskipTests=true -Prelease"` 