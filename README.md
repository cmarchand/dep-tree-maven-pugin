## dep-tree-maven-plugin

This plugin generates a text file that contains the dependency-tree informations, and declares it as an artifact. Hence, when a `mvn deploy` is run, this text file is also deployed.

This allows a [Nexus](https://fr.sonatype.com/nexus-repository-sonatype) Open Source to store dependency informations.  
Then, a simple script can snif the Nexus repository, read dependency trees information files, and fill in a database. If interested, you may have a look at [dependency-sniffer](https://github.com/cmarchand/dependency-sniffer) which does this, and provides a web client to browse dependencies.

Usually, you use this plugin only when you publish, so on deploy phase. But as it does very simple thinggs, you can use it at each build.

To use this plugin, just add this to your `pom.xml` :

```
  <build>
    <plugins>
      <plugin>
        <groupId>top.marchand.maven</groupId>
        <artifactId>dep-tree-maven-plugin</artifactId>
        <version >1.0.0</version>
        <executions>
          <execution>
            <goals><goal>tree</goal></goals>
          </execution>
        </executions>
      </plugin>
...
```

