<a id="readme-top"></a>

<div align="center">

# shiro-kisso-spring-boot-starter

**Spring Boot Starter for shiro-kisso**

[![Maven Central](https://img.shields.io/maven-central/v/io.github.easy4j/shiro-kisso-spring-boot-starter)](https://github.com/easy-4-java/shiro-kisso-spring-boot-starter)
[![Java](https://img.shields.io/badge/Java-17-orange)](#3-requirements-and-compatibility)
[![License](https://img.shields.io/badge/license-Apache-2.0-green)](https://www.apache.org/licenses/LICENSE-2.0)

[简体中文](./README.zh-CN.md) | [English](./README.md)

[Positioning](#1-positioning) · [Capabilities](#2-core-capabilities) ·
[Dependency](#5-dependency) · [Quick Start](#6-quick-start) ·
[Configuration](#7-configuration-reference) · [Versions](#9-version-lines-and-compatibility) ·
[Build](#10-build-and-test) · [License](#12-license)

</div>

---

> **Current Version**：`1.0.3-SNAPSHOT`<br>
> **JDK Baseline**：`17`<br>
> **Group ID**：`io.github.easy4j`<br>
> **Artifact ID**：`shiro-kisso-spring-boot-starter`<br>
> **License**：Apache License 2.0<br>

## 1. Positioning

**shiro-kisso-spring-boot-starter** is a Spring Boot starter that integrates **shiro-kisso** for applications using shiro-kisso. It provides auto-configuration, property binding, and ready-to-use beans so that applications can consume shiro-kisso capabilities with minimal setup.

| Dimension | Description |
|---|---|
| Type | Spring Boot Starter |
| Consumers | Spring Boot applications using shiro-kisso |
| Core Capabilities | auto-configuration, property binding, ready-to-use beans for shiro-kisso |
| JDK | `17` |
| Coordinates | `io.github.easy4j:shiro-kisso-spring-boot-starter:1.0.3-SNAPSHOT` |
| Config Prefix | `shiro.kisso` |

## 2. Core Capabilities

| Capability | Status | Description |
|---|:---:|---|
| Auto-configuration | ✅ Stable | Registers shiro-kisso beans automatically |
| Property Binding | ✅ Stable | Binds `shiro.kisso.*` to `ShiroKissoProperties` |
| `SSOAuthorization` bean | ✅ Stable | Auto-registered via ShiroKissoWebAutoConfiguration |

## 3. Requirements and Compatibility

| Dependency | Minimum | Evidence |
|---|---:|---|
| JDK | `17` | `pom.xml` |
| Spring Boot | `2.3.0.RELEASE` | `pom.xml` parent |
| Maven | `3.6+` | Maven Enforcer |

## 4. Auto-configuration

The starter auto-configures the following beans:

| Bean | Condition | Missing Behavior |
|---|---|---|
| `SSOAuthorization` | classpath + property | not created |
| `SSOHandlerInterceptor` | classpath + property | not created |
| `KissoStatelessPrincipalRepository` | classpath + property | not created |

Auto-configuration registration:

- `META-INF/spring/org.springframework.boot.autoconfigure.AutoConfiguration.imports` (Spring Boot 2.7+ / 3.x / 4.x)
- `META-INF/spring.factories` (Spring Boot 2.x legacy)

## 5. Dependency

```xml
<dependency>
    <groupId>io.github.easy4j</groupId>
    <artifactId>shiro-kisso-spring-boot-starter</artifactId>
    <version>1.0.3-SNAPSHOT</version>
</dependency>
```

No additional easy4j component dependencies.

## 6. Quick Start

### 6.1 Add dependency

Add the dependency above to your `pom.xml`.

### 6.2 Configure

```yaml
shiro.kisso:
  enabled: true
```

### 6.3 Use the bean

```java
@SpringBootApplication
public class Application {
    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}
```

Then inject the auto-configured bean in your code:

```java
@Autowired
private SSOAuthorization kissoAuthorization;
```

## 7. Configuration Reference

### 7.1 Config Prefix

`shiro.kisso`

### 7.2 Configuration Items

| Property | Type | Default | Required | Description | Sensitive |
|---|---|---|:---:|---|:---:|
| `shiro.kisso.enabled` | boolean | `true` | No | Enable the starter | No |
<!-- additional properties below -->

## 8. Version Lines and Compatibility

| Branch | JDK | Spring Boot | Component Version | Status |
|---|---:|---:|---|:---:|
| `2.3.x` / `2.7.x` | `8+` | 2.3.x / 2.7.x | `1.0.x` | Maintenance |
| `3.0.x` ~ `3.5.x` | `17` | 3.x | `2.0.x` | Maintenance |
| `4.0.x` / `4.1.x` | `17+` | 4.x | `3.0.x` | Active |

## 9. Build and Test

```bash
mvn clean verify
mvn -pl shiro-kisso-spring-boot-starter -am test
```

## 10. Troubleshooting

| Symptom | Diagnosis | Resolution |
|---|---|---|
| Bean not created | Check auto-configuration report | Verify `shiro.kisso.enabled=true` and classpath |
| `ClassNotFoundException` | Missing dependency | Add the required module |
| Version conflict | `mvn dependency:tree` | Use BOM for version alignment |

## 11. Contribution

1. Fork the repository.
2. Create a feature branch.
3. Run `mvn clean verify` before submitting.
4. Submit a pull request.

## 12. License

This project is licensed under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0).

---

<div align="center">

[Back to top](#readme-top) · [Issues](https://github.com/easy-4-java/shiro-kisso-spring-boot-starter/issues) · [Repository](https://github.com/easy-4-java/shiro-kisso-spring-boot-starter)

</div>
