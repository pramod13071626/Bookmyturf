# BookMyTurf

BookMyTurf is a comprehensive web application built with Spring Boot that allows users to book sports turfs and manage reservations. The platform supports user registration, authentication, and role-based access for both regular users and administrators. Admins can manage grounds, slots, coaches, and games, while users can view and book available slots based on their location.

## Features

### User Features
- **User Registration and Login**: Secure authentication with session management.
- **Dashboard**: Personalized dashboard showing available games and grounds based on user's city.
- **Ground Viewing**: Browse and view details of sports grounds.
- **Slot Booking**: Book available time slots for sports activities (implementation in progress).

### Admin Features
- **User Management**: View, edit, and delete user accounts.
- **Ground Management**: Add, edit, and view sports grounds with images and details.
- **Slot Management**: Create, update, and delete time slots for grounds, including pricing for weekdays and weekends.
- **Coach Management**: Manage coach profiles and assignments.
- **Game Management**: Add and manage different sports/games offered.
- **Dashboard**: Admin overview with access to all management tools.

### Additional Features
- **Email Notifications**: Integrated with Spring Boot Mail for sending notifications (configuration required).
- **Security**: Role-based access control using Spring Security.
- **Responsive UI**: Built with Thymeleaf templates and custom CSS for a user-friendly interface.
- **Database Integration**: Uses MySQL for data persistence with JPA.

## Tech Stack

- **Backend**: Java 17, Spring Boot 3.4.3
- **Frontend**: Thymeleaf, HTML, CSS, JavaScript
- **Database**: MySQL
- **Security**: Spring Security
- **Build Tool**: Maven
- **Other Libraries**: Lombok, Hibernate Validator, Jackson, Apache HttpClient

## Prerequisites

Before running the application, ensure you have the following installed:

- **Java 17** or higher
- **Maven** 3.6+
- **MySQL** 8.0+
- **Git** (for cloning the repository)

## Installation and Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/pramod13071626/Bookmyturf.git
   cd Bookmyturf/BookMyTurf-main
   ```

2. **Database Setup**:
   - Install and start MySQL.
   - Create a database named `sportsdb`.
   - Update the database credentials in `src/main/resources/application.properties`:
     ```
     spring.datasource.url=jdbc:mysql://localhost:3306/sportsdb
     spring.datasource.username=your_username
     spring.datasource.password=your_password
     ```

3. **Build the Application**:
   ```bash
   mvn clean install
   ```

4. **Run the Application**:
   ```bash
   mvn spring-boot:run
   ```
   The application will start on `http://localhost:1010`.

5. **Access the Application**:
   - User Login: `http://localhost:1010/login1`
   - Admin Login: Use admin credentials (default admin user needs to be created in the database).

## Usage

### For Users
1. Register a new account at `/register1`.
2. Log in with your credentials.
3. View available grounds and games on your dashboard.
4. Book slots (feature under development).

### For Admins
1. Log in with admin credentials.
2. Access the admin dashboard at `/admin/dashboard`.
3. Manage users, grounds, slots, coaches, and games through the respective sections.

## Project Structure

```
BookMyTurf-main/
├── src/
│   ├── main/
│   │   ├── java/com/example/sport/
│   │   │   ├── SportApplication.java          # Main application class
│   │   │   ├── config/                        # Security and other configurations
│   │   │   ├── controller/                    # REST and web controllers
│   │   │   ├── dto/                           # Data Transfer Objects
│   │   │   ├── model/                         # JPA entities
│   │   │   ├── repository/                    # JPA repositories
│   │   │   ├── service/                       # Business logic services
│   │   │   └── ...
│   │   └── resources/
│   │       ├── application.properties         # Application configuration
│   │       ├── static/                        # CSS, JS, images
│   │       └── templates/                     # Thymeleaf HTML templates
│   └── test/                                  # Unit tests
├── pom.xml                                    # Maven configuration
└── README.md                                  # This file
```

## API Endpoints

### Admin Endpoints
- `GET /admin/dashboard` - Admin dashboard
- `GET /admin/users` - List all users
- `POST /admin/user/{id}/delete` - Delete a user
- `GET /admin/slots` - Slot management page
- `POST /admin/slots/submit` - Create a new slot
- `PUT /admin/slots/update/{groundId}` - Update slots for a ground
- `DELETE /admin/slots/delete/{slotId}` - Delete a slot

### User Endpoints
- `GET /login1` - Login page
- `POST /login` - Authenticate user
- `GET /register1` - Registration page
- `POST /register` - Register new user
- `GET /user/dashboard` - User dashboard
- `GET /logout` - Logout

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature (`git checkout -b feature/AmazingFeature`).
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For questions or support, please contact the project maintainer at [othersites141@gmail.com].

---

*Note: This application is for educational purposes. Ensure to implement proper security measures before deploying to production.*
