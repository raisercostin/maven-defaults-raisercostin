[![Download](https://img.shields.io/maven-metadata/v?metadataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Fraisercostin%2Fmaven-repo%2Fmaster%2Forg%2Fraisercostin%2Fmaven-defaults-raisercostin%2Fmaven-metadata.xml)](https://raw.githubusercontent.com/raisercostin/maven-repo/master/org/raisercostin/maven-defaults-raisercostin/maven-metadata.xml)

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
    <version>1.24</version>
  </parent>
  ...
</project>
``` 

Also add the repository where this is hosted `pom.xml/project/repositories` that points to https://github.com/raisercostin/maven-repo
```xml
    <repository>
      <id>raisercostin-github</id>
      <name>Repository at https://github.com/raisercostin/maven-repo</name>
      <url>https://raw.githubusercontent.com/raisercostin/maven-repo/master/</url>
    </repository>
```

## Executable jar
To have an executable jar add this to your `pom.xml/project/build` and a new file `${finalName}-myapp.jar` will be generated.
```xml
      <plugin>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-maven-plugin</artifactId>
        <configuration>
          <mainClass>${main.class}</mainClass>
          <classifier>myapp</classifier>
        </configuration>
      </plugin>
```

# Development
- To release
  `mvn release:prepare release:perform -DskipTests=true -Prelease -Darguments="-DskipTests=true -Prelease"` 
- To update versions for a profile
  `mvn versions:update-properties -Pjunit5`
- See possible dependency updates
  `mvn versions:display-dependency-updates`
