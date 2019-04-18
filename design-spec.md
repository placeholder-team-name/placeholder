# Design Specification

## Problem
College students lack the time and energy to keep their family updated. Their family can follow them on social media. Unfortunately, the content their loved one posts on there is not always an accurate reflection of life. Few people consistently post when they have good news to share, and even fewer people choose to share when life is not going their way. Yet it is the unfiltered sharing of these highs and lows that drives connection.

Especially parents cannot wait to hear from their children. We talked to several parents and found that they want to know about serious topics, such as what's bothering their child, as well as the seemingly banal, like 'Is my child eating well?'

The good news is that many college students already crave sharing more honestly. Many of them have 'Finstas', secondary Instagram accounts on which they talk in depth about what's on their mind. Our challenge is to give students the tools to easily extend this information to their family members.

## Solution
Our hypothesis is that sharing information 

Our app will help college students stay in touch with their family by making it easy for them to write a monthly newsletter about their life.


 This newsletter gives an 





We are going to help students stay in touch with their family by building a web app. Our app helps students author a monthly newsletter about their life. At the end of every month, the app will prompt students to send the email to their family members. The result is that these family members will feel closer to the student. Before, they only heard from their loved one every half year. Now, they hear about their highs, lows, and day-to-day every month.






## Designing Against Time
Our audience is college students. They have both limited time and attention and are frequently in distracting environments. Family can quickly fall of as a priority, which is why the problem exists in the first place. Our biggest challenge is solving our problem in spite of these constraints. We need to motivate students to a) want to come back to our app and b) actually do so. Our design needs to be fault tolerant. For example, a student who works on a newsletter an entire month but forgets to send it on the last day should be able to finish their work regardless and quickly start on the new month.

## The Five Modules
We can split up our design in five modules. Every module consists out of multiple screens and can become more simple or complex based on where we are in the month as well as the user's progress. The five modules are:

* Authentication
* Authoring Experience
* Contact Management
* Handoff
* Push Notifications

### Module #1: Authentication
Users have to sign in when they use our web app for the first time. To make it easy for ourselves as well as the user, we will ask them to sign in with Google. For this reason, there is no need for a 'Forgot Password' flow (module). The only overhead comes from the user being able to prematurely quit the sign-in process.

### Module #2: Authoring Experience
Besides getting the user to come back to our app and making sure they send an email once a month, the email's content is the most important. The 'Authoring Experience' is about making writing as easy as possible by subtly guiding the user's writing process. We do this using prompts that change based on day of the month and the time user checks our app. Since we do not have a lot of time, we will focus on enabling the most important types of content: text and images. On top of this, we allow users to insert weather information because our research has shown parents are interested in minuite details like this.

### Module #3: Contact Management
Users need to control where their email goes. Every family member will receive the same email in our MVP. The list of family members is unlikely to change, which is why users should not need to specify it every time they want to send an email. That would also increase an email's completion rate. Contacts are complex because they need to support CRUD operations (update, delete, etc.) and the user's input can contain mistakes.

### Module #4: Handoff
Students should be able to send their email at any time in the month. Our design needs to support the user manually deciding to send their email, and our app prompting them to send it when the month is almost over. It's in the handoff face that we need to be fault tolerant. A student who missed the 'deadline' by a few months should still be able to send their work.

There is some complexity from an interopability perspective. There is no guarantee that a user's email gets sent successfully. That is why we need to notify users when we failed to send their email and offer them to retry.

### Module #5: Push Notifications
We will use push notifications to remind students to work on their newsletter throughout the month and ultimately send it. We will rely on the OS' push notifications, meaning that from a design perspective the only challenge is the content.

## Creative Inspiration
