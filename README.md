[![Download](https://api.bintray.com/packages/raisercostin/maven/maven-defaults-raisercostin/images/download.svg)](https://bintray.com/raisercostin/maven/maven-defaults-raisercostin/_latestVersion)

# Features
- Support for scala if src/main/scala exists
- Support for kotlin if src/main/kotlin exists
- Support for junit5
  - To enable junit5 profile add in your project a file `${basedir}/junit5.enable`
- Best to enable dependencies via `org.springframework.boot:*`
- (!) Enabling profiles cannot be done by defining properties in your pom since they will not influence profile activation.

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

# Development
- To release
  `mvn release:prepare release:perform -DskipTests=true -Prelease -Darguments="-DskipTests=true -Prelease"` 
- To update versions for a profile
  `mvn versions:update-properties -Pjunit5`
- See possible dependency updates
  `mvn versions:display-dependency-updates`