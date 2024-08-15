## Знакомоство с SonarQube
Первый запуск сканера
![изображение](https://github.com/user-attachments/assets/f0c2bb80-1756-4672-bf10-8757b605b290)

После исправления ошибок
![изображение](https://github.com/user-attachments/assets/118f778d-5ce9-4d96-915f-007265a03a0b)

## Знакомство с Nexus
### maven-metadata.xml
```
<metadata modelVersion="1.1.0">
<groupId>netology</groupId>
<artifactId>java</artifactId>
<versioning>
<latest>8_282</latest>
<release>8_282</release>
<versions>
<version>8_102</version>
<version>8_282</version>
</versions>
<lastUpdated>20240815162527</lastUpdated>
</versioning>
</metadata>
```
### смотрим скачанные зависимости
[xvv@host-15 mvn]$ ls ~/.m2/repository/netology/java/8_282/

java-8_282-distrib.tar.gz  java-8_282-distrib.tar.gz.sha1  java-8_282.pom.lastUpdated  _remote.repositories
### pom
```
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
 
  <groupId>com.netology.app</groupId>
  <artifactId>simple-app</artifactId>
  <version>1.0-SNAPSHOT</version>
   <repositories>
    <repository>
      <id>my-repo</id>
      <name>maven-public</name>
      <url>http://51.250.36.60:8081/repository/maven-public/</url>
    </repository>
  </repositories>
  <dependencies>
    <dependency>
      <groupId>netology</groupId>
      <artifactId>java</artifactId>
      <version>8_282</version>
      <classifier>distrib</classifier>
      <type>tar.gz</type>
    </dependency> 
  </dependencies>
</project>
