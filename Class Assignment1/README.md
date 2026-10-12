# Class Work – Assignment 1: 5-Page Website using Spring Boot

A clean, responsive 5-page web application built with **Spring Boot** and **Spring Web**, serving static HTML and CSS without requiring template engines (Thymeleaf), ORM (JPA), or databases.

---

## 📌 Project Overview

This project satisfies the requirements for **Class Work – Assignment 1**. It demonstrates how Spring Boot serves static web content natively from `src/main/resources/static/` while providing clean page-to-page navigation, semantic HTML5 structure, and modern CSS styling.

### Technologies Used
- **Java 21+**
- **Spring Boot 3.3.4** (`spring-boot-starter-web`)
- **Maven** (and Maven Wrapper `mvnw`)
- **HTML5 & CSS3** (Vanilla CSS with Google Font *Plus Jakarta Sans*)
- **Embedded Apache Tomcat** (port `8080`)

---

## 🏗️ How This Project Was Built

1. **Spring Web Dependency**:
   - Initialized `pom.xml` with `org.springframework.boot:spring-boot-starter-web`.
   - The embedded Tomcat server automatically routes HTTP requests to static resources located in `src/main/resources/static/`.

2. **Application Entry Point**:
   - Built [`SpringBootWebApplication.java`](src/main/java/com/example/SpringBootWebApplication.java) annotated with `@SpringBootApplication` to bootstrap the application:
     ```java
     package com.example;

     import org.springframework.boot.SpringApplication;
     import org.springframework.boot.autoconfigure.SpringBootApplication;

     @SpringBootApplication
     public class SpringBootWebApplication {
         public static void main(String[] args) {
             SpringApplication.run(SpringBootWebApplication.class, args);
         }
     }
     ```

3. **No Thymeleaf / Database Needed**:
   - Because all pages are static content, Spring Boot maps requests to `static/` by default:
     - Requesting `http://localhost:8080/` loads `index.html`.
     - Requesting `http://localhost:8080/about.html` loads `about.html`.
     - Requesting `http://localhost:8080/product.html` loads `product.html`.
     - Requesting `http://localhost:8080/features.html` loads `features.html`.
     - Requesting `http://localhost:8080/contact.html` loads `contact.html`.
     - Requesting `http://localhost:8080/css/style.css` serves the stylesheet.

4. **UI & Styling Design**:
   - Implemented a unified layout in `css/style.css` featuring a sticky frosted glass navigation bar, active tab indicators, responsive flex/grid layouts, custom badge components, and interactive hover effects.

---

## 📂 Project Structure

```
Class Assignment1/
├── src/
│   └── main/
│       ├── java/
│       │   └── com/
│       │       └── example/
│       │           └── SpringBootWebApplication.java
│       └── resources/
│           └── static/
│               ├── index.html        # Home Page
│               ├── about.html        # Project Creator Page
│               ├── product.html      # Product Page
│               ├── features.html     # Features Page
│               ├── contact.html      # Contact Page
│               └── css/
│                   └── style.css     # Shared Stylesheet
├── pom.xml                           # Maven Configuration
├── mvnw                              # Maven Wrapper script (Linux/macOS)
├── mvnw.cmd                          # Maven Wrapper script (Windows)
├── .gitignore                        # Git ignore file
└── README.md                         # Documentation
```

---

## 🌐 The 5 Required Pages

| # | Page Name | URL | Contents Included |
|---|---|---|---|
| 1 | **Home Page** | `http://localhost:8080/` | Project title (Student Management System), welcome message, Spring Boot intro, top navbar |
| 2 | **Project Creator** | `http://localhost:8080/about.html` | Creator name (Rahul Kumar), Course, College, Year, Skills badges, bio |
| 3 | **Product Page** | `http://localhost:8080/product.html` | Product name, description, purpose, technologies used, target users |
| 4 | **Features Page** | `http://localhost:8080/features.html` | Checklist of features: Add, View, Update, Delete, Search Student, and Reports |
| 5 | **Contact Page** | `http://localhost:8080/contact.html` | Contact card with creator name, email, phone, college, and location |

---

## 🚀 How to Run and Use

### Prerequisites
- **Java Development Kit (JDK 17 or 21+)** installed. Check with:
  ```bash
  java -version
  ```

### Step 1: Clone the Repository
```bash
git clone https://github.com/avyuktcodes/Java-Full-Stack-Development.git
cd "Java-Full-Stack-Development/Class Assignment1"
```

### Step 2: Run the Application
You can run directly with Maven Wrapper (no separate Maven installation needed):

- **On macOS / Linux:**
  ```bash
  ./mvnw spring-boot:run
  ```

- **On Windows:**
  ```cmd
  mvnw.cmd spring-boot:run
  ```

*(Or if you have Maven installed, simply run `mvn spring-boot:run`)*

### Step 3: Open in Browser
Once you see `Started SpringBootWebApplication in ... seconds` in your terminal:
- Open your browser and navigate to:
  👉 **[http://localhost:8080](http://localhost:8080)**

You can navigate across all 5 pages using the top navigation bar or direct URLs:
- `http://localhost:8080/`
- `http://localhost:8080/about.html`
- `http://localhost:8080/product.html`
- `http://localhost:8080/features.html`
- `http://localhost:8080/contact.html`

### Step 4: Packaging as an Executable JAR (Optional)
To build a standalone executable jar:
```bash
./mvnw clean package -DskipTests
```
Then run the jar anytime without Maven:
```bash
java -jar target/spring-boot-web-project-0.0.1-SNAPSHOT.jar
```
