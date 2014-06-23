---
layout: post
title: "Concept of Operations"
description: "Phase 1"
category: Phase 1
tags: [phase1]
tagline: "Phase 1"
---
{% include JB/setup %}


## The Current System  
The current system by which users can plan and organize meet-ups for sporting events are through manual communication within the users’ known social circles, through joining games in session at the location of the event, or through social networking platforms such as Facebook and Foursquare.    

Although Foursquare and Facebook are mediums by which users can share their current location to users within their social network, it does not specifically provide the functionality of organizing pick-up games for sporting events. If a user announces a sporting event through Foursquare or Facebook, other users would need to take it upon themselves to decide whether or not to join the person. The features provided by Facebook for planning and organizing events are not suitable for short time span and spontaneity by which “pick-up” games are planned and executed. 

----------------------------------

## The Proposed System

### Needs
This system is extremely applicable in the university environment. This system allows students and other members of the university system to meet up with people who have similar athletic interests with one another. This system is entirely free and available for anyone who either wishes to create an account for the system, or even those people who have a Facebook that they wish to connect to the system. To make this even more available, this is developed on a website platform so that users of any operating system/platform can access it.

People do not necessarily need this system, but as previously mentioned, it allows for people to connect with those of similar interests on short term notice. As a whole, the university setting benefits from applications that allows members of the communities to get together and meet others. In terms of ease of use, it will be made with the end user in mind. This is so that people can find the games they want to play when they want to play them. 

### User Types and Modes of Operation
- User Types
	- Game Master
		- Creates events, sets up location and time, publicizes game. 
		- Normal players when searching, responding, and verifying games that they did not create.
	- Player/Voter
		- Able to verify games, attend games, and commit to play at games. 
		- Participant
- Modes of Operation
	- Game Creation
		- Allows the game master to create a new event. 
		- Game master must input information about desired event time and location and an optional difficulty level.
	- Game Information Session
		-  This will be a particular event’s game information page. 
		- Enables users to view event details, verify the game, and commit to attend.
	- Search/Browse
		- Mode in which users have the ability to filter through types of games in a localized area to meet their particular athletic preferences.

### Operational Scenarios
The purpose of our system is to provide a medium for athletes of all skill levels to easily find and participate in sporting events around the UCF campus. By creating an account in our system, new users will have access to view potentially hundreds of athletic events, commit publicly or privately to attend those events, interact with people who share similar athletic interests, verify events have started once they are at the specified venue, and even build an athletic reputation among the GameServe’s community.

A student, Jackie, may decide she wants to play softball, but since softball is very difficult to play with any fewer than nine players on each team, she has a hard time getting enough people interested in order to get a real game going. Jackie is the ideal person for this software. In our system, Jackie would first create an account, then she could search by sport type for softball and browse through the upcoming or in-session events for that sport. If Jackie finds an event happening that she would like to attend, she can commit to going, which will increase the popularity of the event, indicating to other users how many people plan to attend.

If she does not find an event that suits her athletic needs,  she is able to schedule a new event from scratch. Once her event is created, other users can sign up to participate at her event. When the event time and day come around, all the users who have said they planned to attend will meet up at the event’s specified location, verify for others that other participants have shown up and begin playing a game with people that otherwise would not have even had an opportunity to meet.

In the event of an error, the system should recover to the best of its ability. We will eliminate the possibility for input errors for time by implementing drop down inputs for the date and time fields for an event. All information will be stored in a database so if the internet is down for a user or the host, the event information will be retained in the system and content should be restored when the network service is restored.

### Operational Features  
#### Must-Have
- User login system (Email/password or Facebook)
- Ability to store, and update unique user data.
- Ability to store, update, and delete unique game events.
- Upcoming game event information viewable to all users.
- Ability to browse and sort through list of future games.
- Functionality for users to let others know that they are planning to attend a particular sporting pick up event (called “Commit to play”). 
	- NOTE: Players should only be able to commit to play to an event if he/she has not already committed to another event during the same time period. 
- Ability to confirm an event is taking place. 
	- NOTE: A user should be able to verify an event only if he/she has previously “committed to play” at that event. Also, games will only be verifiable starting 30 mins before an event and ending after the event’s duration has passed. 
- Map overlay of University of Central Florida campus and pinpoints of event locations. 
- User reputation point system. 
	-  The system should distribute “rep” points to users for attending games, creating events, increasing a game’s popularity and gives user more incentive to use the system.

#### Would Like To Have
- A popularity meter based on user interest in a particular event (based on how many have indicated they plan to attend, how many have “verified” the event, and how many mentions the event gets in the software’s community. 
- Ability to comment on a particular event for the community to share additional information.
- Ability to invite users (and people not apart of the system) to a particular event.
- Ability to view the pages of other user’s in the system.
- Ability to send notifications to users who are subscribed to certain types of events. 
- Optional text message/e-mail notification sent to players before game time.
- Alert when creating a new game when there is an existing game of the same type and similar time to let game master know he could commit to a game rather than start a new one. 


### Implementation
The architectural pattern for developing the user interface can follow the commonly used Model-View-Controller design pattern.

- Model  
	- Implemented through a SQL database which will store the data of the application; state of objects and user data.
- View 
	- Structured using HTML complimented by it’s layout defined through CSS (SCSS); 
	- Generated by Controller
- Controller
	-  Implemented through Javascript and PHP along with the libraries available.  Javascript will provide the client-side functionality and PHP will provide server-side functionality.

We will be developing the software on Mac OS X and Windows 8.1. Each member of our group will code with their editor of choice. The list includes: Sublime Text 2,  Vim, Notepad++, and Brackets. A local install of apache will be employed to host and test our project.

In an attempt to not limit our application to desktop or mobile platforms exclusively, the system will be a web application accessible from desktops, laptops, tablets, smart phones, and other mobile computing devices.

Because our project is a web application, the software will be available on the internet and will require an internet connection to use. Our team will be sure to develop the site with all major browsers (Chrome, Firefox, Safari, and IE 9 & 10) in mind.

We have decided to tailor our system specifically for use by the UCF community, and strictly for events on the campus of UCF. Though the software will be live on the internet and accessible from anywhere in the world, some of its features (such as setting up a pickup game at an off-campus arena) may not be fully supported outside the geographic bounds of the system’s intended purpose.

One disadvantage to our system is that the subset of the UCF population with smart phones will be required to use the mobile browser to access the program rather than simply clicking on native smart phone app. Though this may be seen as inconvenient by some in this sample population, it will still be accessible to those by using a mobile browser from their phone.  We think this is the best solution to the accessibility problem. By developing on the web, we are not excluding desktop, or laptop users who do not have a smartphone from using our software, like we would have if we had developed an exclusive android or Apple application.  However, this limitation can be overcome through integrating the application using Apache Cordova.

Another disadvantage of our system is that we depend on the internet to be working on our mobile devices. In the event of an mobile network outage, our hand-held users will be unable to connect and interact with our system. Unfortunately, this is a disadvantage we can not control, but by encouraging users to search and sign up for games before event times, we can lower the impact that these kind of problems create for our users.



