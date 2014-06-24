---
layout: post
title: "Software Requirement Specification"
description: "Phase 1"
category: Phase 1
tags: [phase1]
tagline: "Phase 1"
---
{% include JB/setup %}



## Section 1: Introduction

### Software to be Produced

- GameServe is a website that is used to allow UCF students to host their own pick-up games. The software provides locations and time slots for all recreational areas on the UCF campus. Verification logic is also provided to check the reputation of users who have hosted a game previously.

#### Reference Documents:  

- Concept of Operations
- Project Management Plan
- Test Plan

### Applicable Standards
- N/A

### Definitions, Acronyms, and Abbreviations  
- Game Master - One who sets up the pick up game for the available time slot
- Player - Those who confirm their attendance to the session and verify the game's occurrence.

---------------------------


## Section 2: Product Overview

### Assumptions:
- First assumption is availability of the internet on a mobile platform. This is not completely necessary, but it allows for users to verify events that are going on, which is a core feature of the service.
- Second assumption is the need of an ability to interface with Google Maps. This implies that a feature of this platform relies on the availability of Google Maps.
- The only other assumption that is being made about a user using the system is the use of a modern web browser. This means most specifically Chrome, Firefox, Opera, any modern Android browser (dolphin, chrome, default browser, etc.), any modern iOS browser (Safari, Chrome, etc.) and versions of IE 9+.

### Stakeholders:
- Developers of the platform 
	- This group wants the platform to be successful both for the class and potentially as a platform that could grow in use of UCF students.
- Members of UCF community





### Event Table:  

| **Event Name** | **External Stimuli** | **External Responses** | **Internal data and state** |
| --- | --- | --- | --- |
| **User Account Creation** | Click on "Create an account" button. | Page redirect to login page | Once information is verified client side, hash user password client side, then send all form data to the server. The server then creates a user based off of this information. |
| **User Login** | Click on "Login" button | Page redirect to home page | Username and hashed password is sent server side. If account information is correct, the user is now in a logged in state. |
| **User Login with Facebook** | Click on "Login with Facebook" button. | Page redirect to Facebook's OAuth page. | User logs in with Facebook, and system gets back OAuth token verifying their login. |
| **User Forgot Password** | Click on "Forgot Password" button. | Page redirect to Forgot Password page | User inputs email, and an email is sent to them with a link which redirects them to reset password. |
| **User Forgot Password Reset** | Click on verification link sent to user's email. | Page redirect to password update screen. | User puts in new password and verifies this. This password is hashed, sent to the server, and the server updates user information. |
| **Event Creation** | Click on "Create an Event" button. | Redirect user to Create an Event page | User inputs all information about the event and the information is sent to the server to create the event in the database. |
| **Browse Events List** | Click on "Browse Events" tabs. | Redirect user to Browse Events page | Server queries database for list of events to serve up to the user. |
| **Filter Event Type** | Click on "Filter Events" button and select wanted event. | Bring up filter events modal and allow users to select events they want to see. | User selects a filter, and the displayed list of games are filtered as per the user query (By event type, time of event, etc.) |
| **Showing Intent to Attend** | Click on "Commit to Play" button. | Change Commit to Game button to an icon showing the user has clicked it. Also adds user to "committed user" list on event page. | User is added to the list of committed users client side and server side. |
| **Check In to Event** | Click on "Check In" on the page for that event. | Change Check In button to an icon showing the user has clicked it. Also adds user to "checked in" list on event page. | User is added to list of checked in users client side and server side. User is giving reputation points for this interaction. Game Master gets points for each person that checks in to the event as well. |
| **View User Page** | Click on User's name anywhere it is a link in the application. | Redirect user to page for the user. | Server renders the page and sends it server side. |



### Use Case Diagram
![Use Case Diagram](http://i.imgur.com/vBvHLO3.png)

### Use Case Descriptions:
Each of the use cases in the diagram matches the description in the event table above. A not logged in user does not have the same privileges as a logged in user, and vice versa. A not logged in user must be able to create an account, login with the two available login options, and reset their password in the case that they forgot it. Giving the logged in user the ability to do this is rather redundant, and thus is omitted. The logged in user though is the only one allowed to create games, and show intent to attend and check in. This is only available to logged in users because these actions need to be tied to an account.

All users though can browse events and view other users pages. This allows not logged in users to get a view into what the application does, and gives logged in users access to the core functionality of the application.

---------------------------

## Section 3: Specific Requirements

| No: 1 |
| --- |
| Statement: The system shall allow for the log in /account creation of multiple users simultaneously |
| Source: Concept of Operations |
| Dependency: 6 |
| Conflicts:None |
| Supporting Materials: None |
| Evaluation Method: If a user enters the site and can either create an account or log into an account while a user does the same action |
| Revision History: P.Delva 6/7/2014 Initial Release |

| No: 2 |
| --- |
| Statement: The system display a list of sporting events that the user can create |
| Source: Concept of Operations |
| Dependency: None |
| Conflicts:None |
| Supporting Materials: None |
| Evaluation Method: If a user enters to create an session and there are multiple options for what sport is being played at the time of creation |
| Revision History: P.Delva 6/7/2014 Initial Release |

| No: 3 |
| --- |
| Statement: The system should have the ability to confirm or deny an event is taking place |
| Source: Concept of Operations |
| Dependency: 1 |
| Conflicts:None |
| Supporting Materials: None |
| Evaluation Method: A user should be able to log into a created event and enter a section allowing them to place whether or not a match is in fact taking place |
| Revision History: P.Delva 6/7/2014 Initial Release |

| No: 4 |
| --- |
| Statement: The system should have the ability to provide a map overlay of the UCF campus and pinpoint event locations |
| Source: Concept of Operations |
| Dependency: None |
| Conflicts:None |
| Supporting Materials: None |
| Evaluation Method: Upon entering the website, a user should be able to see all of the locations that matches can be held and where specific events are being held |
| Revision History: P.Delva 6/7/2014 Initial Release |

| No: 5 |
| --- |
| Statement: The system should have the ability to allow users to announce their attendance at an event |
| Source: Concept of Operations |
| Dependency: 4 |
| Conflicts:None |
| Supporting Materials: None |
| Evaluation Method:A user should be able to access an event page and put their name down on the list of attendees |
| Revision History: P.Delva 6/7/2014 Initial Release |

| No: 6 |
| --- |
| Statement: The system should be able to support unique users |
| Source: Concept of Operations |
| Dependency: 1 |
| Conflicts:None |
| Supporting Materials: None |
| Evaluation Method: When a user creates an account they shouldn't be able to create an account with the same email address or username |
| Revision History: P.Delva 6/7/2014 Initial Release |

| No: 7 |
| --- |
| Statement: The system should allow for a user to check into an event |
| Source: Concept of Operations |
| Dependency: 1 |
| Conflicts:None |
| Supporting Materials: None |
| Evaluation Method:Once a user is at the event, they should be able to check in, confirming their attendence |
| Revision History: P.Delva 6/7/2014 Initial Release |

| No: 8 |
| --- |
| Statement: The system should have a point system rewarding members |
| Source: Concept of Operations |
| Dependency: All |
| Conflicts:None |
| Supporting Materials: None |
| Evaluation Method:A user should be given points for select actions like making an account, checking into games, etc. |
| Revision History: P.Delva 6/7/2014 Initial Release |

| No: 9 |
| --- |
| Statement: The system will not allow a user to attend two events at once |
| Source: Concept of Operations |
| Dependency: 1 |
| Conflicts:None |
| Supporting Materials: None |
| Evaluation Method:The system will replace the old event with the new one or cancel the request to attend the new event |
| Revision History: P.Delva 6/7/2014 Initial Release |

| No: 10 |
| --- |
| Statement: The system should allow the user to view other user's history of games and points |
| Source: Concept of Operations |
| Dependency: 1,8 |
| Conflicts:None |
| Supporting Materials: None |
| Evaluation Method:A user should be able to click on a user's name from an event page and have the information displayed |
| Revision History: P.Delva 6/7/2014 Initial Release |

### Functional Requirements

The system should limit potential for input error by using designated input options where possible, and parsing all custom input from user for incorrect formats and syntax using regular expressions. If an incorrect input is entered, system should reject the input and highlight the associated field to alert user of incorrect input.

The exact sequence of operations for a user should be:

1. Create an account with the application
2. Log into the system as a new user
3. Take a "tour" of the website and its features by following interface overlays
4. Browse through upcoming pickup games from the homepage
5. Filter athletic events by sport
6. View a particular event to get more information 
7. Commit to play a game to show other users how many people are planning to attend
8. Participate in game hype in the comments section of the event you have committed to
9. Check-in at the game to let others know there are people there and that the game is happening

Input for the system will be entirely in the event pages. Game masters can upload event information and will be displayed as output for the users through the site as the browse, search, and view details of existing events.

### Interface Requirement

The interface will be required to receive and display all relevant information in a user friendly way. The user input for creating events can be synchronous since each event is a separate entity. Comments will be stored in order of when they were submitted for each event.

The Input:

- Users
  - first name - string (50 chars)
  - last name - string (50 chars)
  - Username/nickname - string (50 chars)
  - email - string (150 chars) (optional)
  - phone number (25 chars) (optional)

- Events
  - game type - dropdown menu
  - "other" game type - String (100 chars)
  - event street number (if applicable) - Integer
  - event street (if applicable) - String
  - event city - String (string 50 chars)
  - date - calendar selection
  - event start time - dropdown menus (15 min intervals)
  - expected event duration - (numerical input dropdown field 15 min intervals)
  - comments - String (500 chars long)

The Output:

- Event page
  - game type
  - event location
  - date
  - start and approximate end time (with duration)
  - pinned-map of the location
  - How many people have committed to play
  - How many people are checked in to the event (once it is the event time)
  - game hype (comments)

- Optional email/text notification
  - what time the game starts
  - game location
  - How many other people have committed to play

- User page
  - username
  - first and last name (if made publicly available)
  - reputation points
  - contact info (if made publicly available)
  - check-in history (if made publicly available)
  - favorite sport (based on previous games checked into)

### Physical Environment Requirements

The software environment for the user is the user's web browser of choice. The development team will support recent releases of chrome, firefox, safari, and IE (version 10 &11 only) browsers. The software will need to be hosted on a server on the UCF subdomain. In the event that we fail to obtain access to the UCF servers, we will look into other options. If no other options are available to us before the due date of the project, we will present our software using local servers on our development machines.

### User and Human Factors Requirements

Every user in the system is a potential player. Therefore, each user has the same set of available options associated with their account. A game master may remove an event only if no other users have committed to play at that event. If any player has committed to the event, the game master for that event should have no option to remove that event from the system. Each player can accumulate "reputation" points for participating as an active member of the athletic community. These points have no effect on the player's account other than displaying how many "rep points" he/she has.

The only training and documentation of the system will be in the form of a walk-through tutorial when the user first joins the site. This will help users understand the functionality of the website and allow them to create and commit to games without confusion.

The system will prevent players from committing to play at multiple events on the same day at the same time. This will happen when a user tries to commit to play an event which overlaps another game. The system should alert the user and not sign him up for the new event.

### Documentation Requirements

Online documentation will be required to sign up. The system requires the users enter sign-up information which may consist of email, facebook, phone number(optional), username(optional), and password. The users of the system should be familiar with how to navigate the web.

### Data Requirements

Our software will not be computation heavy. The computations the system will need to evaluate will be the total of each player's reputation points, each event's "heat" or popularity, how many people have committed to play at an event, how many people have checked in at each event, and whether the event's start date and time have expired or not. The most difficult of these will be determining how much time difference there is untill/since an event starts. We will do this computation in using SQL during database queries to display only events that are useful to our users, and using PHP to send reminders to users that a game they have committed to play in is coming up. Because times are stored in 15 minute increments, all time calculations must be precise to a quarter hour.

### Resource Requirements

Our resource requirements consist of our team of skilled developers to build the system. Once in production, a web hosting platform to make the site accessible for users. This platform should keep its servers at an appropriate temperature so as not to slow down or damage themselves. Ideally, the web hosting service will be free if we are able to access the UCF servers. Additionally, the domain name for the system will cost at most $20/year. The software itself should be under 100MB of storage space, with a growing database. All users must be connected to the internet to access the system. We recommend using the system on a machine with a minimum of 1GBs of ram, and 1.0GHz processor.

### Security Requirements

In order to access and participate in the system, each user must sign on securely with email and password, or facebook credentials. Each user's private information will not be displayed to other users, unless that user has made his contact information publicly available. The database of events, and users, should be backed up to a separate hard drive early each morning, between the hours of 3-5 a.m., so that any interference with the regular functionality of the site may be reduced to minimum impact. In the event of data loss on the main server, the recover drives may be used to restore the system to the most recent available data state.

### Quality Assurance Requirements

Accessibility, portability, reliability, security, and stability are crucial components to a piece of software like gameServe. It is important to our developers that the site is live and fully functional as often as possible. When selecting a hosting service for the site, we will be sure to take into account the reliability statistics of each service, and employ the one that most directly supports the needs of our users. Portability goes hand in hand with accessibility, in order to maximize our potential user population, we have decided to make the software a web application. This will allow users from all types of computing devices to use the system with ease, without making the system exclusive to a certain subset of the UCF community such as strictly desktop, or strictly mobile users.

Ideally, the system should be fully functional a minimum of 22 hours each day. The extra two hours will be set aside for system maintenance and backups, during historically low traffic times. Maintenance to the site should take an absolute maximum of 2 hours. All changes to the site should be extensively tested before going to production, to ensure the site's stability.

## Section 4: Supporting Material
