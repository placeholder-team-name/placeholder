# Design Specification

## Problem
College students lack the time and effort to keep important people in their lives updated, especially their family members. Existing social solutions only cover brief, filtered moments in life which are tailored for a narrow audience. This creates a communication gap between students and their family members, making it hard to maintain this important relationship.

TODO: Refine and add proof

## Solution
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

## Module #1: Authentication
Users have to sign in when they use our web app for the first time. To make it easy for ourselves as well as the user, we will ask them to sign in with Google. For this reason, there is no need for a 'Forgot Password' flow (module). The only overhead comes from the user being able to prematurely quit the sign-in process.

## Module #2: Authoring Experience
Besides getting the user to come back to our app and making sure they send an email once a month, the email's content is the most important. The 'Authoring Experience' is about making writing as easy as possible by subtly guiding the user's writing process. We do this using prompts that change based on day of the month and the time user checks our app. Since we do not have a lot of time, we will focus on enabling the most important types of content: text and images. On top of this, we allow users to insert weather information because our research has shown parents are interested in minuite details like this.

## Module #3: Contact Management
## Module #4: Handoff
## Module #5: Push Notifications
