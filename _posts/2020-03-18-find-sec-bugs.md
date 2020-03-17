# 简介

**[find-sec-bugs](https://find-sec-bugs.github.io/) 即 Find Security Bugs，是[SpotBugs](https://spotbugs.github.io/)的一款插件，用于Java Web应用程序的安全审核。**

# 特性

#### 1）135 种 bug 模型

可以检测 超过816个独特的 API 签名的 [135 种类型的漏洞](https://find-sec-bugs.github.io/bugs.htm) 。

#### 2）支持多种框架和库

涵盖流行的框架，包括 Spring-MVC、Struts 和 Tapestry 等。

#### 3）IDE集成

插件适用于 [Eclipse](http://findbugs.sourceforge.net/manual/eclipse.html)、[IntelliJ](https://plugins.jetbrains.com/plugin/3847?pr=idea)、[Android Studio](https://plugins.jetbrains.com/plugin/3847?pr=idea) 和 [NetBeans](https://netbeans.org/kb/docs/java/code-inspect.html#fb)。
 命令行集成可用于 [Ant](http://findbugs.sourceforge.net/manual/anttask.html) 和[Maven](https://github.com/spotbugs/spotbugs-maven-plugin)。

#### 4）持续集成

可以与 [Jenkins](https://plugins.jenkins.io/findbugs) 和 [SonarQube](https://github.com/spotbugs/sonar-findbugs) 等系统集成。

#### 5）覆盖 OWASP TOP 10 和 CWE 

对于每种错误模式，都提供了广泛的参考，并引用了 OWASP Top 10 和 CWE。

#### 6）欢迎参与贡献

项目开源，并且[欢迎大家参与贡献](https://github.com/find-sec-bugs/find-sec-bugs/graphs/contributors)。

# 用法举例
## Maven
#### 1）配置POM
配置[SpotBugs Maven Plugin](https://github.com/spotbugs/spotbugs-maven-plugin)到`pom.xml`。
```
<build>
    <plugins>
        
        [...]
        <!-- SpotBugs Static Analysis -->
        <plugin>
            <groupId>com.github.spotbugs</groupId>
            <artifactId>spotbugs-maven-plugin</artifactId>
            <version>3.1.12</version>
            <configuration>
                <effort>Max</effort>
                <threshold>Low</threshold>
                <failOnError>true</failOnError>
                <includeFilterFile>${session.executionRootDirectory}/spotbugs-security-include.xml</includeFilterFile>
                <excludeFilterFile>${session.executionRootDirectory}/spotbugs-security-exclude.xml</excludeFilterFile>
                <plugins>
                    <plugin>
                        <groupId>com.h3xstream.findsecbugs</groupId>
                        <artifactId>findsecbugs-plugin</artifactId>
                        <version>1.9.0</version>
                    </plugin>
                </plugins>
            </configuration>
        </plugin>
    </plugins>
</build>
```

#### 2）执行检查
```
mvn compile
mvn spotbugs:spotbugs
```

#### 3) 结果分析
**GUI方式:**
```
mvn spotbugs:gui
```
**XML Report:**
查看`target/findbugsXml.xml`的结果报告。