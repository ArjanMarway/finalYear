# Software Architecture & Technology Rationale

### Technologies Used:

### Frameworks, Language and Libraries to be used in this project:
- Python for implementing functionality throughout the project.
- SpeechRecognition for implementing STT engines into the system.
- YAML for importing, reading and configuring the user profile.
- eSpeak to implement the TTS engine.
- Pip to manage python packages
- PyAudio to record and output audio across multiple OS.
- Google STT to convert audio input into strings

### Why we chose STT, TTS and Logic Engine?
The engines used provide the groundwork for the VA  to work. Therefore, different people are able to communicate with it at different times.

The core components of the VA are are: STT, Logic, Responses and TTS.

- Google STT converts the users speech into a string via audio processing and sends this as a variable to Logic Handling. 

- Logic takes the string and and checks whether the string matches against the arguments of functions. The string is then passed to the Responses file.

- Responses.py is the encyclopedia of set responses for the questions asked by the user. It stores these ansers inside functions, which are then passed to the TTS engine. 

- TTS outputs the response via the TTS engine, eSpeak (Linux) or Say (for OS X). 

![alt tag](http://cdn.dzone.com/static/images/vaannila/spring/spring-mvc-pic-9.gif)

This is what the Spring MVC framework file structure looks like:

![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/master/0_docs/Images/src-springMVC.png)

The model, repository, service and validator is our main project body which handles the data information and software implementation, and we work with the css and js in the webapp below. The view folder works for webpages displayed through the project. 

![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/master/0_docs/Images/Architecture.png)

### External APIs:
The usage of external API’s is to expand the components in our system in order to implement key core features. The features include:

- **OpenStreetMap**

In order to implement a functional map system we need an API that was easy to work with, so we decided to use Open Street Map. A great advantage of using Open Street Map data is that it is open-source and hence it is free to use. It is also easy to place into an application which makes for a great alternative to Google Maps. We will need it to create routes to and from Lecturer and Learner meetups and to ensure that the Lecturer or Learner can interact with the map in real time (by incorporating javascript) which would allow organising a meetup to be a quick, simple and satisfying experience. It is also flexible in terms of scaling, so a lecturer or learner can easily use it on different environments such as their mobile device as well as a desktop.

- **JavaMail**

JavaMail is imported by the (org.springframework.mail.javamail) library which is a core API which will add lots of functionality to our system. It allows the system to automatically send emails out to users from the system in that users are sent emails after certain events such as creating an account for the first time, changing an password and recovering an account. JavaMail will also would enable emailing between learners, lecturers and administrators which is a core aspect to the overall functionality of service. It is also supported by the Spring Framework supports which makes it easier to integrate into our system.

![JavaMail-image](https://www.javatpoint.com/images/Javamail1.jpg)

- **Java Message Service (JMS)**

Java Message Service (JMS) API is allows us to create, send, receive and read messages using reliable coupled communication. JMS is a Java API which defines a common set of interfaces that allow Java programs to communicate with other messaging implementations. It allows communication that is asynchronous and reliable. Jave Messaging Service allows the users of the website to message each other. As JMS is asynchronous, the user is not required to request messages in order to receive them.

![JMS-Image](http://techaffinity.com/blog/wp-content/uploads/2015/07/jmsBlogImage.png)

- **Java Persistence (JPA)**

Java Persistence API allows us to develop our webapp with an object/relational mapping facility for managing relational data in our application. Java Persistence API allows us to perform object to relational Mapping (ORM) in our database. It is an open source implementation but requires a database to persist to. The Java Persistence API allows us to map our queries to the database and converts the results to our model. It allows us to handle any incoming requests.

![JPA-Image](https://www.ibm.com/support/knowledgecenter/SSTVLU_7.1.0/com.ibm.websphere.extremescale.over.doc/images/jpa_loader.gif)


- **Leaflet.js**

Leaflet.js API allows us to create a map on a page and manipulate it. It is an open-source JavaScript library for mobile-friendly interactive map. The API uses JavaScript to allow the map to be implemented into the system. By using Leaflet.js API we are able to implement OpenStreetMaps into our system. We are also able teo view the maps on a mobile device as well as on major desktops and mobile platforms. Leaflet.js allows us to use any map provider and roll our own tiles. 


### Security Strategy: 

- **Spring Security**

We will be using the Spring security framework to authenticate and authorize different users. The security framework enables users to login to an application by verifying their credentials and additionally provides the ability to hide a certain portion of a webpage if the user's account type does not have the appropriate privileges. For example, a user with a learner account type is unable to view the assessment scores or grades of another learner as this privilege is given to a lecturer. Furthermore, only administrators have the ability to delete or suspend both learner and lecture's accounts, whereas a user with a lecturer account has the privilege to upload/delete lectures from the system. This system ensures that a user only has the authorisation to modify their data, and not the data of other users. Moreover, by using the Spring security framework, we will be able to identify incoming requests from HTTP sources from users and envoy these requests to a controller. The controller can give a response to the user after handling the request and in turn, this allows for more efficiency and added security.

The Spring security framework provides us with the flexibility of selecting exactly how we wish to secure the system - we are not presented with a fixed set of options and are free to make our own methods if we choose to. The requirements have given us insight as to which features would need to be secure, e.g. when lecturers organise meet ups with learners, only the learners and lecturers enrolled on that particular course are able to view the meetup locations. Also implementing a login system guarantees that only legitimate account holders can access the live chat, which ensures that non-users are unable to read private messages between users. The system will be monitored by the administrators, who will make sure that any inappropriate behaviour is dealt with appropriately, and will additionally overlook all activities, including verifying  that the location for a Meet-Up is suitable.  

- **Cross-Site Scripting (XSS)**

We have taken special measures to prevent Cross-site scripting (XSS) from taking place in our system. Cross-site scripting is when an attacker executes a script which allows them to gain access to certain parts of a website. Most of the times, XSS is used to steal cookies and steal session tokens of a valid user to perform session hijacking. We have decided to add filters into our system to prevent cross site scripting. Although this doesn't fully protect our website, it would take a very skilled hijacker to hijack our website. The hijacker would have to load the malicious script on the server and wait for it to be executed. This would be injected onto the webpage, then onto the database, leaving the webpage in a vulnerable state. It is important for the system to have filters in place which prevent XSS attacks.

![XSS-image](https://www.secpoint.com/images/image/cross-site-scripting-explained.gif)

- **SQL Injections**

We have also taken consideration for SQL injection attacks so that users are not able to inject SQL queries into our website. If an attacker successfully proceeds with an SQL Injection then they would have access to our database, allowing them to access, modify and delete data. We are protected from SQL injections as nothing is passed through our URLs, meaning an attacker cannot use a SQL Injection to gain access to our website. We have also added SQL parameters in our SQL statements so that there is no other way for attackers to bypass our website using SQL injections

![SQL-injection](http://mycourses.med.harvard.edu/ec_res/nt/02CB3F0E-DCC8-4C2D-BAB1-46BEB3FE9302/image002.png)

- **Form Validation**
We have added form validation into our forms to ensure that information is valid and is being entered. Some ways we have done this is by making the user input their data twice (confirming email address and password). This ensure the users are actual users and are not hackers using an automated script. We also plan to add a validator which checks if the user is a human. We did the form validation using spring and also created classes in our validator folder.

![FormValidation-Image](https://www.smashingmagazine.com/wp-content/uploads/images/web-form-validation/validation.png)

- **Firewalls** 

For the network we will be having a firewall to control traffic flow of incoming requests from the outside world and blocking any unauthorised requests. The firewall will filter incoming packets, considering their source, destination and the data it contains and discard any that do not match its internal rule set. Also the firewall will log traffic coming in so we can see what type of traffic is passing the system, helpful for identifying external attacks to the system. Furthermore it can alert us to internal threats as it monitors internal packets leaving the system so if malware enters the system it sends a signal to the author that it is in the system, this adds further security and protection to the system. Users can have external firewalls on their hard drive. Some external firewalls are loaded on antivirus software and work with browsers to prevent malicious web pages. These external firewalls help limit the inflow of fata from outside sources but also control data coming in.

![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/master/0_docs/Images/Computer-and-Networks-Network-Security-Diagrams-Access-Control-and-Encryption.png)

### Two-Factor Authentication
For authentication we decided to use Google Authenticator because it is from a well-known and trusted source and it adds extra secure communication between client and server. Google Authenticator allows for authentication for mobile users as it uses a two-step verification process. Time-based One-time Password Algorithm (TOTP) and HMAC-based One-time Password Algorithm (HOTP). The TOTP algorithm uses a one-time password with a time stamp of the current time for a one use password. The authenticator provides a six to eight digit one-time password that users must provide along with their username and password. This is great as if there was to be a hacker trying to break into a user’s account, knowing the username and password isn't enough as they would need knowledge of the shared secret key or access to the authenticator from the device. So this is a great way for adding extra security to the system. 

![Two-Factor-Authentication-Image](https://github.com/UOL-CS/co2015-16-17-group-04/blob/master/0_docs/Images/Two-Factor-Authentication.png?raw=true)

### Performance Strategy:
- To manage out performance we will use the developer tools in Google Chrome to monitor the details of each webpage to make sure the application is working well. We will also use it to check the time spent between the time the HTTP request was made and the time the view is displayed on the browser. If we see that it is taking too long for the page to display then we will perform and create some testing scripts that will focus on absolute performance, testing how long it takes to render a certain page and on a performance scale how does the system slow as more users are using the system at once.

- Moreover we will be incorporating database normalization in our mySQL scripts which reduce data redundancy and improve data integrity which will ensure that our system is performing in the most efficient manner it can.

### Architectural Design Decisions

- **How did JavaMail support our project? What design decisions did we change during or after implementation?**

Javamail allowed us to send emails out to the users after a certain reqeust was sent on the system. We had to create a default email address for the emails to be sent from. Some instances where we have used the JavaMail API is when users register to the system. When users register, an email is sent to the user wecloming them to our website. We were originally going to use JavaMail to send the users password to them if they forgot it, however we realised that because of the security of our website, the password send would be encrypted. We then decided to have a 'forgot username' page as an aditional feature, where an email is sent to the user containing their username. This was done via JavaMail. We have also used the JavaMail API for learners and lecturers to email each other. It is one of the core aspects of our functionality. 

- **How did Spring Security support our project? Why did we not use other means of security?** 

By implementing Spring Security into our project, we were able to keep the website secure. It has protected us from many attacks such as XSS attacks, file upload and form validation. Spring Security has allowed us to add authentication into our system. Users are now required to enter their password and email address twice, just to ensure they are real users. Non registered users cannot access the system. We decided not to add other security measures as Spring Securirt was protecting our website enough. Nevertheless, we did add a few classes which protected the website even more. Our main form of security was done via Spring Security. 

- **Why did we use Gradle JettyRunWar instead of Gradle BootRun?**

We decided to use Gradle JettyRunWar instead of BootRun as JettyRunWar would deploys a WAR (web application archive) to an embedded Jetty web container. This meant that we would not have to have anything stored locally, saving space for our developers but also making it a lot simpler to deploy. Although it meant that we had to redeploy the server everytime we made a change to the JSP pages, it was more effecient for us to use JettyRunWar. After the project is completed, we plan on converting to the newest version of Jetty as Gradle are removing the current method in future releases.   

- **Why did we decide to do the CSS manually rather than using Bootstrap?**

When deploying multiple webpages using bootstrap, we realised that there were things which overlapped each other. Bootstrap didnt allow us to have as much control over the design of our web pages. Our objects + design was fixed. We did not like this as some things on our web page looked odd. We decided to create our CSS manually and upload to RAWGIT, which allowed us to use the CSS on our page without it being inside the directory. It allowed anyone to edit it from anywhere. It also allowed us to have full control over the design of our webapp. 

- **Why did we decide to use emails as our way of sending meetup requests?**

We decided to use emails as our way of sending meetup requests because of the simplicity of doing it. We originally wanterd to have meetups done via a notification on the website but after careful discussion and planning we decided to implement the meeting requests via email. We ensured that we were still meeting the requirements and that the users could still send meetups to each other. Another influence in our decision to do this was because we had already used the email messages for other features. This includesthe report a problem page, where the problem would be sent to the BrainWave email address where the admin can view the problem. It was also used on the signup page where the user would receive an email upon signup. We saw this to be a vital part of our system as it ensures the user it signed up to the website with a valid email address. 

- **Why did we decide to use Google Authenticator for our two factor authentication?**

We decided to use Google Authenticator over any other authenticator for many reasons. The Google authenticator app works independently to any other app so nobody can access the code through a third party device. Another reason it is so secure is because it creates a new code every 60 seconds. This ensures that the code is more protected as the authentication code is not stored for very long. The Google authenticator app does not require any internet or mobile phone  connection. Because of the TOTP algorithm inbuilt into the authenticator, we are able to see the code without the need of internet. Google Authenticator also allows us to have multiple accounts in one place. If a user is both a lecturer and learner then they would require two authentication codes and Google Authenticator allows this. One of the most important factors of why we chose Google Authenticator was because it was free and had the ability to be used with Non-Google websites. You are just required to scan the QR code and then your code would be given to you.

- **Why did we decide to use the Leaflet.js API to implement OpenStreetMaps?**

At first we were struggling to find an API to implement OpenStreetMaps into our system. We thought about using the OpenLayers API but it was conflicting with other features of our system. We had a group meeting and decided to use the Leaflet.js API as it was a JavaScript library which had many plugins, allowing us to have free control over the maps we implemented into our system. We ensured that we did our research before implementing Leaflet.js into our system as we didnt want to cause any conflict errors in our system.  

- **Why did we decide to send reports to admin via email?**

We implemented a report a problem page for users to send reports. When the user submits the report, the report is sent to the BrainWave platform email address - brainwaveplatform@gmail.com. Only the administrators have access to this email address and will be able to view the reports. The reason we decided to have reports sent by email is because it was simpler as only the administrators have access to the account. If the administrator account was hacked then the hacker would be able to see all of the reports, as well as other information. As the security of our website improves, we plan to implement the reports directly into the amdministrator account.  

- **Why did we decide to give the administrator accounts a seperate login page rather than having them on the standard login/register page?**

We decided to give the administrator a seperate login page due to security reasons. The administrator login page is hidden. Initially there is only one administrator account which is owned by one of the developers. The administrator can then give the hidden login page to another administrator, who can then register an account. We did this as we didn't want users registering as an administrator and taking advantage of the administrator features, such as deleting other user accounts. In future releases we plan to give administrators rights to promote other administrators rather than having a register page. 

### Architectural Decisions (200 words)

Throughout my project, I have made many architectural design decisions which were set to contribute to the project. Some of these decisions were to use different STT and TTS engines to support the natural language input/output. By implementing these engines (such as Google STT) it has been easier to reach the project requirements. Another decision I had was to choose where system responses came from. Originally I intended to use a database, however this would not be efficient as the VA would only be reading data, so I decided to store all responses in a seperate Python file. On the other hand, many design decisions have had to change due to tasks not being able to be completed. This resulted in me having to find a different way to gather feedback and requirements for my system, resulting in a change to the project schedule and aim. 
