## This project is all about Spring Security

*   commit1: just add two lines (dependency) and you have login form with dummy user "user" and secure password shown in console in front of your whole application as per default it activate form based authentication.
*   commit2: Basic Authentication : Adding Basic Authentication is just overriding method from WebSecurityConfigurerAdapter method configure and using antMatchers in order to allow and disable access.
*   commit3: In-Memory Authentication : Users can be added in In Memory Authentication. Spring has User which extends UserDetails which list can be put into InMemoryUserDetailsManager
*   commit4: JDBC-Authentication :
**  Create User Entity and Repository 
**  Implement UserDetails and UserDetailsService from Spring Security
**  Configure AuthenticationProvider with implemented Service.
**  Configure AuthenticationManagerBuilder with AuthenticationProvider
*   commit5: formLogin Authentication
BCrypt Passwords : BCrypt Library is spring in built for hashing passwords. They are safe so. Just add to the AuthenticationProvider that you want to use BCryptPasswordEncoder.
Adding Authorization in Spring:

Create Authority Entity and Repository

Add Authority List to UserDetailsService and Principal

update UserDetails Overridden method in Principal to give back these Authorities

Add all Controller Methods with @PreAuthorize(hasRole()) as per requirement. Its provides Method Level Class security.

In Configuration add @EnableGlobalMethodSecurity(prePostEnabled = true) in order to let step 5 work.

Create AuthorityMapper

Add this to AuthenticationProvider


Form based Authentication in Spring:

Add Thymeleaf-extras-springsecurity4 dependency.

Implement Navigation. use sec:authorize ="isAnonymous()" (elements shows when not logged in) or "isAuthenticated()" (elements shows when logged in)for Login/Logout links

Implement Login/Logout Methods in Controller returning respective page

Security Configuration to set formLogin instead of basicAuth and set login and logout behaviours

Add error.html which is default template name for all errors with code 404, 403, 400

*   commit6: LDAP Authentication 

Add spring-security-ldap for LDAP and unboundid-ldapsdk for embedded LDAP server.

Provide application properties and dummy data for embedded ldap

with help of AuthenticationBuilder configure LdapAuthentication

