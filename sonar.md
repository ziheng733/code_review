# sonar

## sonarQube搭建
+ 参见：https://blog.csdn.net/aixiaoyang168/article/details/77565756

## maven project 配置
配置 settings.xml文件  
```
<settings>
    <pluginGroups>
        <pluginGroup>org.sonarsource.scanner.maven</pluginGroup>
    </pluginGroups>
    <profiles>
        <profile>
            <id>sonar</id>
            <activation>
                <activeByDefault>true</activeByDefault>
            </activation>
            <properties>
                <!-- 配置 Sonar Host地址，默认：http://localhost:9000 -->
                <sonar.host.url>
                  http://myserver:9000
                </sonar.host.url>
            </properties>
        </profile>
     </profiles>
</settings>
```

配置插件  
```
<build>
  <plugins>
    <plugin>
      <groupId>org.sonarsource.scanner.maven</groupId>
      <artifactId>sonar-maven-plugin</artifactId>
      <version>3.7.0.1746</version>
    </plugin>
  </plugins>
</build>
```

运行sonar分析  
```
mvn clean install sonar:sonar
```
