# Maven — Java Build & Dependency Management

## 1. What is Maven?

**Maven is a build automation and dependency management tool for Java projects.**

It helps with:

* Managing dependencies
* Compiling Java code
* Running tests
* Packaging applications
* Cleaning build files
* Maintaining a standard project structure

```text
Java Project
     ↓
   Maven
     ↓
Dependencies + Build + Test + Package
```

---

## 2. Why Do We Need Maven?

Without Maven, we would have to manually:

* Download `.jar` files
* Manage library versions
* Manage dependencies of dependencies
* Handle conflicting versions
* Compile the project
* Run tests
* Create the final `.jar`
* Clean generated files

For example:

```text
Spring Web
    ↓
Other required libraries
    ↓
More dependencies
```

Maven automatically manages these dependencies.

---

## 3. What Does Maven Do?

### Dependency Management

Downloads and manages external libraries.

Examples:

* Spring Boot
* Hibernate
* MySQL/PostgreSQL Driver
* JUnit
* Spring Security

### Build Automation

Compiles Java code and creates the application package.

```text
.java
 ↓
compile
 ↓
.class
 ↓
package
 ↓
.jar
```

### Testing

Runs project tests.

```bash
mvn test
```

### Packaging

Creates `.jar` or `.war` files.

```bash
mvn package
```

### Cleaning

Removes generated build files.

```bash
mvn clean
```

---

# 4. `pom.xml`

`pom.xml` is the main configuration file of a Maven project.

**POM = Project Object Model**

Example structure:

```xml
<project>

    <groupId>com.example</groupId>
    <artifactId>myapp</artifactId>
    <version>1.0</version>

    <dependencies>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>

    </dependencies>

</project>
```

The important sections include:

* `groupId` → identifies the project/group
* `artifactId` → project name
* `version` → project version
* `dependencies` → external libraries required by the project

---

# 5. What is a Dependency?

A **dependency is an external library that your application needs**.

For example:

```text
Spring Boot Application
        ↓
Needs Spring Web
        ↓
Spring Web = Dependency
```

Instead of manually downloading the library, we declare it in `pom.xml`.

Maven downloads and manages it automatically.

---

# 6. Dependency Management

Maven also handles **transitive dependencies**.

For example:

```text
Your Application
      ↓
Spring Web
      ↓
Spring Core
      ↓
Other Required Libraries
```

You don't necessarily need to manually add every library.

Maven resolves the required dependency chain.

---

# 7. Maven Repository

Maven gets dependencies from repositories.

The most important public repository is:

**Maven Central**

The general flow is:

```text
pom.xml
   ↓
Maven
   ↓
Maven Central
   ↓
Download Dependency
   ↓
Local Repository
```

---

# 8. Local Maven Repository

Maven stores downloaded dependencies locally so they can be reused.

On Windows, the default location is usually:

```text
C:\Users\<username>\.m2\repository
```

So if a dependency has already been downloaded, Maven can use the local copy instead of downloading it again.

---

# 9. Maven Project Structure

A standard Maven project looks like:

```text
my-project/
│
├── pom.xml
│
└── src/
    ├── main/
    │   ├── java/
    │   └── resources/
    │
    └── test/
        └── java/
```

### `src/main/java`

Contains application Java code.

### `src/main/resources`

Contains configuration and other resources.

For Spring Boot:

```text
application.properties
```

### `src/test/java`

Contains test code.

### `pom.xml`

Contains Maven project configuration and dependencies.

---

# 10. Important Maven Commands

### Check Maven

```bash
mvn -version
```

### Clean

```bash
mvn clean
```

Removes generated build files.

### Compile

```bash
mvn compile
```

Compiles the source code.

### Test

```bash
mvn test
```

Runs tests.

### Package

```bash
mvn package
```

Builds, tests and packages the application.

Usually creates:

```text
target/
└── application.jar
```

### Install

```bash
mvn install
```

Builds the project and installs the generated artifact into the local Maven repository.

---

# 11. Maven Lifecycle

Maven has a predefined build lifecycle.

Simplified:

```text
validate
   ↓
compile
   ↓
test
   ↓
package
   ↓
verify
   ↓
install
   ↓
deploy
```

You don't normally need to execute every phase separately.

For example:

```bash
mvn package
```

will execute the required earlier phases:

```text
compile
   ↓
test
   ↓
package
```

---

# 12. Maven vs Java

They are different.

```text
Java
 ↓
Programming Language + JDK
```

```text
Maven
 ↓
Build + Dependency Management Tool
```

They work together:

```text
Java JDK
   +
Maven
   +
Spring Boot
   ↓
Java Backend Application
```

---

# 13. Maven vs Spring Boot

Maven is **not a framework**.

```text
Spring Boot
    ↓
Backend Framework
```

```text
Maven
    ↓
Build & Dependency Management Tool
```

They work together:

```text
Spring Boot Project
       ↓
    pom.xml
       ↓
     Maven
       ↓
Dependencies
       ↓
    Build
       ↓
 application.jar
```

---

# 14. Complete Maven Flow

Suppose a Spring Boot project contains a dependency in `pom.xml`.

When we run:

```bash
mvn clean package
```

Maven roughly performs:

```text
Read pom.xml
     ↓
Find dependencies
     ↓
Check local .m2 repository
     ↓
Download missing dependencies
     ↓
Compile Java code
     ↓
Run tests
     ↓
Package application
     ↓
Create JAR
```

The final application may be:

```text
target/
└── my-application.jar
```

It can then be executed using:

```bash
java -jar target/my-application.jar
```

---

# Key Takeaway

> **Maven is a Java build automation and dependency management tool that manages project dependencies and automates tasks such as compiling, testing and packaging.**

The main things to remember:

```text
pom.xml
   ↓
Dependencies
   ↓
Maven
   ↓
Build
   ↓
Test
   ↓
Package
   ↓
JAR
```

For Spring Boot development, the most important Maven concepts are:

* `pom.xml`
* Dependencies
* Maven repositories
* Local `.m2` repository
* Maven lifecycle
* `mvn clean`
* `mvn test`
* `mvn package`
* `mvn install`
