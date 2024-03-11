# Microservices Example with Clean Architecture and Spring

This project aims to study and implement the Clean Architecture pattern using Spring and RabbitMQ as a means of communication. It consists of two applications:

1. **Student Registration**: A simple application that allows users to register as students.
2. **Email Service**: A service that listens to a RabbitMQ queue and sends an email whenever a new student is registered.

The project also includes a Docker Compose file to easily start all the required components.

## Technologies Used

- **Spring Boot**: Java framework for creating microservices.
- **Clean Architecture**: Software design pattern that promotes separation of concerns.
- **RabbitMQ**: Message broker for asynchronous communication between applications.
- **Docker**: Platform for building, shipping, and running applications in containers.

## Getting Started

To run the project, follow these steps:

1. Install Docker and Docker Compose.
2. Clone the repository:
```
git clone https://github.com/ikk1/microservices.git
```
3. Go to the project directory:
```
cd microservices
```
4. Build and start the applications with Docker Compose:
```
docker-compose up
```

### Registering a New Student
Send a POST request to `http://localhost:8080/students` with the following request body format:
```json
{
  "name": "Student Name",
  "email": "email@example.com",
  "address": "Student Address",
  "course": "MATH"
}
```
Replace the values as needed. The course field should be one of the following options: MATH, SCIENCE, HISTORY, or ENGLISH, indicating the student's course.

### Viewing the List of Students
Make a GET request to http://localhost:8080/students to retrieve a list of all registered students.

It will return a list of students in the following format:
```json
[
  {
    "id": 1,
    "name": "Student Name",
    "email": "email@example.com",
    "address": "Student Address",
    "course": "MATH"
  },
  {
    "id": 2,
    "name": "Another Student Name",
    "email": "anotheremail@example.com",
    "address": "Another Student Address",
    "course": "SCIENCE"
  },
  ...
]
```
Note: The Email Service application is not accessible via a web browser. It runs in the background and listens to the RabbitMQ queue. The email is sent to the address specified in student registration.

## Contributing
If you find this project useful, feel free to contribute by:

- Reporting bugs or suggesting improvements.
- Submitting pull requests with your changes.

## License
This project is licensed under the MIT License.

## References
- Clean Architecture: [Uncle Bob's Blog](https://blog.cleancoder.com/)
- Spring Boot: [Official Website](https://spring.io/projects/spring-boot)
- RabbitMQ: [Official Website](https://www.rabbitmq.com/)
- Docker: [Official Website](https://www.docker.com/)

## Additional Information
This is a basic example of microservices using Clean Architecture and Spring. For more information on these topics, please refer to the resources mentioned above.

## Contact
If you have any questions or feedback, please feel free to contact me at deus_junior1@yahoo.com.br.