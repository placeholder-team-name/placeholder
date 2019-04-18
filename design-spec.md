# Design Specification

## Problem
College students lack the time and energy to keep their family updated. Their family can follow them on social media. Unfortunately, the content their loved one posts on there is not always an accurate reflection of life. Few people consistently post when they have good news to share, and even fewer people choose to share when life is not going their way. Yet it is the unfiltered sharing of these highs and lows that drives connection.

Especially parents cannot wait to hear from their children. We talked to several parents and found that they want to know about serious topics, such as what's bothering their child, as well as the seemingly banal, like 'Is my child eating well?'

The good news is that many college students already crave sharing more honestly. Many of them have 'Finstas', secondary Instagram accounts on which they talk in depth about what's on their mind. Our challenge is to give students the tools to easily extend this information to their family members.

## Solution
Our hypothesis is that regular, unfiltered sharing of information fosters connection. Our app will help college students do that by making writing a monthly newsletter easy. Students add to this newsletter throughout the month. Our app will also occasionally prompt them to do so. At the end of every month, the app asks students to send the newsletter to their family members and start on next month's update. The student's family members will feel closer to them. Before, they only heard from their loved one approximately every half year. Now, they hear about their highs, lows, and day-to-day every month.

College students have limited limited time and attention. They are also frequently in distracting environments. Family quickly falls off as a priority. We need to motivate students to a) want to come back to our app and b) actually come back to it. Our app does that by making the writing process easy and fun. On top of this, it uses push notifications to occasionally remind students to check in. One of our focuses is fault tolerance. It is unrealistic to expect students to write on a daily basis, and students will sometimes forget to send their monthly newsletter. Our app keeps this in mind and helps students finish their newsletter in spite of what comes up in their lives.

## The Five Modules
We can split up our design in five modules:

* Login
* Write and Preview
* Recipients
* Send
* Push Notifications

### Module #1: Login
Users have to log in when they use our app for the first time. We will ask them to sign in with Google to make it easy for them as well as ourselves. Hence, there is no 'Forget Password' flow. The only overhead comes from the user being able to prematurely quit the sign-in process.

<img src="http://downloads.vincentmvdm.com/login.jpg" width="320" />
*splash screen, login screen, login screen - user cancelled Google login, session expired*

### Module #2: Write and Preview
We need to make it as easy as possible to fill the email with good content. We do this by subtly guiding the user's writing process via prompts. These prompts change based on day of month and time of day. We support the most important types of content: text and images.

<img src="http://downloads.vincentmvdm.com/write-preview1.jpg" width="320" />
*write - empty state, write - user added content, write - user added content and came back on a different day, write - user tried uploading image but it's too big*

<img src="http://downloads.vincentmvdm.com/preview1.jpg" width="320" />
*preview - user views content so far, preview - empty state*

### Module #3: Recipients
Users need to control who receives their email. Every family member gets the same email. Users should only have to write someone's email once. That is why we give them access to a recipient list. From a design perspective, there's many states to the recipient list because the user's input needs to be correct.

### Module #4: Send
Students should be able to send their email at any time. Our app prompts them when the month is almost over. A lot can go wrong while sending the email. The app notifies users when their email failed to send and offers them to retry.

### Module #5: Push Notifications
The app uses push notifications to remind students to work on their newsletter and ultimately send it. The student's OS determined the look and feel of these notifications. Our challenge is their contents.
