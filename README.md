# react-spring-boot-boilerplate

# 🔗 URL Shortener App

A full-stack URL shortener built with **React** for the frontend and **Java Spring Boot** for the backend. Users can submit long URLs, receive a shortened link, and access the original URL using that short code — with built-in expiry and validation.

Spring-boot code is inside Backend directory you can start the app using

./mvnw <br>
server will run at http://localhost:8080/

React JS code is inside client directory you can start the app using

npm start <br>
app will run at http://localhost:3000/



---

## ⚙️ Features

- 📥 Submit any valid URL and get a short redirect link.
- ⏱ Short URLs expire after **5 minutes**.
- 🧭 Visiting a short URL redirects to the original, or shows:
  - ⚠️ "URL expired" message
  - ❌ "URL does not exist" message
- 🧹 Duplicate URLs are handled — returning the same short code.
- 🌐 Responsive frontend UI using React and Axios.
- 💾 In-memory H2 database for backend storage.

---

## 🛠 Tech Stack

| Layer       | Technology     |
|-------------|----------------|
| Frontend    | React + Axios |
| Backend     | Java + Spring Boot + JPA     |
| Database    | H2 (in-memory)               |

---

## 🚀 Getting Started

### 🔌 Backend Setup (Spring Boot)

1. Clone repo and open in IDE
2. In `application.properties`:
    ```properties
    spring.application.name=backend
    spring.datasource.url=jdbc:h2:mem:testdb
    spring.datasource.driverClassName=org.h2.Driver
    spring.datasource.username=sa
    spring.datasource.password=
    spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
    spring.h2.console.enabled=true
    ```
3. Run the application (`UrlShortenerApplication.java`)

### 🌐 Frontend Setup (React)

1. Navigate to `url-shortener-frontend` folder
2. Install dependencies:
    ```bash
    npm install
    ```
3. Start dev server:
    ```bash
    npm start
    ```
4. React app runs at `http://localhost:3000`

---

## 📦 API Endpoints

| Method | Endpoint                    | Description                           |
|--------|-----------------------------|---------------------------------------|
| POST   | `/shorten`                  | Accepts raw URL in body, returns short URL |
| GET    | `/{shortCode}`              | Redirects to original URL (if valid)  |
|        |                             | Returns if invalid/expired |

---

## 🧪 Testing

- ✔ Try generating a short URL
- ✔ click the link before 5 mins → it works!
- ❌ After 5 mins → shows “expired” in alert box.
- ❌ Try updating the code in D.B and try generating the url and click Random code → shows “not found” in alert box.

---

