## Setup and Usage

### required tools
- JDK (version >= 8)
- Maven
 
### Installation
Step1:- Clone the repository:
- git clone https://github.com/jyoti145/Xindus-Projectt/tree/master

Step2:- Navigate to dir XindusWishlistManagement:
- cd XindusWishlistManagement

Step3:- Build the project using Maven:
- mvn clean install

### Configuration
Step1:- Database Configuration:
- Open the src/main/resources/application.properties file.
- Configure your database connection settings:
  - spring.datasource.url=jdbc:mysql://localhost:3306/wishlistmanagement
  - spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
  - spring.datasource.username=root
  - spring.datasource.password=root
  
Step2:- Configuration of Spring Security :
- Customize JWT token expiration time and secret key, in the SecurityConfig.java file.

### Running the App
1. Run the app :
- mvn spring-boot:run  //default port is 8080


### API's
1. Sign Up:
-  use any of these (postman / insomnia / thunderclient).
- make a POST request to http://localhost:8080/auth/register in body params  containing user details:
  - {
    - "firstName": "example_firstname",
    - "lastName": "example_lastname",
    - "email": "example_email",
    - "password": "example_password"
  - }

2. Login:
- make a POST request to http://localhost:8080/auth/login in body params containing user credentials:
  - {
    - "email": "example_email",
    - "password": "example_password"
   - }

#### Note: Save the JWT token received in the response.

3. Accessing Other APIs:
- To access other APIs requiring authentication, include the JWT token in the Authorization header of your requests:
   - In Postman, set the Authorization type to "Bearer Token" and paste the JWT token obtained during login.
   - Use the following endpoints for other API functionalities:
     - Wishlist Management: http://localhost:8080/api/wishlists
     - Products: http://localhost:8080/api/products
