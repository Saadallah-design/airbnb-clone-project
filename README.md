# airbnb-clone-project
Project of Airbnb Clone in the ALX ProDev Backend program.

## Overview of the Project
The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security. This project enables learners to understand complex architectures, workflows, and collaborative team dynamics while building a scalable web application.

## Project Goals
- Master collaborative team workflows using GitHub.
- Deepen their understanding of backend architecture and database design principles.
- Implement advanced security measures for API development.
- Gain proficiency in designing and managing CI/CD pipelines for efficient deployment.
- Strengthen their ability to document and plan complex software projects effectively.
- Develop an understanding of integrating technologies like Django, MySQL, and GraphQL in a unified ecosystem.

## Technology Stack and Requirements
- Possess prior experience with backend frameworks like Django and database systems such as MySQL.
- Understand software development lifecycle practices, including security, CI/CD, and database design.
- Be comfortable with modern tools such as Docker, GitHub Actions, or similar CI/CD platforms.

1. Django
    - a high-level, open source web framework for building RESTful APIs.
    - ***Django is written in Python***. It provides a set of tools and features right out of the box without the need to install separate libs = batteries-included approach.
    - ***Built-in Admin Panel***: can automatically generate a secure professional looking admin interface for managing data.
    - ***ORM (Object-Relational Mapper)***: Django's ORM allows you to interact with your database using Python code instead of raw SQL
    - ***URL Routing***: Django uses a powerful URL dispatcher that maps URLs to views (Python functions or classes) that handle web requests.
    - ***Security***: It provides built-in protections against common web vulnerabilities like Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), and SQL injection.
    - ***MTV Architecture***: (Model-View-Template) architectural pattern.

2. Django REST Framework
    - **Definition**: Django REST Framework (DRF) is a powerful and flexible toolkit for building Web APIs using the Django web framework. 
    - **Serialization**: DRF provides serializers that allow you to convert complex data types, like Django model instances, into native Python data types that can be easily rendered into JSON, XML, or other formats. This is the core of an API, as it allows you to send data over the internet.
    - **Authentication and Permissions**: It includes built-in classes for handling various authentication schemes (e.g., Token-based, OAuth2) and permission policies, which let you control who can access your API's resources.
    - **Views and ViewSets**: DRF offers a variety of views, from simple API views to complex ModelViewSet classes. These views automatically handle common operations like creating, retrieving, updating, and deleting objects (CRUD).
    - **URL Routing**: It provides an easy-to-use API router that automatically handles URL patterns for your viewsets, reducing the amount of manual URL configuration you need to do.
    - **Browsable API**: One of DRF's most popular features is its browsable API. This is a web interface that makes your API's endpoints browsable in a web browser, which is incredibly useful for developers to interact with and test the API without needing separate tools.

3. MySQL
    - **Definition**: open-source relational database management system (RDBMS). It's used to store and manage structured data for a wide range of applications, from small websites to large enterprise systems. MySQL organizes data into tables, which are made up of rows and columns, similar to a spreadsheet.
    - **Relational**: it is a relational database, stores data in tables and uses relationships btw those tables to connect infos.
    - **SQL**: Structured Query Language, allows u to create, read, update and delete (CRUD) data. 
    - **Client-Server Architecture**: MySQL operates as a client-server system. A server process (the MySQL database) handles all data management, and clients (like your applications or the terminal) connect to the server to perform queries.
    - **Known for being**: Open source, speed and ability to handle large num of transactions (high traffic), reliability and widely adopted. 

4. PostgreSQL
    - **Definition**: often called "Postgres," is a powerful, open-source relational database management system (RDBMS). It is known for its strong reputation for extensibility, data integrity, and adherence to SQL standards. 
    - **Robustness and Reliability**: PostgreSQL is built to be highly reliable and resistant to data corruption. It has advanced features like write-ahead logging (WAL), which ensures that database changes are persistent and can be recovered in the event of a crash.
    - **Extensibility**: PostgreSQL is not just a database; it's also a platform. You can extend its functionality with custom data types, functions, operators, and languages (like Python or R). 
    - **Concurrency Control**: It uses a system called Multi-Version Concurrency Control (MVCC). This allows multiple users to read and write to the database at the same time without "locking" each other out, which significantly improves performance and responsiveness.
    - **Data Types**: PostgreSQL supports a vast array of data types, including not just standard ones like integers and strings, but also advanced ones like JSON, XML, and geometric data, which makes it suitable for modern applications.

5. GraphQL
    - **Definition**: GraphQL is a query language for your API and a server-side runtime for executing those queries. It was developed by Facebook and is an alternative to traditional REST APIs. _Unlike_ REST, which typically uses multiple endpoints to fetch data, GraphQL lets clients request exactly the data they need from a single endpoint.
    - Benefit of this approach of "Ask for what you need, get exactly what you need" solve 2 PROBLEMS:
        - ***Over-fetching***: When a REST endpoint returns more data than an application needs, leading to wasted bandwidth and slower performance.
        - ***Under-fetching***: When a REST endpoint doesn't return enough data, forcing the client to make multiple requests to different endpoints to gather all the necessary information.

6. Celery:  For handling asynchronous tasks such as sending notifications or processing payments.

    - **Definition**: A task queue that handles asynchronous or scheduled tasks. It's used in web development to run time-consuming operations in the background, so your application's main process remains fast and responsive to users.

    - **Core Components**:
        - ***Celery Client***: This is your application code (e.g., a Django view) that sends a task to the queue. You "call" a task, and it's sent to the broker to be executed later.
        - ***Broker***: A message broker (like Redis or RabbitMQ) acts as a middleman. It holds the tasks in a queue until a worker is available to process them.
        - ***Celery Worker***: This is a separate process that constantly monitors the broker for new tasks. When it finds a task, it executes the code and can optionally send the result back to a result backend.
        - ***Result Backend***: A database or message queue (like Redis or a database) used to store the results of the completed tasks, which the client can later retrieve.

    - **Common Use Cases**:
        - ***Sending Emails***: Instead of making a user wait for an email to be sent after they sign up, you can offload the email sending to a Celery task.
        - ***Image Processing***: Resizing or watermarking images can be time-consuming. Celery can handle this in the background, improving the user experience.
        - ***Data Imports***: Importing large datasets can take minutes or even hours. Celery can run the import task and notify the user when it's complete.
        - ***Scheduled Tasks***: Celery can be configured to run tasks at specific times, similar to a cron job. This is useful for things like generating daily reports.

7. Redis: Used for caching and session management
    - **Definition**: open-source, in-memory data store that can be used as a database, cache, or message broker. Unlike traditional databases that store data on a hard disk, Redis holds data in RAM, which allows for incredibly fast read and write operations. Its name stands for Remote Dictionary Server.
    - **In-Memory Data Store**: The primary feature of Redis is its speed. By storing data in memory, it can retrieve information with sub-millisecond latency. This makes it ideal for real-time applications, such as leaderboards, real-time analytics, and session caching.
    - **Data Structures**: Redis is more than just a key-value store. It supports a wide variety of data structures, including strings, hashes, lists, sets, and sorted sets. This flexibility allows developers to model complex data and solve a wide range of problems directly within Redis.
    - **Caching**: This is one of the most common uses for Redis. Applications can use Redis to cache frequently accessed data, reducing the load on a primary database and speeding up response times.
    - **Message Broker**: Redis can act as a message broker in a publish-subscribe (pub/sub) pattern. This allows different parts of an application to communicate with each other asynchronously, which is a key component of task queues like Celery.
    -**Persistence**: Although Redis is an in-memory database, it offers persistence options to prevent data loss in case of a crash. It can periodically save the data to a hard disk, creating a snapshot that can be reloaded when the system restarts.

8. Docker
    - **Definition**: Docker is a platform that uses OS-level virtualization to deliver software in packages called containers. A container is an isolated, lightweight, and executable package that includes everything needed to run a piece of software, including the code, a runtime, libraries, and system tools.
    - **Utility**: Packages an application and all its dependencies into a single container making sure it will run consistently on any machine with docked installed regardless of the underlying environment.
    - **Key Features**: 
        - Portability: Containers can be moved between different environments (development, testing, production) without any changes, ensuring consistency.
        - Isolation:  Each container runs in an isolated environment, preventing conflicts between applications or with the host system.
        - Efficiency: more lightweight and start faster than traditional virtual machines because they share the host's operating system kernel.
        - Scalabality: Docker makes it easy to scale applications. You can quickly and consistently spin up multiple instances of the same container to handle increased traffic.

9. **CI/CD pipelines**: are a set of automated practices that help developers deliver software faster and more reliably by building, testing, and deploying code changes. It's a fundamental part of modern DevOps and Agile methodologies. The acronym stands for Continuous Integration, Continuous Delivery, and Continuous Deployment.


## Team Roles

### According to ALX team role
1. Backend Developer: Responsible for implementing API endpoints, database schemas, and business logic.
2. Database Administrator: Manages database design, indexing, and optimizations.
3. DevOps Engineer: Handles deployment, monitoring, and scaling of the backend services.
4. QA Engineer: Ensures the backend functionalities are thoroughly tested and meet quality standards.


### According to ITRexGroup blog:
1. Business Analyst (BA)
    - Understands customer's business processes
    - Translates customer business needs into requirements

2. Product Owner (PO)
    - Holds responsibility for a product vision and evolution
    - Makes sure the final product meets customer requirements

3. Project Manager
    - Makes sure a product or its part is delivered on time and within budget.
    - Manages and motivates the software development team

4. UI/UX designer
    - Transforms a product vision into user-friendly designs
    - Creates user journeys for the best user experience and highest conversion rates

5. Software architect
    - Designs a high-level software architecture
    - Selects appropriate tools and platforms to implement the product vision 
    - Sets up code quality standards and performs code reviews

6. Software developer
    - Engineers and stabilizes the product
    - Solves any technical problems emerging during the development lifecycle

7. Quality assurance (QA) engineer
    - Makes sure an application performs according to requirements
    - Spots functional and non-functional defects

8. Test automation engineer
    - Designs a test automation ecosystem
    - Writes and maintains test scripts for automated testing

9. DevOps engineer
    - Facilitates cooperation between development and operations teams
    - Builds continuous integration and continuous delivery (CI/CD) pipelines for faster delivery

## Database Design

1. Users
    - a user can list many properties.
    - can book multiple properties.
    - can pay with different payment methods
    - can leave multiple review for different bookings and properties.

2. Properties
    - A property can be listed by more than one user
    - a property can be paid for with different payment methods
3. Bookings
    - each booking has a unique current user
    - bookings have a start and end date
    - bookings have different payment methods
4. Payments
    - each user has their own payment method
    - each user can have multiple payment methods
    - use can pay for multiple bookings
5. Reviews
    - reviews can be about a single and multiple properties/bookings
    - user with different reviews for different bookings
    - user with different reviews for same booking

## Feature Breakdown

1. User management: 
    - Includes registering new users. user authentication and managing user profiles.
    - ***Endpoints***: /users/, /users/{user_id}
2. Property management:
    - Creating, updating, retrieving and deleting property listings.
    - /bookings/, /booking/{booking_id}
3. API Documentation:
    - Backend APIs ensuring clarity and ease of integration, Django REST for comprehensive RESTful API for handling CRUD ops on user and property data.
4. Booking system:
    - Make, update, and manage bookings, including check-in and check-out details.
5. Payment processing:
    - Handle payment transactions related to bookings.
    - ***Endpoints***: /payments/
6. Review system:
    - Post and manage reviews for properties.
    - ***Endpoints***: /reviews/, /reviews/{review_id}/
7. Database optimization:
    - ***Indexing***: Implement indexes for fast retrieval of frequently accessed data. 
    - ***Caching***: Use caching strategies to reduce database load and improve performance.


