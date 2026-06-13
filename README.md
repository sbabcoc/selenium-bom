# Selenium BOM

This project provides a [Bill of Materials](https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html#bill-of-materials-bom-poms) (BOM) for synchronizing dependency versions across [Selenium Foundation](https://github.com/sbabcoc/Selenium-Foundation), [Selenium Grid Manager](https://github.com/sbabcoc/selenium-grid-manager), and their client projects.

## Available Variants

Two BOM variants are published, one for each supported Selenium API version:

| Artifact | Selenium API |
|----------|-------------|
| `selenium-bom-s3` | Selenium 3 |
| `selenium-bom-s4` | Selenium 4 |

## Version Compatibility

BOM versions are kept in sync with `selenium-foundation` and `selenium-grid-manager`. The base version number (without the `-s3`/`-s4` suffix) corresponds to the BOM version:

| BOM Version | selenium-foundation | selenium-grid-manager |
|-------------|--------------------|-----------------------|
| 34.1.0      | 35.0.4-s3 / 35.0.4-s4 | 35.0.4-s3 / 35.0.4-s4 |

## Usage

### Maven

Import the appropriate BOM variant in your `dependencyManagement` section:

```xml
<dependencyManagement>
    <dependencies>
        <!-- Selenium 4 variant -->
        <dependency>
            <groupId>com.nordstrom.ui-tools</groupId>
            <artifactId>selenium-bom-s4</artifactId>
            <version>34.1.0</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

Then declare dependencies without version numbers:

```xml
<dependencies>
    <dependency>
        <groupId>com.nordstrom.ui-tools</groupId>
        <artifactId>selenium-foundation</artifactId>
    </dependency>
    <dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-chrome-driver</artifactId>
    </dependency>
</dependencies>
```

### Gradle

Import the appropriate BOM variant using the `platform()` dependency:

```groovy
dependencies {
    implementation platform('com.nordstrom.ui-tools:selenium-bom-s4:34.1.0')

    implementation 'com.nordstrom.ui-tools:selenium-foundation'
    implementation 'org.seleniumhq.selenium:selenium-chrome-driver'
}
```

## Managed Dependencies

### Shared (both variants)

| Artifact | Description |
|----------|-------------|
| `com.nordstrom.tools:java-utils` | Java utilities |
| `com.nordstrom.tools:settings` | Settings management |
| `com.nordstrom.tools:junit-foundation` | JUnit Foundation |
| `com.github.sbabcoc:logback-testng` | Logback adapter for TestNG |
| `org.apache.httpcomponents:httpclient` | Apache HTTP client |
| `org.apache.commons:commons-lang3` | Apache Commons Lang |
| `org.apache.commons:commons-text` | Apache Commons Text |
| `com.beust:jcommander` | Command line parsing |
| `com.google.guava:guava` | Google Guava |
| `org.yaml:snakeyaml` | YAML parser |
| `net.bytebuddy:byte-buddy` | Byte code generation |
| `org.hamcrest:hamcrest-core` | Hamcrest matchers |
| `junit:junit` | JUnit 4 |
| `org.mockito:mockito-core` | Mockito |

### Selenium 4 variant (`selenium-bom-s4`)

| Artifact | Description |
|----------|-------------|
| `com.nordstrom.ui-tools:selenium-foundation` | Selenium Foundation (s4) |
| `com.nordstrom.ui-tools:selenium-grid-manager` | Selenium Grid Manager (s4) |
| `com.nordstrom.ui-tools:htmlunit-remote` | HtmlUnit remote driver |
| `com.nordstrom.tools:testng-foundation` | TestNG Foundation (Java 11+) |
| `org.seleniumhq.selenium:selenium-grid` | Selenium Grid |
| `org.seleniumhq.selenium:selenium-support` | Selenium Support |
| `org.seleniumhq.selenium:selenium-chrome-driver` | Chrome driver |
| `org.seleniumhq.selenium:selenium-edge-driver` | Edge driver |
| `org.seleniumhq.selenium:selenium-firefox-driver` | Firefox driver |
| `org.seleniumhq.selenium:selenium-safari-driver` | Safari driver |
| `org.seleniumhq.selenium:htmlunit3-driver` | HtmlUnit3 driver |
| `org.htmlunit:htmlunit` | HtmlUnit |
| `io.appium:java-client` | Appium Java client |
| `org.eclipse.jetty:jetty-servlet` | Jetty servlet container |
| `org.jsoup:jsoup` | HTML parser |
| `io.netty:netty-transport-native-epoll` | Netty epoll transport |
| `io.netty:netty-transport-native-kqueue` | Netty kqueue transport |

### Selenium 3 variant (`selenium-bom-s3`)

| Artifact | Description |
|----------|-------------|
| `com.nordstrom.ui-tools:selenium-foundation` | Selenium Foundation (s3) |
| `com.nordstrom.ui-tools:selenium-grid-manager` | Selenium Grid Manager (s3) |
| `com.nordstrom.tools:testng-foundation` | TestNG Foundation (Java 8) |
| `org.seleniumhq.selenium:selenium-server` | Selenium Server |
| `org.seleniumhq.selenium:selenium-support` | Selenium Support |
| `org.seleniumhq.selenium:selenium-chrome-driver` | Chrome driver |
| `org.seleniumhq.selenium:selenium-edge-driver` | Edge driver |
| `org.seleniumhq.selenium:selenium-firefox-driver` | Firefox driver |
| `org.seleniumhq.selenium:selenium-safari-driver` | Safari driver |
| `org.seleniumhq.selenium:htmlunit-driver` | HtmlUnit driver |
| `io.appium:java-client` | Appium Java client |
| `io.github.bonigarcia:webdrivermanager` | WebDriver Manager |
| `com.squareup.okhttp3:okhttp` | OkHttp |
| `com.squareup.okio:okio` | Okio |
| `org.jetbrains.kotlin:kotlin-stdlib` | Kotlin standard library |
| `org.jetbrains.kotlin:kotlin-stdlib-common` | Kotlin standard library (common) |
| `org.eclipse.jetty.websocket:websocket-client` | Jetty WebSocket client |
| `org.jsoup:jsoup` | HTML parser |

## License

This project is licensed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.txt).
