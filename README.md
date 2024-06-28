<h1>SOLO APP</h1>
<h3>About the application</h3>
<p>SOLO is a social network focused on connecting people with similar interests in physical and social activities. Imagine being in a new city and wanting, for example, to find company for beach volleyball or exploring trails. With SOLO, you can easily discover and participate in these activities, created by other users of the platform.</p>

<h3>Key Features:</h3>
    <ul>
        <li><strong>Discover Activities:</strong> Explore a variety of activities such as sports, trekking, gym, beach, and trips, all organized based on location.</li>
        <li><strong>Create Your Activities:</strong> Be the organizer! Create events for other users to join you in your adventures.</li>
        <li><strong>Connect with New Friends:</strong> Beyond participating in activities, you can add people you've met and stay in touch beyond the app.</li>
    </ul>

<h1>Proposed Model: Layered Architecture</h1>
<p>This application was build under a typical three-layered architecture: Presentation, Service, and Data Access layers.</p>

![Texto Alternativo](https://github.com/EdnardoBarr/solo-app/blob/master/layered.jpg)

<h4>Presentation Layer:</h4>
<ul>
  <li>This layer handles the interaction with the user, receives HTTP requests, and sends responses.</li>
  <li>Controllers in this layer are annotated with @RestController.</li>
  <li>The controllers interact with the Service layer to process requests and obtain results.</li>
  <li>DTOs (Data Transfer Objects) were used to transfer data between the Presentation and Service layers.</li>
</ul>

<h4>Service Layer:</h4>
<ul>
  <li>The Service layer contains business logic and orchestrates the flow of data between the Presentation and Data Access layers.</li>
  <li>Service classes are annotated with @Service.</li>
  <li>It uses the Data Access layer to retrieve or manipulate data.</li>
</ul>

<h4>Data Access Layer:</h4>
<ul>
  <li>The Data Access layer is responsible for interacting with the database.</li>
  <li>It includes repository interfaces annotated with @Repository.</li>
</ul>

<h1>Database Diagram</h1>
<p>The tables in the database of the application are as in the figure below.
  
![Texto Alternativo](https://github.com/EdnardoBarr/solo-app/blob/master/relations-database.png)

<h1>Authentication</h1>
<p>Authentication is required for users to access the application.</p>
<ul>
  <li>Spring Security</li>
  <li>JWT</li>
  <li>Bcrypt</li>
</ul>

<h1>Testability</h1>
<p>It was created Unit Tests for the Service Layer</p>
<ul>
  <li>JUnit5</li>
  <li>Mockito</li>
  <li>AssertJ</li>
</ul>

<h1>Documentation</h1>
<p>The documentation of the api was built with Swagger</p>
<ul>
  <li>http://localhost/api/v1/api-docs/swagger-ui/index.html</li>
</ul>

<h1>Running the Project</h1>
<p>The project features a fully configured stack in docker-compose. Providing all the necessary infrastructure for developers.</p>

<h3>Stack</h3>
<ul>
  <li>Java 17+</li>
  <li>Maven 3+</li>
  <li>Spring Boot</li>
  <li>PostgreSQL</li>
  <li>React</li>
  <li>Styled Components</li>
  <li>Docker</li>
  <li>docker-compose</li>
</ul>

<h3>Starting the service</h3>
<p><strong>cmd</strong> in the parent folder where all the projects of the application are located and run the application</p>

![Texto Alternativo](https://github.com/EdnardoBarr/solo-app/blob/master/directory.png)

```
docker-compose up
```

<h1>Requests Diagram</h1>
<p>Once the application is deployed, the incoming requests will proceed in a flow as in the diagram below.</p>
<ul>
    <li>The request from the client will be met in Nginx and forwarded to the front-end port.</li>
    <li>The requests to be made by the front-end will be directed to the back-end port by Nginx again.</li>
</ul>

![Texto Alternativo](https://github.com/EdnardoBarr/solo-app/blob/master/requests-diagram.png)

