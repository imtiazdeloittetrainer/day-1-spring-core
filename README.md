# day-1-spring-core

# Day 1 – Spring IoC Container Exercises

## Prerequisites

Before starting these exercises:

* Use **Eclipse or Spring Tool Suite (STS)**.
* Create a **normal Java Project**.
* **Do NOT use Maven.**
* **Do NOT use Spring Boot.**
* Add the required Spring JAR files manually to the project build path.

### Suggested Project Structure

```text
Spring-Day1-IoC
│
├── src
│   └── com.iits
│       ├── bean
│       │   └── Student.java
│       │
│       └── main
│           ├── BeanFactoryTest.java
│           ├── ApplicationContextTest.java
│           └── FileSystemXmlApplicationContextTest.java
│
├── lib
│   └── Spring JAR files
│
└── applicationContext.xml
```

---

# Exercise 1 – Using BeanFactory

## Objective

Create and retrieve a `Student` bean using the **Spring `BeanFactory`**.

### Step 1 – Create Student Class

Create:

```text
com.iits.bean.Student
```

with the following properties:

```text
studentId
studentName
course
```

Provide:

* Default constructor
* Getters and setters
* `displayStudent()` method

Expected output:

```text
Student ID   : 101
Student Name : Imtiaz
Course       : Java Full Stack
```

---

### Step 2 – Create XML Configuration

Create:

```text
applicationContext.xml
```

Configure the `Student` class as a Spring bean.

The bean should have:

```text
studentId   = 101
studentName = Imtiaz
course      = Java Full Stack
```

---

### Step 3 – Create BeanFactory Test

Create:

```text
BeanFactoryTest.java
```

Use a Spring `BeanFactory` to load the XML configuration and retrieve the `Student` bean.

### Expected Flow

```text
applicationContext.xml
        ↓
    BeanFactory
        ↓
    Student Bean
        ↓
      getBean()
        ↓
  Student Object
        ↓
 displayStudent()
```

### Expected Output

```text
========== STUDENT DETAILS ==========

Student ID   : 101
Student Name : Imtiaz
Course       : Java Full Stack
```

### Questions

1. What is `BeanFactory`?
2. Who creates the `Student` object?
3. What is the purpose of `getBean()`?
4. What is the role of `applicationContext.xml`?

---

# Exercise 2 – Using ApplicationContext

## Objective

Create and retrieve a `Student` bean using:

```text
ApplicationContext
```

and:

```text
ClassPathXmlApplicationContext
```

---

### Step 1 – Reuse Student Bean

Use the same:

```text
Student.java
```

and:

```text
applicationContext.xml
```

from Exercise 1.

---

### Step 2 – Create ApplicationContext Test

Create:

```text
ApplicationContextTest.java
```

Use:

```text
ApplicationContext
```

with:

```text
ClassPathXmlApplicationContext
```

to load:

```text
applicationContext.xml
```

---

### Expected Flow

```text
applicationContext.xml
        ↓
ClassPathXmlApplicationContext
        ↓
   ApplicationContext
        ↓
     Student Bean
        ↓
      getBean()
        ↓
  Student Object
```

### Expected Output

```text
========== STUDENT DETAILS ==========

Student ID   : 101
Student Name : Imtiaz
Course       : Java Full Stack
```

---

### Experiment

Change the bean values in:

```text
applicationContext.xml
```

For example:

```text
studentId   = 102
studentName = Rahul
course      = Spring Framework
```

Run the application again.

### Expected Output

```text
Student ID   : 102
Student Name : Rahul
Course       : Spring Framework
```

### Questions

1. What is `ApplicationContext`?
2. What is `ClassPathXmlApplicationContext`?
3. Where does `ClassPathXmlApplicationContext` look for the XML file?
4. What is the difference between `BeanFactory` and `ApplicationContext`?
5. Which one is generally preferred in normal Spring applications?

---

# Exercise 3 – Using FileSystemXmlApplicationContext

## Objective

Load Spring XML configuration from the **file system** using:

```text
FileSystemXmlApplicationContext
```

---

### Step 1 – Create External Configuration

Create a folder outside your project.

For example:

```text
C:\spring-config
```

Create:

```text
C:\spring-config\applicationContext.xml
```

Configure the `Student` bean inside this XML file.

Example values:

```text
studentId   = 103
studentName = Priya
course      = Spring Core
```

---

### Step 2 – Create Test Class

Create:

```text
FileSystemXmlApplicationContextTest.java
```

Use:

```text
FileSystemXmlApplicationContext
```

to load:

```text
C:\spring-config\applicationContext.xml
```

---

### Expected Flow

```text
C:\spring-config
        │
        ↓
applicationContext.xml
        │
        ↓
FileSystemXmlApplicationContext
        │
        ↓
Student Bean
        │
        ↓
    getBean()
        │
        ↓
Student Object
```

### Expected Output

```text
========== STUDENT DETAILS ==========

Student ID   : 103
Student Name : Priya
Course       : Spring Core
```

---

## Experiment

Move the XML file to another location.

For example:

```text
C:\spring-config-new\applicationContext.xml
```

Update the configuration path in your Java program and run it again.

Verify that the application successfully loads the bean.

---

# Final Comparison

After completing all three exercises, complete this table:

| Feature                | BeanFactory | ApplicationContext | FileSystemXmlApplicationContext |
| ---------------------- | ----------- | ------------------ | ------------------------------- |
| Type                   |             |                    |                                 |
| XML Configuration      |             |                    |                                 |
| Configuration Location |             |                    |                                 |
| Bean Retrieval         |             |                    |                                 |
| Main Purpose           |             |                    |                                 |

---

# Final Student Task

Draw the following three flows in your notebook:

### 1. BeanFactory

```text
XML
 ↓
BeanFactory
 ↓
Bean
 ↓
getBean()
```

### 2. ApplicationContext

```text
XML
 ↓
ClassPathXmlApplicationContext
 ↓
ApplicationContext
 ↓
Bean
 ↓
getBean()
```

### 3. FileSystemXmlApplicationContext

```text
File System
 ↓
XML
 ↓
FileSystemXmlApplicationContext
 ↓
Bean
 ↓
getBean()
```

---

# Submission Requirements

Submit the project with:

```text
✓ Student.java
✓ applicationContext.xml
✓ BeanFactoryTest.java
✓ ApplicationContextTest.java
✓ FileSystemXmlApplicationContextTest.java
✓ Console output screenshots
✓ Comparison table
```

## Important

```text
No Maven
No Gradle
No Spring Boot

✓ Eclipse or STS
✓ Normal Java Project
✓ Spring JAR files added manually
✓ Spring Core
✓ XML-based configuration
```
