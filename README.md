# greenStich_Assignement


<h3>This project is a backend implementation of a login and signup REST API with security and JWT tokens. It is built using Java, Spring Boot, and utilizes H2 database for data storage. The API endpoints provided below demonstrate the functionality of the application.</h3>

<h2>Installation and Setup</h2>

<p>### Prerequisites
- Java Development Kit (JDK) 8 or later
- Maven
- Postman (for testing the API)
</p>

<h2>API Endpoints</h2>
<ul>
  <li>Method: POST</li>
  <li>Path: http://localhost:8081/app/signup</li>
  <li>Description: Register a new user.</li>
  <li>Request Body: User data in the JSON format (e.g., name, email, password).</li>

<p>
  {
  "fullName": "Nitish Kumar",
  "password": "nitish@123",
  "email": "nitishkumar09598@gmail.com"
}
</p>
<li>Response:</li>
<p>
  {
    "id": 121,
    "fullName": "Nitish kumar",
    "password": "$2a$10$KVzpEHKFpX2ephA7RXLgqumnZKFy3bT8wdJMW3tYH2yqUJcpZPGSG",
    "email": "nitishkumar09598@gmail.com",
    "role": "ROLE_USER"
}
</p>
</ul>


<h2>Welcome Endpoint (Requires Authentication)</h2>
<ul>
  <li>Method: GET</li>
  <li>Path: http://localhost:8081/logged-in/user</li>
  <li>Description: A protected endpoint that requires authentication to access.</li>
  <li>Authentication: Bearer Token</li>
  <li>Request Header
    <ul>
      <li>Authorization: Bearer</li>
    </ul>
  </li>
  <li>Response: A welcome message string.</li>
  <li>Example
  <ul>
      <li>Bearer Token:       eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJTaGltYmh1Iiwic3ViIjoiSldUIFRva2VuIiwidXNlcm5hbWUiOiJza0BnbWFpbC5jb20iLCJyb2xlIjoiUk9MRV9VU0VSIiwiaWF0IjoxNjg1Njc3Mzg3LCJleHAiOjE2ODU3MDczODd9.VwM2IGD1fABjEcnNoMb4uIyBnYe3_BmZGx33dElaD-E
      </li>
    <li>Response:Hello from GreenStitch”
</li>
    </ul>
  </li>
</ul>
<h2>Tech Stack</h2>
<ul>
  <li>Java</li>
  <li>Spring Boot</li>
  <li>H2 Database</li>
  <li>Spring Security</li>
  <li>JWT Token</li>
  <li>Lombok</li>
  <li>Maven</li>
</ul>
<h2>Validation Rules</h2>

<p>The following validation rules are applied to the user entity:</p>

<ul>
  <li>Full Name
  <ul>
    <li>Minimum length: 3 characters</li>
    <li>Maximum length: 20 characters</li>
  </ul>
    <li>Password</li>
    <ul>
      <li>At least 8 characters</li>
      <li>Contains at least one digit</li>
      <li>Contains at least one lowercase letter</li>
      <li>Contains at least one uppercase letter</li>
      <li>Contains at least one special character</li>
    </ul>
  <li>Email
     <ul>
    <li>Valid email format</li> 
  </ul>
  </li>
</ul>
<h2>Development</h2>

<p>The project can be imported and run using an IDE like Eclipse</p>

<h2>Test API</h2>
<p>You can use Postman to test the API endpoints.</p>

<h1>H2 Database Configuration
</h1>
<hr>
<p>The project uses the H2 in-memory database by default.</p>

<p>The application is configured to use the H2 database. The configuration can be found in the application.properties file:</p>
<p># Server Port Configuration
server.port=8081

# H2 Database Configuration
spring.datasource.url=jdbc:h2:mem:testdb<br>
spring.datasource.driverClassName=org.h2.Driver<br>
spring.datasource.username=sa<br>
spring.datasource.password=<br>
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect<br>
spring.h2.console.enabled=true<br>
spring.h2.console.path=/h2-console<br>
</p>
