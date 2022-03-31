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
    <version>1.18</version>
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
  
- To fix the following warnings
```
[INFO] [WARNING] Some problems were encountered while building the effective model for org.raisercostin:maven-defaults-raisercostin:pom:1.4
[INFO] [WARNING] 'dependencyManagement.dependencies.dependency.(groupId:artifactId:type:classifier)' must be unique: commons-io:commons-io:jar -> duplicate declaration of version 2.6 @ line 437, column 19
[INFO] [WARNING] 'build.pluginManagement.plugins.plugin.(groupId:artifactId)' must be unique but found duplicate declaration of plugin org.jetbrains.kotlin:kotlin-maven-plugin @ line 979, column 17
[INFO] [WARNING] 'build.pluginManagement.plugins.plugin.(groupId:artifactId)' must be unique but found duplicate declaration of plugin org.apache.maven.plugins:maven-compiler-plugin @ line 1004, column 17
[INFO] [WARNING] 'build.pluginManagement.plugins.plugin.(groupId:artifactId)' must be unique but found duplicate declaration of plugin org.apache.maven.plugins:maven-failsafe-plugin @ line 1010, column 17
[INFO] [WARNING] 'build.pluginManagement.plugins.plugin.(groupId:artifactId)' must be unique but found duplicate declaration of plugin org.apache.maven.plugins:maven-jar-plugin @ line 1024, column 17
[INFO] [WARNING] 'build.pluginManagement.plugins.plugin.(groupId:artifactId)' must be unique but found duplicate declaration of plugin org.apache.maven.plugins:maven-war-plugin @ line 1035, column 17
[INFO] [WARNING] 'build.pluginManagement.plugins.plugin.(groupId:artifactId)' must be unique but found duplicate declaration of plugin org.codehaus.mojo:exec-maven-plugin @ line 1046, column 17
[INFO] [WARNING] 'build.pluginManagement.plugins.plugin.(groupId:artifactId)' must be unique but found duplicate declaration of plugin org.apache.maven.plugins:maven-resources-plugin @ line 1053, column 17
[INFO] [WARNING] 'build.pluginManagement.plugins.plugin.(groupId:artifactId)' must be unique but found duplicate declaration of plugin pl.project13.maven:git-commit-id-plugin @ line 1062, column 17
[INFO] [WARNING] 'build.pluginManagement.plugins.plugin.(groupId:artifactId)' must be unique but found duplicate declaration of plugin org.springframework.boot:spring-boot-maven-plugin @ line 1079, column 17
[INFO] [WARNING] 'build.pluginManagement.plugins.plugin.(groupId:artifactId)' must be unique but found duplicate declaration of plugin org.apache.maven.plugins:maven-shade-plugin @ line 1094, column 17
[INFO] [WARNING]
```