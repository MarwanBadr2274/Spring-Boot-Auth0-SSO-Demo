
# Spring-Boot-Auth0-SSO-Demo

This repository offers a demonstration for the Single Sign-On (SSO) functionality supported by Auth0 for Spring Boot web applications. The repository contains a Spring Boot Application that represents an OAuth2/OIDC client.




## Prerequisites

 - Auth0 developer account: https://auth0.com/signup?place=header&type=button&text=sign%20up
 - Java 17
 - Spring Boot 3.*

## No-code Instructions

 1. **Create Two Web Applications in Auth0 Applications Tab:**
-   Log in to your Auth0 dashboard.
-   Navigate to the "Applications" section.
-   Click on the "Create Application" button.
-   Choose "Regular Web Applications" for both applications and choose Java Spring Boot.

2. **Save the Client ID, Client Secret, and Domain of Each Application:**
- After creating each application, note down the Client ID, Client Secret, and Domain. You'll need these credentials for integrating Auth0 with your web applications.

3. **Add Callback URLs and Logout URLs for Each Application:**
-   For each application, configure the "Allowed Callback URLs". and "Allowed Logout URLs" in the application settings as follows: 
callback URLs: http://localhost:{port}/login/oauth2/code/auth0 
http://localhost:{port}/login/oauth2/code/okta
logout URLs: http://localhost:{port}/
-   These URLs define where Auth0 should redirect the user after authentication and after logging out, respectively.

4. **Adjust Auth0 Advanced Settings for Seamless SSO:**
-   In the Auth0 dashboard, navigate to the "Settings -> Advanced" section.
-   Under the "Advanced," turn on "Enable Seamless SSO" option to allow users to authenticate seamlessly across different applications without re-entering credentials.

5. **Add User Credentials to your Tenant:**
-   In the Auth0 dashboard, navigate to the "User Management -> Users" section.
-   Under the "Users," create a new user with username-password-authentication and save it.


## Code Instructions

 1. **Download or Clone the Repository:**

-   Download or clone the repository containing the web application code to your local machine.

2. **Create a Second Copy of the Downloaded Application:**
- Duplicate the downloaded application folder to create a second copy of the application.

3. **Adjust Properties:**
-   In each `application.properties` file of the two applications, adjust the Client ID, Client Secret, and Domain obtained from one of your Auth0 applications.
- Adjust the ports to match the ports added in your Auth0 settings for the callback and logout URLs for each application.


## Running and Testing the Web Applications

 1. **Run Both Applications from Your Favorite IDE**

-   After adjusting the `application.properties` fil in each application to match your Auth0 configurations, run both applications.

2. **Test SSO:**
- Visit http://localhost:{app-1-port}/profile
- Enter the credentials of the user you added to Auth0 and give your consent for information retrieval.
- You will see the user information shown as a decoded JWT token.
- Visit http://localhost:{app-2-port}/profile
- You will not be asked to enter the credentials again.
- To logout visit http://localhost:{app-port}/logout

## Useful Notes
- Use the "Monitoring" dashboard in Auth0 to track the logs of your applications' HTTP communication with Auth0.



