# SSE Assignment - Assignment 1

Ananthanarayanan S  
CB.SC.P2CYS23007  

## Case study: Corporate HRMS System

### Scope:
An corporate HRMS System where employees can log in, view account details, Change the database, Apply Leave.

### Objectives:
- Identify potential threats.
- Assess the impact and likelihood of threats.
- Develop mitigation strategies.

### Entities:
- Employee (External Entity)
- Web Server (Process)
- Database Server (Data Store)
- Authorization Server (Internal Entity)

### Steps:
1. Click new model.

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/c1e1219e-e6c8-4a3b-9e69-309752b040b4)

Now the resultant canvas will be:
-	Demo of Simple Web Application

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/0621a303-71ad-42f1-b87a-e8824bd90781)


## Identify and Analyse Threats:

Navigate to ‘View’ then click ‘analysis view’

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/73c2dc99-2186-4ee3-a651-06ff7c4d8a57)


### Data Flow Sequence:
1. **Employee -> Web Application (Submit credentials)**
   - **Data Flow Type:** HTTP
   - **Description:** Employee submits login credentials to the web application.

2. **Web Application -> Authorization Server (Verify credentials)**
   - **Data Flow Type:** HTTPS
   - **Description:** The web application sends the credentials to the authorization server for verification.

3. **Authorization Server -> Web Application (Send account details)**
   - **Data Flow Type:** HTTPS
   - **Description:** The authorization server sends the account details back to the web application.

4. **Web Application -> Employee (Display account details)**
   - **Data Flow Type:** HTTP
   - **Description:** The web application displays the account details to the customer.

5. **Employee -> Web Application (Request Applying Leave)**
   - **Data Flow Type:** HTTPS
   - **Description:** The employee requests applying leave through the web application.

6. **Web Server -> Authorization Server (Update Leave Account)**
   - **Data Flow Type:** HTTPS
   - **Description:** The web server sends the leave request to the authorization server to update the leaves.

7. **Web Server -> SQL Database Server (Initiate request for Update)**
   - **Data Flow Type:** HTTPS
   - **Description:** The web server initiates the request with the database server.

8. **SQL Database Server -> Web Server (Confirm Update)**
   - **Data Flow Type:** HTTPS
   - **Description:** The SQL Database Server confirms the update and sends the confirmation back to the web server.

9. **Web Server -> Employee (Display HRMS System)**
   - **Data Flow Type:** HTTPS
   - **Description:** The web server displays the leave status to the employee in the HRMS System.

### Analysis:
- **Potential Threats:** 
  1. Unauthorized access to employee credentials during transmission over HTTP.
  2. Man-in-the-Middle attacks during HTTPS communication.
  3. SQL Injection during leave update process.
  4. Denial of Service (DoS) attacks targeting Web and Database servers.
  
- **Impact and Likelihood:** 
  - Impact: Potential loss of sensitive data, service disruption, unauthorized access to HRMS.
  - Likelihood: Depends on the effectiveness of security measures in place.
  
- **Mitigation Strategies:**
  - Implement HTTPS for all data transmissions.
  - Use strong authentication and authorization mechanisms.
  - Regular security audits and updates to prevent SQL Injection.
  - Implementing rate limiting and other DoS protection measures.


![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/d409c1f5-acb1-4138-b060-73d3aed7e444)

Analysis View -

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/026840ce-27ae-4c92-8b1c-669659d427b2)

We can choose a specific threat and check its properties-

![image](https://github.com/ananthan05/Secure-Systems-Engineering/assets/140697378/1228bfee-5ff1-4e6f-965d-6c3a903920c0)
