## Login and Registration Example Project with Spring Security
If you're already a student of Learn Spring Security, you can get started diving deeper into registration with Module 2 </br>
If you're not yet a student, you can get access to the course here: https://bit.ly/github-lss
</br></br></br>


### Relevant Articles: 
- [Spring Security Registration Tutorial](https://www.baeldung.com/spring-security-registration)
- [The Registration Process With Spring Security](https://www.baeldung.com/registration-with-spring-mvc-and-spring-security)
- [Registration – Activate a New Account by Email](https://www.baeldung.com/registration-verify-user-by-email)
- [Registration with Spring Security – Password Encoding](https://www.baeldung.com/spring-security-registration-password-encoding-bcrypt)
- [Spring Security – Roles and Privileges](https://www.baeldung.com/role-and-privilege-for-spring-security-registration)
- [Prevent Brute Force Authentication Attempts with Spring Security](https://www.baeldung.com/spring-security-block-brute-force-authentication-attempts)
- [Spring Security – Reset Your Password](https://www.baeldung.com/spring-security-registration-i-forgot-my-password)
- [Spring Security Registration – Resend Verification Email](https://www.baeldung.com/spring-security-registration-verification-email)
- [The Registration API becomes RESTful](https://www.baeldung.com/registration-restful-api)
- [Registration – Password Strength and Rules](https://www.baeldung.com/registration-password-strength-and-rules)
- [Updating your Password](https://www.baeldung.com/updating-your-password)
- [Two Factor Auth with Spring Security](https://www.baeldung.com/spring-security-two-factor-authentication-with-soft-token)
- [Registration with Spring – Integrate reCAPTCHA](https://www.baeldung.com/spring-security-registration-captcha)
- [Purging Expired Tokens Generated By The Registration](https://www.baeldung.com/registration-token-cleanup)
- [Custom Login Page for Returning User](https://www.baeldung.com/custom-login-page-for-returning-user)
- [Allow Authentication from Accepted Locations Only with Spring Security](https://www.baeldung.com/spring-security-restrict-authentication-by-geography)
- [Spring Security – Auto Login User After Registration](https://www.baeldung.com/spring-security-auto-login-user-after-registration)
- [Keep Track of Logged in Users With Spring Security](https://www.baeldung.com/spring-security-track-logged-in-users)
- [Login For a Spring Web App – Error Handling and Localization](https://www.baeldung.com/spring-security-login-error-handling-localization)
- [Notify User of Login From New Device or Location](https://www.baeldung.com/spring-security-login-new-device-location)
- [Preventing Username Enumeration Attacks with Spring Security](https://www.baeldung.com/spring-security-enumeration-attacks)


### Build and Deploy the Project
```
mvn clean install
```

This is a Spring Boot project, so you can deploy it by simply using the main class: `Application.java`

Once deployed, you can access the app at: 

https://localhost:8081


### Set up MySQL
By default, the project is configured to use the embedded H2 database.
If you want to use the MySQL instead, you need to uncomment relevant section in the [application.properties](src/main/resources/application.properties) and create the db user as shown below:
```
mysql -u root -p 
> CREATE USER 'tutorialuser'@'localhost' IDENTIFIED BY 'tutorialmy5ql';
> GRANT ALL PRIVILEGES ON *.* TO 'tutorialuser'@'localhost';
> FLUSH PRIVILEGES;
```


### Set up Email

You need to configure the email by providing your own username and password in application.properties
You also need to use your own host, you can use Amazon or Google for example.

### AuthenticationSuccessHandler configuration for Custom Login Page article
If you want to activate the configuration for the article [Custom Login Page for Returning User](https://www.baeldung.com/custom-login-page-for-returning-user), then you need to comment the @Component("myAuthenticationSuccessHandler") annotation in the MySimpleUrlAuthenticationSuccessHandler and uncomment the same in MyCustomLoginAuthenticationSuccessHandler.

### Feature toggle for Geo IP Lib
The geolocation checks do not work for the IP addresses 127.0.0.1 and 0.0.0.0, 
which can be a problem when running the application locally or in a test environment.
To enable/disable the check on the geolocation, set the property `geo.ip.lib.enabled` to true/false; this is false by default.
