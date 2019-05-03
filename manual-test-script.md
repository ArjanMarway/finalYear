# Tests


## Registration Screen

| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 1.1 | Go to /webapp/registration    | The registration screen should appear |
| 1.2 | Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says 1."THIS FIELD IS REQUIRED. USERNAME MUST BE BETWEEN 6 AND 32 CHARACTERS LONG."  2."THIS FIELD IS REQUIRED. PASSWORD MUST BE AT LEAST 8 CHARACTERS." |
| 1.3 | Enter username `'alexa'`. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says 1."USERNAME MUST BE BETWEEN 6 AND 32 CHARACTERS LONG."  2."THIS FIELD IS REQUIRED. PASSWORD MUST BE AT LEAST 8 CHARACTERS." |
| 1.4 | Enter password `'leschar'`once. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says 1."THIS FIELD IS REQUIRED. USERNAME MUST BE BETWEEN 6 AND 32 CHARACTERS LONG." 2. "PASSWORD MUST BE AT LEAST 8 CHARACTERS." 3. "THESE PASSWORDS DON'T MATCH." |
| 1.5 | Enter password `'leschar'`twice. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says 1."THIS FIELD IS REQUIRED. USERNAME MUST BE BETWEEN 6 AND 32 CHARACTERS LONG." 2. "PASSWORD MUST BE AT LEAST 8 CHARACTERS." |
| 1.6 | Enter username `'alexa'` with password `'leschar'`. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says 1."USERNAME MUST BE BETWEEN 6 AND 32 CHARACTERS LONG." 2."PASSWORD MUST BE AT LEAST 8 CHARACTERS." 3."THESE PASSWORDS DON'T MATCH." |
| 1.7 | Enter username `'alexa'` with password `'leschar'` twice. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says 1."USERNAME MUST BE BETWEEN 6 AND 32 CHARACTERS LONG." 2."PASSWORD MUST BE AT LEAST 8 CHARACTERS." |
| 1.8 | Enter username `'alexa'` with password `'leschar'` twice. Enter email `'tommy'` once. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says 1."USERNAME MUST BE BETWEEN 6 AND 32 CHARACTERS LONG." 2."PASSWORD MUST BE AT LEAST 8 CHARACTERS." 3.Alert "Please include '@' " |
| 1.9 | Enter username `'alexa'` with password `'leschar'` twice. Enter email `'tommy'` twice. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says 1."USERNAME MUST BE BETWEEN 6 AND 32 CHARACTERS LONG." 2."PASSWORD MUST BE AT LEAST 8 CHARACTERS." 3.Alert "Please include '@' " |
| 2.1 | Enter username `'michael'` with password `'leschar'` twice. Enter email `'tommy'` twice. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says 1."PASSWORD MUST BE AT LEAST 8 CHARACTERS." 2.Alert "Please include '@' " |
| 2.2 | Enter username `'michael'` with password `'rightpass'` twice. Enter email `'tommy'` twice. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says "Alert "Please include '@' " |
| 2.3 | Enter username `'michael'` with password `'rightpass'` twice. Enter email `'tommy@gmail.com'` first and then enter `'tommy'`. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says 1."EMAILS DON'T MATCH." 2."Alert "Please include '@' " |
| 2.4 | Enter username `'michael'` with password `'rightpass'` twice. Enter email `'tommy@gmail.com'` first and then enter `'tom@gmail.com'`. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says "EMAILS DON'T MATCH." |
| 2.5 | Enter username `'michael'` with password `'rightpass'` first and then enter `'leschar'`. Enter email `'tommy@gmail.com'` first and then enter `'tom@gmail.com'`. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says "EMAILS DON'T MATCH." |
| 2.6 | Enter username `'michael'` with password `'rightpass'` twice. Enter email `'tommy@gmail.com'` twice. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | You are taken to Home page /webapp/welcome|
| 2.7 | Enter username `'michael'` with password `'otherrightpass'` twice. Enter email `'tom@gmail.com'` twice. Choose `LECTURER` or `LEARNER`. Click `SUBMIT` | Message says "USERNAME ALREADY EXISTS!" |

## Login Screen

| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 3.1 | Go to /webapp/registration   | The login screen should appear |
| 3.2 | Enter username `'wrongusername'` with description `'rightpass'`. Click `LOG IN` | Refresh the page |
| 3.3 | Enter username `'michael'` with password `'wrongpassword'`. Click `LOG IN` | Refresh the page |
| 3.4 | Enter username `'wrongusername'` with password `'wrongpassword'`. Click `LOG IN` | Refresh the page |
| 3.5 | Enter username `'michael'` with password `'rightpass'`. Click `LOG IN` | You are taken to Welcome page /webapp/welcome |


## Add Course Screen

| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 4.1 | Go to /webapp/course/add  | The course add screen should appear |
| 4.2 | Enter course name `java` with description `fundamental java skills`. Click `SUBMIT` | You are taken to Welcome page /webapp/welcome |

## Course Lists Screen
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 5.1 | Go to /webapp/course/list  | The lists of courses should be appeared |

## Send email
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 6.1 | Go to /webapp/registration    | The registration screen should appear |
| 6.2 | Type in correct information and click SUBMIT  | The welcome email will be sent to the email address |

## Authentication
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 7.1 | Go to /webapp/registration   | The login screen should appear |
| 7.2 | Type in correct username and password then click SUBMIT   | The two-factor authentication page should be appeard ![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/QRcode.png)|
| 7.3 | Use the google authenticator in android or ios mobile phone to scan the QR code in the two-factor authentication page | The verification code should be showed on the phone screen <img src="https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/google%20authenticator.png" alt="alt text" width="300" height="400">|
| 7.3 | Type in the verification code and click LOG IN | You are taken to Welcome page /webapp/welcome |

## Report Problem
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 8.1 | Go to /webapp/reportProblem    | The report problem page screen should appear |
| 8.2 | Type in the problem and click SUBMIT  | The report problem email will be sent to the email address: brainwaveplatform@gmail.com |

## Log out Button
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 9.1 | In the welcome page /webapp/welcome, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |
| 9.2 | In the add course page /webapp/course/add, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |
| 9.3 | In the course list page /webapp/course/add, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |
| 9.4 | In the send message page /webapp/sendMessage, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |
| 9.5 | In the report problem page /webapp/reportProblem, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |
| 9.6 | In the arrange meetup page /webapp/meetup/main, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |

## Home page Button
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 10.1 | In the add course page /webapp/course/add, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |
| 10.2 | In the course list page /webapp/course/list, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |
| 10.3 | In the send message page /webapp/sendMessage, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |
| 10.4 | In the report problem page /webapp/reportProblem, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |
| 10.5 | In the arrange meetup page /webapp/meetup/main, Click the button 'LOGOUT'  | The page should go to the registration page /webapp/registration |


## Send Message Button
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 11.1 | In the add course page /webapp/sendMessage, type in the correct information and then Click the button 'SUBMIT'  | The email should be sent to the correct user's email address |
| 11.2 | In the add course page /webapp/sendMessage, type in the incorrect information and then Click the button 'SUBMIT'  | The email should not be able to sent out |

## Forgot Username
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 12.1 | Go to the log in page /webapp/registration and click the  'FORGOT USERNAME?'  | You are taken to the page /webapp/forgotPassword  |
| 12.2 | Type in the email address when register and Click the button 'SUBMIT'  | A email with the username should be sent to the email addrerss  |

## Meet Up
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 13.1 | Use the lecturer account `'yyyyyy'` to login and then go to the Welcome page /webapp/welcome. Click the  'Arrange a meet-up'  | You are taken to the page /webapp/meetup/main  |
| 13.2 | Type in the correct information `' zzzzzz, java spring skills, java spring skills discussion'` choose a location to meet in the map (the map should be zoomed up and zoomed down) and then Click the button 'SUBMIT'  | The email with the correct information and a link of the meet-up map should be sent to the learner's email addrerss  |
| 13.3 | Use the learner account`'zzzzzz'` to login and open the link showed in email address  | The page /webapp/meetup/view should be opened with meet-up location map  |

## Security
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 14.1 | Use the lecturer account `'yyyyyy'` to login and then go to the welcome page /webapp/welcome.  | The page should allow lecturer to upload course, edit cousre, manage meet-up, send message and open the course lists |
| 14.2 | Use the learner account `'zzzzzz'` to login and then go to the welcome page /webapp/welcome.  | The page should allow learner to access meet-up map, send message, leave review, rate course and open course lists  |

## Rate and Review
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 15.1 | Use the learner account `'zzzzzz'` to 1.login and then go to the course lists page /webapp/course/list. 2.Choose a course from lists and click on it  | You are taken to the webapp/course/viewcourse  |
| 15.2 | Click the "Leave a review" | You are taken to the webapp/course/rateview  |
| 15.3 | Choose a rating stars for the course and type in the review in text box and then Click the button 'SUBMIT' | You are taken back to the webapp/course/list  |
| 15.4 | Click on the course again | You are taken to the webapp/course/viewcourse, and the review and rate should be appeared on the page  |
| 15.5 | Use the lecturer account `'yyyyyy'` to 1.login and then go to the course lists page /webapp/course/list. 2.Choose a course from lists and click on it  | You are taken to the webapp/course/viewcourse  |
| 15.6 | Click the "Leave a review" | You are not allowed to access the webapp/course/rateview  |

## Responsive Web Design
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 16.1 | Go to the Login and Registration page /webapp/registration  | The reponsive web should be worked  |
| 16.2 | Go to the Welcome page /webapp/welcome  | The reponsive web should be worked  |
| 16.3 | Go to the Add Course page /webapp/course/add   | The reponsive web should be worked  |
| 16.4 | Go to the Course Lists page /webapp/course/list   | The reponsive web should be worked  |
| 16.5 | Go to the Report Problem page /webapp/reportProblem   | The reponsive web should be worked  |
| 16.6 | Go to the Send Message page /webapp/sendMessage  | The reponsive web should be worked  |
| 16.7 | Go to the Meet-up page /webapp/meetup/main  | The reponsive web should be worked  |
| 16.8 | Go to the Course viewing page webapp/course/viewcourse  | The reponsive web should be worked  |
| 16.9 | Go to the Rating and Viewing page webapp/course/rateview  | The reponsive web should be worked  |

## Administrator delete course
| Test | Step | Expected Outcome |
|----|:-----|:-----|
| 17.1 | Go to the Login and Registration page /webapp/registration and enter the username `'administrator'` and password `' password '` and then click 'SUBMIT' | You are taken to /webapp/admin/main |
| 17.2 | Click the 'Delete' button beside the course  | The course should be deleted  |
| 17.3 | Go to /webapp/course/list | The course should not be appeared in the lists  |



# Test Results

## Test Run 19-Apr-2017

**Tests Executed:** 1.1, 1.2, 1.4, 2.6, 3.1, 3.2, 3.5, 4.1, 4.2, 5.1
**Tests Failed:** None

1.1 Go to the Register page

1.2 Type the username and then click the SUBMIT Button
    
    Get the error message   
    
1.4 Type the password and click the SUBMIT button

    Get the error message 
    
1.9 Type the password and click the SUBMIT button

    Get the error message 
    
2.1 Type the password and click the SUBMIT button

    Get the error message 
2.6 Type the username and password and email address click the SUBMIT button

    Then go to the home page
    

3.1 Go to the login page

3.2 Type the username and password and click the LOG IN button

    Then get the error message 
    
3.3 Type the username and password and click the LOG IN button

    Then get the error message    
    
3.5 Type the username and password and click the LOG IN button

    Then go to the welcome page


4.1 Go to the add course page

4.2 Type the course name, description and click the SUBMIT button and then
5.1 Go to the course lists page

    Get the lists of courses successfully

## Test Run 22-Apr-2017

**Tests Executed:** 1.1, 1.2, 1.5, 1.7, 2.2, 2.4, 2.6, 3.1, 3.2, 3.5, 4.1, 4.2, 5.1
**Tests Failed:** None

1.1 Go to the Register page

1.2 Type the username and then click the SUBMIT Button
    
    Get the error message   
    
1.5 Type the password and click the SUBMIT button

    Get the error message 
    
1.7 Type the username and password then click the SUBMIT button

    Get the error message 
    
2.2 Type the username and password then click the SUBMIT button

    Get the error message 
    
2.4 Type the username, password and email address then click the SUBMIT button

    Get the error message
    
2.6 Type the username, password and email address then click the SUBMIT button

    Get the error message
    

3.1 Go to the login page

3.2 Type the username and password and click the LOG IN button

    Then get the error message 
    
3.3 Type the username and password and click the LOG IN button

    Then get the error message    
    
3.5 Type the username and password and click the LOG IN button

    Then go to the welcome page


4.1 Go to the add course page

4.2 Type the course name, description and click the SUBMIT button and then
5.1 Go to the course lists page

    Get the lists of courses successfully
    
 ## Test Run 25-Apr-2017

**Tests Executed:** 1.1, 1.2, 1.7, 2.2, 2.4, 2.6, 2.7 3.1, 3.2, 3.5, 4.1, 4.2, 5.1, 6.1, 6.2, 7.1, 7.2, 7.3, 7.4
**Tests Failed:** None

1.1 Go to the Register page

1.2 Type the username and then click the SUBMIT Button
    
    Get the error message   
    
1.7 Type the username and password and then click the SUBMIT Button
    
    Get the error message   
    
2.2 Type the username, password and email address then click the SUBMIT button

    Get the error message 
    
2.4 Type the username, password and email address then click the SUBMIT button

    Get the error message
    
2.6 Type the username, password and email address then click the SUBMIT button

    Then go to the home page
    
2.7 Type the username, password and email address then click the SUBMIT button

    Get the error message
    

3.1 Go to the login page

3.2 Type the username and password and click the LOG IN button

    Then get the error message 
    
3.3 Type the username and password and click the LOG IN button

    Then get the error message    
    
3.5 Type the username and password and click the LOG IN button

    Then go to the welcome page


4.1 Go to the add course page

4.2 Type the course name, description and click the SUBMIT button and then
5.1 Go to the course lists page

    Get the lists of courses successfully

6.1 Go to the Register page and then
6.2 
        
    Get the welcome email from correct registerd email address: 693418590@qq.com successfully
    
   ![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/email.png)
    
7.1 Go to the Register page

7.2 

    Type in with correct username yyyyy and correct password yyyyyyyy

7.3 

    Get the code form mobile phone

7.4 
    
    Log in successfully
    
    
## Test Run 28-Apr-2017

**Tests Executed:** 1.1, 1.2, 1.6, 1.8, 1.9, 2.2, 2.4, 2.6, 2.7 3.1, 3.2, 3.5, 4.1, 4.2, 5.1, 6.1, 6.2, 7.1, 7.2, 7.3, 7.4, 8.1, 8.2, 9.1
**Tests Failed:** None

1.1 Go to the Register page

1.2 Type the username and then click the SUBMIT Button
    
    Get the error message   
    
1.6 Type the username and password and then click the SUBMIT Button
    
    Get the error message   
    
1.8 Type the username and password and then click the SUBMIT Button
    
    Get the error message  
    
1.9 Type the username and password and then click the SUBMIT Button
    
    Get the error message   
    
2.2 Type the username and password and then click the SUBMIT button

    Get the error message 
    
2.5 Type the username, password and email address then click the SUBMIT button

    Get the error message
    
2.6 Type the username, password and email address then click the SUBMIT button

    Then go to the home page
    
2.7 Type the username, password and email address then click the SUBMIT button

    Get the error message
    

3.1 Go to the login page

3.2 Type the username and password and click the LOG IN button

    Then get the error message 
    
3.3 Type the username and password and click the LOG IN button

    Then get the error message    
    
3.5 Type the username and password and click the LOG IN button

    Then go to the welcome page


4.1 Go to the add course page

4.2 Type the course name, description and click the SUBMIT button and then
5.1 Go to the course lists page

    Get the lists of courses successfully

6.1 Go to the Register page and then
6.2 
        
    Get the welcome email from correct registerd email address: 693418590@qq.com successfully
    
   ![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/email2.png)
    
7.1 Go to the Register page

7.2 

    Type in with correct username yyyyy and correct password yyyyyyyy

7.3 

    Get the code form mobile phone

7.4 
    
    Log in successfully

8.1 Go to the Report Problem page and then
8.2
     
     Get the report problem email from the correct email address: brainwaveplatform@gmail.com
    
   ![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/reportPrblem.png)
   
9.1 
    
    Log out successfully


## Test Run 29-Apr-2017

**Tests Executed:** 1.1, 1.2, 1.6, 1.8, 2.5, 2.6, 2.7 3.1, 3.2, 3.5, 4.1, 4.2, 5.1, 6.1, 6.2, 7.1, 7.2, 7.3, 7.4, 8.1, 8.2, 9.1, 9.2, 9.3, 9.4, 9.5, 9.6, 10.1, 10.2, 10.3, 10.4, 10.5, 11.1, 11.2
**Tests Failed:** None

1.1 Go to the Register page

1.2 Type the username and then click the SUBMIT Button
    
    Get the error message   
    
1.6 Type the username and password and then click the SUBMIT Button
    
    Get the error message   
    
1.8 Type the username and password and then click the SUBMIT Button
    
    Get the error message  
    
2.4 Type the username, password and email address then click the SUBMIT button

    Get the error message
    
2.6 Type the username, password and email address then click the SUBMIT button

    Then go to the home page
    
2.7 Type the username, password and email address then click the SUBMIT button

    Get the error message
    

3.1 Go to the login page

3.2 Type the username and password and click the LOG IN button

    Then get the error message 
    
3.3 Type the username and password and click the LOG IN button

    Then get the error message    
    
3.5 Type the username and password and click the LOG IN button

    Then go to the welcome page


4.1 Go to the add course page

4.2 Type the course name, description and click the SUBMIT button and then
5.1 Go to the course lists page

    Get the lists of courses successfully

6.1 Go to the Register page and then
6.2 
        
    Get the welcome email from correct registerd email address: 693418590@qq.com successfully
    
   ![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/email2.png)
    
7.1 Go to the Register page

7.2 

    Type in with correct username yyyyy and correct password yyyyyyyy

7.3 

    Get the code form mobile phone

7.4 
    
    Log in successfully

8.1 Go to the Report Problem page and then
8.2
     
     Get the report problem email from the correct email address: brainwaveplatform@gmail.com
    
   ![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/reportPrblem.png)
   
9.1 
    
    Log out successfully
    
9.2 
    
    Log out successfully
9.3 
    
    Log out successfully
   
9.4
    
    Log out successfully
    
9.5 
    
    Log out successfully
9.6 
    
    Log out successfully
    
10.1 
    
    Return to home page successfully
    
10.2 
    
    Return to home page successfully
10.3 
    
    Return to home page successfully
   
10.4
    
    Return to home page successfully
    
10.5 
    
    Return to home page successfully
    
11.1
    
    The email was sent to the correct user's enmail address cd123126@gmail.com successfully
    
   ![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/sendmessage.png)
    
11.2
     
    The page failed to load


## Test Run 30-Apr-2017

**Tests Executed:** 12.1, 12.2, 13.1, 13.2, 14.1, 14.2
**Tests Failed:** None

12.1 Go to registration page and click the 'FORGOT USERNAME?' and then
12.2 Type correct email address: cd123126@gmail.com
    
    Get the correct username from corresponding email address
    
   ![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/forgetUsername.png)

13.1 and then 13.2

    Get the meet-up email with description and link
   
   ![alt tag](https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/meetupEmail.png)
    
13.3 
    
    Get the exact map for meet-up
   
   <img src="https://github.com/UOL-CS/co2015-16-17-group-04/blob/test/0_docs/Images/learnerMeetup.png" alt="alt text" width="500" height="350">

14.1
        
    Access the functions of lecturer successfully 

14.2
        
    Access the functions of learner successfully  
     

## Test Run 01-May-2017

**Tests Executed:** 15.1, 15.2, 15.3, 15.4, 15.5, 15.6, 16.1, 16.2, 16.3, 16.4, 16.5, 16.6, 16.7, 16.8, 16.9, 17.1, 17.2, 17.3
**Tests Failed:** None

15.1 
    
    Go to the page successfully

15.2
    
    Go to the page successfully
    
15.3 
    
    Works successfully

15.4 
    
    Works successfully
    
15.5 
    
    Go to the page successfully

15.6 
    
    Works successfully

16.1 
    
    Works successfully
    
16.2 
    
    Works successfully
    
16.3 
    
    Works successfully
    
16.4 
    
    Works successfully
    
16.5 
    
    Works successfully
    
16.6 
    
    Works successfully

16.7 
    
    Works successfully

16.8 
    
    Works successfully
 
16.9 
    
    Works successfully

17.1 Go to the login page and then 17.2
 
    Delete successfully 
 
17.3 
    
    Works successfully
