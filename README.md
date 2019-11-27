# Entry-Management System

## Summer Geeks Assignment for SDE-Intern at Innovaccer

## Introduction
The web application gives the user two options: ``Check In`` and ``Check Out``.

**Check In:**
The Visitor is asked to enter his/her and Host's details.Thereafter,a SMS and E-mail is sent to the Host giving the details of the Visitor.

**Check Out:**
The Visitor is asked to enter his/her E-mail Id for verification and after it the visitor is checked out.

## Tech Stack
* Front-End : [EJS](https://ejs.co/), [HTML](https://html.com/), [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS), [Bootstrap](https://getbootstrap.com/).
* Back-End : [NodeJS](https://nodejs.org/en/), [ExpressJS](https://expressjs.com/), [Nodemailer](https://nodemailer.com/about/)(Mail service), [fast2sms](https://www.fast2sms.com/)(Message Service).
* Database: [MongoDB](https://www.mongodb.com/).

## Approach

**Workflow:**
* Visitor is given the option to Check-in.
* Visitor is asked to fill his own details as well as the host's details whom he wants to meet.
* Visitor is then given the option to Checkout.
* At the time of checkout, the Visitor is asked to enter his Email-id for verification.
* After this, the visitor is checked out of the system.
* A visitor can check-in and checkout at any time irrespective of the other visitors.

**Database 'user'** and it's **Collections** are designed as following:
* **Clients:** Contains details specific to the visitors.
```console
|___Clients
        |___name 
        |___email
        |___phone
```
* **Hosts:** Contains details specific to the hosts.
```console
|___Hosts
       |___hname
       |___hemail 
       |___hphone
```
* **Visits:** Contains details specific to the visits by visitors(Check-in - Check-out).
```console
|___Visits
       |___email
       |___checkin
       |___checkout
       |___hemail
```

I have made **3 collections** so as to **reduce redundancy** in the database. Even if a visitor has visited the office more than once, his details will only be stored once in the Clients collection. The same goes for the Host's Details.

**Corner Cases:**
* A visitor cannot check-in again if he/she is already checked in and has **not checked out**. 
* A visitor cannot checkout with an Email-Id that has not been used to Check-in.
* A visitor cannot checkout again if he/she is already been checked out.

## Screenshots

![Entry Management System's Home Page]()

![Check-in Portal]()

![Check-in Success Message]()

![Check-out Portal]()

![Check-out Success Message]()

Error Messages
![]()
![]()
![]()

Collections:

![Clients]()

![Hosts]()

![Visits]()

![E-mail & Message sent]()

![E-mail received at host's end after check-in]()

![E-mail received at visitor's end after check-out]()


## Installation
1. Install [MongoDB](https://www.mongodb.com/) and [NodeJS](https://nodejs.org/en/).
2. Clone the assignment using 
```bash
git clone https://github.com/Pulkit287/Innovaccer-Summergeeks-Assignment.git
```
3. Install dependencies after entering the project directory.
```bash
cd Innovaccer-Summergeeks-Assignment
npm install
```
4. Then you'll have to update the email user and password in ``
app.js
`` -

```console
Add Email account for sending E-mail via node-mailer for example

user: 'ENTER E-MAIL ID',                                
pass: 'ENTER YOUR PASSWORD'
```
and ``from`` variable in ``sndMail() function`` in ``app.js`` used to send mails-

```console
from: 'ENTER E-MAIL ID'
```
finally, update your ``FAST2SMS API authorization key`` in ``app.js`` in ``sndMsg()`` function for sending sms through fast2sms.
```console
Add details for sending message's via 'Fast2sms' API for example

"authorization": "ENTER YOUR AUTHORIZATION KEY" 
```
5. Run ``mongod`` in seperate terminal and ``node app.js`` in seperate terminal with the project.
6. Then go to [localhost:3000](localhost:3000).

## Author

Name: Pulkit Mathur

E-mail ID: [17ucs116@lnmiit.ac.in](mailto:17ucs116@lnmiit.ac.in)

