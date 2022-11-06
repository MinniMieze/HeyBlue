1. [katas](#katas)
   1. [references](#references)
   2. [about](#about)
   3. [rules](#rules)
   4. [presentation](#presentation)
2. [project](#project)
   1. [links](#links)
   2. [sections](#sections)
3. [decisions](#decisions)
   1. [usage platform](#usage-platform)
   2. [maps platform](#maps-platform)
   3. [deployment platform](#deployment-platform)
   4. [software platform](#software-platform)
   5. [data base](#data-base)
4. [wokflows](#wokflows)
   1. [overall workflow](#overall-workflow)
   2. [app installation workflow](#app-installation-workflow)
   3. [user registration workflow](#user-registration-workflow)
   4. [indentity & device matching workflow](#indentity--device-matching-workflow)
   5. [police available for connections](#police-available-for-connections)
   6. [civilian available for connections](#civilian-available-for-connections)
   7. [location retrival workflow](#location-retrival-workflow)
   8. [civilian related meeting workflow](#civilian-related-meeting-workflow)
   9. [police related meeting workflow](#police-related-meeting-workflow)
   10. [reach meeting point workflow](#reach-meeting-point-workflow)
   11. [meeting workflow](#meeting-workflow)
   12. [social media](#social-media)
   13. [shops & charities](#shops--charities)
   14. [usage & analytics](#usage--analytics)
   15. [messaging & notifications](#messaging--notifications)
   16. [unknown](#unknown)

# katas

## references

- [about_architectural_katas](https://www.architecturalkatas.com/about.html)
- [rules_architectural_katas](https://www.architecturalkatas.com/rules.html)

## about

- architectural katas are
  - an excercise involving a small group (3-5 people)
  - usually as part of a larger group (4-10 groups are ideal)
  - each group is given a project that needs development (a different kata)
  - each group architects a solution based on the requirements
- a moderator
  - assigns katas
  - keeps track of time
  - acts as the facilitator for the exercise
  - answers as a "customer" for questions posed by the architectural groups

## rules

- not all rules listed here
- just the important ones

1. architectural solution can utilize any technology
2. list down the assumptions made about technology or other unknown topics
3. needed - clarity of narrative, organization, and supporting documentation

## presentation

- each project team presents a vision of their proposal to the rest of the group
- any questions from other groups are answered
- then the room votes on presentation, and the next project team takes the floor

# project

## links

- github
  - [link](https://github.com/MinniMieze/HeyBlue)
- miro
  - [link](https://miro.com/app/board/uXjVPKX11Kg=/?share_link_id=243062536143)

## sections

- introduction
  - preface about who we are as a team
  - our motivation to be part of this program
- why
  - supporting engagement between law enforcement and citizens in a mutually beneficial manner
  - architecting the solution by placing privacy and security at the centre of it
- how
  - show proposed solution using diagrams
  - simultaneously explain the architecture decision records
- what
  - the tools involved
  - the platform
  - devops and other processes supporting the tool

# decisions

- this section lists down the architectural decision records

## usage platform

- decide
  - which devices and platforms should the app support?
- options
  - android
  - ios
  - wearos
  - watchos
  - tizen
  - many more listed [here](https://en.wikipedia.org/wiki/Mobile_operating_system)
- decision
  - develop ios apps, android apps and website (rendered inside browsers - chromium and firefox)
- why
  - ios and android collectively cover most of the market
  - any other platforms are miniscule in comparison and developing apps for them without any specific hard requirement, is not ideal at this point of time

## maps platform

- decide
  - which maps platform to use
- options
  - google maps platform
  - amazon location service
  - azure maps
- decision
  - use google maps platform
- why
  - the google maps platform provides the most comprehensive set of tools for tracking location, providing directions, storing shop locations, etc.
  - this platform is tightly integrated with the google maps application that is predominantly used by for all navigation purposes across android, ios, web
  - on the other hand, amazon location service and azure maps depend on fetching data from other location services and need elaborate connection and setup
- supporting links
  - google maps platform - [link](https://developers.google.com/maps)
  - amazon location service - [link](https://aws.amazon.com/location/)
  - azure maps - [link](https://azure.microsoft.com/en-us/products/azure-maps/)
  - most popular mapping apps - [statista](https://www.statista.com/statistics/865419/most-popular-us-mapping-apps-ranked-by-reach/)
  - azure maps vs google maps - [comparison](https://comparisons.financesonline.com/azure-maps-vs-google-maps-api)
  - aws location service overview - [link](https://aws.plainenglish.io/all-about-amazon-location-service-725239540dba)

## deployment platform

- decide
  - where should the application be deployed
- options
  - cloud
    - gcp
    - aws
    - azure
  - on-premices
- decision
  - use "Google Cloud for government"
- why
  - better integration of google maps platform with google cloud
  - comes bundled with monitoring and shopping services that are a hard requirement from the customer
  - this offering is specifically targeted for projects bearing involvement of US government and law enforcement agencies
  - the compliance support for US government contracts comes bundled inside "Google Cloud for government"
- links
  - gcp government - [link](https://cloud.google.com/solutions/government)
  - aws government - [link](https://aws.amazon.com/government-education/government/)
  - azure government - [link](https://azure.microsoft.com/en-us/explore/global-infrastructure/government/get-started/)
  - on-cloud or on-prem for us government comparison - [link](https://www.govpilot.com/blog/should-the-public-sector-be-using-the-cloud-or-in-house-servers)
  - data centre or cloud - pros and cons - [link](https://cloudcheckr.com/cloud-management/government-cloud-services-vs-data-centers/)

## software platform

- decide
  - what programming language or software framework should be used
- options
  - swift (ios)
  - kotlin (android)
  - react native & java script (cross-platform)
  - dart, flutter & firebase (cross-platform)
- decision
  - dart, flutter & firebase
- why
  - backed by google and firmly part of the google ecosystem
  - create cross-platform applications using a single codebase
  - dart is easier to learn and work with compared to jsx
  - dart is static and safer as compared to the dynamic js
  - flutter has pre-made widgets that work out of the box with google services
  - react native is a library, it has far fewer ready-to-use widgets and designing an app involves more work and expertise
  - react native uses javascript bridges to communicate with the native code, and bridges can slow app performance down
  - the dart code that flutter uses compiles directly to c and does not require any bridges to communicate with native code - so better performance
  - swift and kotlin are not cross-platform and only targer ios and android respectively
- links
  - swift - [link](https://developer.apple.com/swift/)
  - kotlin - [link](https://developer.android.com/kotlin)
  - react native - [link](https://reactnative.dev)
  - flutter - [link](https://flutter.dev)
  - dart - [link](https://dart.dev)
  - firebase- [link](https://firebase.google.com)
  - compare react native and flutter
    - [logrocket](https://blog.logrocket.com/react-native-vs-flutter/)
    - [kruschecompany](https://kruschecompany.com/flutter-vs-react-native/)

## data base

# wokflows

![](/katas-main.png)

## overall workflow

- registration
  - app installation - install app from play store or app store
  - user registration - create profile on firebase or through another entity
  - one device --> one account - ensure same device is not used for multiple email ids
- police to civilian connection
  - switch on - available for connections
  - location retrival - track location of device and store details
  - wait for civilian to approach for connection
  - chat with civilian and decide on meeting point
  - meet civilian
  - receive points for each meeting
- civilian initiated connection
  - switch on - available for connections
  - location retrival - track location of device and store details
  - check if police officers in vicinity are available for connections
  - initiate chat with a police officer
  - meet police officer
  - provide feedback inside app whether or not the meeting took place
  - optionally provide feedback on social media
  - receive points for each meeting
- point collection system
  - ???

## app installation workflow

### tools

- flutter on android play store - [how-to](https://docs.flutter.dev/deployment/android)
- flutter on ios app store - [how-to](https://docs.flutter.dev/deployment/ios)

### workflow

- user finds the app on the android or apple store
- during installation process, user is asked for permissions
- 2 of the major permissions that are requested are:
  - push notification
  - location sharing
- once app installation is done, then user moves on to registration flow

## user registration workflow

### tools

- Firebase Authentication
  - firebase authentication provides backend services, easy-to-use sdks, and ready-made ui libraries to authenticate users to your app
  - firebase authentication integrates tightly with other firebase services
  - [link](https://firebase.google.com/docs/auth)
- Firebase UI Auth
  - firebase ui auth provides a drop-in auth solution that handles the ui flows for signing in users with email addresses and passwords, phone numbers, identity provider sign in including google, facebook, github, twitter, apple, microsoft, yahoo, openid connect (oidc) providers and saml providers. it is built on top of firebase auth.
  - [link](https://github.com/firebase/firebaseui-web#demo)

### workflow

- once the
- user has the option to create a profile directly on the app by using their
  - phone number or
  - email id
- alternatively, user can decide to create a profile by connecting to popular federated identity providers like google, facebook, twitter, apple, yahoo or even openid
- alternatively, the site admin can invite a new user by creating their identity in the backend like [this](https://firebase.google.com/docs/auth/web/manage-users)

## indentity & device matching workflow

### requirements

- community members must link an email address to a particular phone and not be able to register multiple devices to a particular email address. (hard requirement)

### tools

- blocking cloud functions
  - firebase authentication with identity platform allows us to use blocking cloud functions
  - blocking functions let you execute custom code that modifies the result of a user registering or signing in to your app
  - for example, you can prevent a user from authenticating if they don't meet certain criteria, or update a user's information before returning it to your client app.
- firebase installations service (fis)
  - it provides a firebase installation id (fid) for each installed instance of a firebase app
  - the firebase installation id is used internally to deliver firebase services

### workflow

- registration of new users happens through firebase authentication
- during registration process, each device is allocated a Firebase installation ID (FID)
- if a user tries to register a new account with a device that has already been allocated a firebase installation id, then such installation will fail

### links

- firebase authentication - [documentation](https://firebase.google.com/docs/auth/)
- firebase installations service (fis) - [documentation](https://firebase.google.com/docs/projects/manage-installations)

## police available for connections

### requirements

- officers location must automatically shut off after 15 minutes (hard requirement)

### workflow

- police officer enters app and flips switch that says that they are available for connecting to civilians
- this switch enables location sharing for that device
- this status is automatically switched off after 15 mins

## civilian available for connections

### workflow

- civilian enters app and flips switch that says that they would like to connect to a police officer in the vicinity
- this switch enables location sharing for that device
- user needs to manually switch off this status

## location retrival workflow

### requirements

- location tracking is a hard requirement

### tools

- triangulation
  - ios core location service - [link](https://developer.apple.com/documentation/corelocation)
  - android location apis - [link](https://developer.android.com/training/location)
  - google maps web service - geolocation api - [link](https://developers.google.com/maps/documentation/geolocation/overview)
- tracking
  - geofire - [link](https://github.com/firebase/geofire-js)
  - this open-source library stores & retrives locations within a given geographic area in realtime
  - this is a lightweight add-on to Firebase
- storage
  - cloud firestore - [link](https://firebase.google.com/docs/firestore)
  - it is a flexible, scalable database for mobile, web, and server development from Firebase and Google Cloud
  - it keeps your data in sync across client apps through realtime listeners and offers offline support for mobile and web
  - the database can be accessed directly from a mobile device or web browser; there's no need for an application server

### workflow

1. location tracking only happens after explicit actions/approvals from user (covered in previous sections)
2. ios & android location apis will keep retriving the availability & location of the device
3. this information is then stored inside firebase using geofire and not displayed to all users
4. what gets displayed to each user is covered in the next sections

## civilian related meeting workflow

### requirements

- connecting with other users is a hard requirement
- users can only have one connection per officer per 24 hour period. (hard requirement)

### tools

- firebase in-app messaging - [link](https://firebase.google.com/docs/in-app-messaging)

### workflow

1. when civilian indicates that they want to connect to a police officer, then the map shows all police officers
   1. who are open for connection
   2. with whom the civilian has not connected in the past 24 hours
2. when civilian has identified the police officer they want to connect to, then they send a connection request to the police officer
3. this `connection_status` is saved as a parameter inside the firestore db - allowing the status multiple values like
   1. request_sent
   2. request_accepted
   3. request_rejected
   4. meeting_planned
   5. meeting_canceled
   6. meeting_in_progress
   7. meeting_concluded
   8. meeting_social_feedback_provided
4. civilian and police officer utilize the in-app chat system to decide on a meeting point, meeting time, etc.
5. app provides the ability to update the `connection_status`

## police related meeting workflow

### requirements

- connecting with other users is a hard requirement
- users can only have one connection per officer per 24 hour period. (hard requirement)

### tools

- firebase in-app messaging - [link](https://firebase.google.com/docs/in-app-messaging)

### workflow

1. when police indicates that they want to connect to a civilian, then they show up as available on the map for those civilians
   1. who are open for connection
   2. with whom the police officer has not connected in the past 24 hours
2. when a civilian approaches the police officer for a meeting, then they send a connection request to the police officer
3. the police officer can accept or decline the request - this will update the value of `connection_status`
4. this `connection_status` is saved as a parameter inside the firestore db - allowing the status multiple values like
   1. request_sent
   2. request_accepted
   3. request_rejected
   4. meeting_planned
   5. meeting_canceled
   6. meeting_in_progress
   7. meeting_concluded
   8. meeting_social_feedback_provided
5. civilian and police officer utilize the in-app chat system to decide on a meeting point, meeting time, etc.
6. app provides the ability to update the `connection_status`

## reach meeting point workflow

### requirements

- location tracking is a hard requirement

### tools

- google maps platform's Directions api
  - [link](https://developers.google.com/maps/documentation/directions/overview)
  - Route api - [link](https://developers.google.com/maps/documentation/routes_preferred)
  - Place api - [link](https://developers.google.com/maps/documentation/places/web-service)
- triangulation
  - ios core location service - [link](https://developer.apple.com/documentation/corelocation)
  - android location apis - [link](https://developer.android.com/training/location)
  - google maps web service - geolocation api - [link](https://developers.google.com/maps/documentation/geolocation/overview)
- navigation
  - ios mapkit - [link](https://developer.apple.com/documentation/mapkit/)
  - android maps sdk - [link](https://developers.google.com/maps/documentation/android-sdk/overview)
  - google maps Directions api - [link](https://developers.google.com/maps/documentation/directions/)
- tracking
  - geofire - [link](https://github.com/firebase/geofire-js)
  - this open-source library stores & retrives locations within a given geographic area in realtime
  - this is a lightweight add-on to Firebase
- storage
  - cloud firestore - [link](https://firebase.google.com/docs/firestore)
  - it is a flexible, scalable database for mobile, web, and server development from Firebase and Google Cloud
  - it keeps your data in sync across client apps through realtime listeners and offers offline support for mobile and web
  - the database can be accessed directly from a mobile device or web browser; there's no need for an application server
  - the database can be accessed directly from a mobile device or web browser; there's no need for an application server
- computation
  - cloud functions for firebase - [link](https://firebase.google.com/docs/functions)
  - it is a serverless framework
  - your code is stored in gcp and runs in a managed environment
  - there's no need to manage and scale your own servers

### workflow

1. this workflow is invoked when value if `connection_status` is `meeting_planned`
2. app shows the direction to the meeting point
3. and also showcases the location of the other person (to indicate if they have reached the meeting spot)
4. users can reach the meeting spot by following the [Route](https://developers.google.com/maps/documentation/routes_preferred) to the specified [Place](https://developers.google.com/maps/documentation/places/web-service)
5. at this point of time, the police officer is no longer available for connections
6. app utilizes the google maps api mentioned above, to navigate to the desired location
7. `connection_status` can be updated to `meeting_canceled` or `meeting_in_progress` based on whether the 2 parties meet each other
8. this is covered in next sections

## meeting workflow

### requirements

- a connection can only happen if the community member and the police officer are within a 10 ft distance from each other

### tools

- geolocation
  - google maps web service
  - geolocation api - [link](https://developers.google.com/maps/documentation/geolocation/overview)
- storage
  - cloud firestore - [link](https://firebase.google.com/docs/firestore)
  - it is a flexible, scalable database for mobile, web, and server development from Firebase and Google Cloud
  - it keeps your data in sync across client apps through realtime listeners and offers offline support for mobile and web
  - the database can be accessed directly from a mobile device or web browser; there's no need for an application server
- computation
  - cloud functions for firebase - [link](https://firebase.google.com/docs/functions)
  - it is a serverless framework
  - your code is stored in gcp and runs in a managed environment
  - there's no need to manage and scale your own servers
- user engagement
  - firebase in-app messaging
  - [link](https://firebase.google.com/docs/in-app-messaging)

### workflow

- the firebase realtime database stores the value for `connection_status`
- when the police and civilian meet, both of them need to update the flag within the app to `meeting_in_progress`
- single person updating the flag does not change its value
- the value remain `meeting_planned` till then
- after a certain period, if the value does not turn `meeting_in_progress`, then the status is marked as `meeting_canceled`
- a geolocation check is done before value turns `meeting_in_progress`
- the Geolocation API returns a location and accuracy radius based on information about cell towers and WiFi nodes that the mobile client can detect
- if both users are not within 10 feet of each other, then the value can not be set to `meeting_in_progress`
- once the meeting is concluded, then both participants need to manually update the `connection_status` value to `meeting_concluded`
- at this point, civilian is offered to login to a social media site of their choice and post about this meeting - this workflow is shown in next sections
- all these activities related to updating meeting status is handled in a very user-friendly way using - firebase in-app messaging

## social media

### requirements

- Uploading to social media is a Hard Requirement
- Connectivity to Users Social Media is an option

### tools

- firebase in-app messaging - [link](https://firebase.google.com/docs/in-app-messaging)
- flutterfire widgets - [link](https://firebase.flutter.dev/docs/ui/widgets/)
- android webview - [link](https://developer.android.com/reference/android/webkit/WebView#basic-usage)
- ios webview - [link](https://developer.apple.com/documentation/webkit/wkwebview)

### workflow

- this workflow is invoked if `connection_status` value is set to `meeting_concluded`
- if user agrees to provide feedback on social media about the meeting, then the app starts the social media authentication workflow
- if user is already not authenticated at the desired social media (facebook, twitter, etc.), then utilize the FlutterFire UI to perform this oauth
- then use webview_flutter, WebView_android & WKWebView_ios to display an in-app webview that takes user to the social media page to make a post
- in the post, the user provides feedback about their meeting
- once done, user is gracefully sent back to the native app

## shops & charities

- the platform must provide a way to allow civilians to find retail establishments where they can redeem their points
- the platform must provide a way to allow officers to find charities where they can gift their points
-	allow businesses/charities to create a storefront on the app to encourage users to redeem or donate their points
-	businesses should have a catalog of items that they are offering and the point value assigned to each item available

### tool

<https://mapsplatform.google.com/maps-products/#places-section>

## usage & analytics

### requirements

- web and mobile-based with back-end processing and reporting and analytics that tracks site activity, connections
- analytics can take app data and aggregate it with other available public data to build comprehensive reports to show impact of app in community
- tracking engagement is a hard requirement

### tool

- Google Analytics
- capabilities
  - what is happening in your app, such as user actions, system events, or errors
  - measurement of user interactions with products across your users' shopping experiences, including interactions such as product (item) list views, product list clicks, viewing product details, adding a product to a shopping cart, initiating the checkout process, purchases, and refunds

### links

- google analytics for flutter & firebase - [link](https://firebase.google.com/docs/analytics/get-started?platform=flutter)
- google marketing platform - [link](https://marketingplatform.google.com/about/analytics/)

## messaging & notifications

### requirements

- the ability to opt in to and out of push notifications is a hard requirement

### tool

- Firebase Cloud Messaging
- capabilities
  - cross-platform messaging solution
  - send messages at no cost
  - push notification at app level (android and ios)

### workflow

- push notification for police officers once a user has selected that police office for an interaction
- push notification to both users and police officers when

### links

- [firebase notifications](https://firebase.flutter.dev/docs/messaging/overview)

## unknown

- Twilio
  - provides programmable communication tools for making and receiving phone calls, sending and receiving text messages, and performing other communication functions using its web service APIs
  - connect with customers on their preferred channels e.g. SMS and WhatsApp messaging, voice, video, and email
  - [website](https://www.twilio.com)
  - [wikipedia](https://en.wikipedia.org/wiki/Twilio)
