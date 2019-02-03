## This project is all about Spring Security

*   commit1: just add two lines (dependency) and you have login form with dummy user "user" and secure password shown in console in front of your whole application as per default it activate form based authentication.
*   commit2: Basic Authentication : Adding Basic Authentication is just overriding method from WebSecurityConfigurerAdapter method configure and using antMatchers in order to allow and disable access.
*   commit3: In-Memory Authentication : Users can be added in In Memory Authentication. Spring has User which extends UserDetails which list can be put into InMemoryUserDetailsManager
*   commit4: JDBC-Authentication :
**  Create User Entity and Repository 
**  Implement UserDetails and UserDetailsService from Spring Security
**  Configure AuthenticationProvider with implemented Service.
**  Configure AuthenticationManagerBuilder with AuthenticationProvider