# Requirements

## Global
- [x] The software will have a palette *that looks generally consistent* ~enforced~ throughout all views of the application, which will be determined later.
  - **COMPLETE** Although basic, because our focus was development, our app follows a black/white/blue color scheme. We use styled-system in combination with a theme.js file to enforce our design system.
- [x] The software will adhere to ~all~ *as many* Web Content Accessibility Guidelines *as possible*.
  - **IMPOSSIBLE SO REVISED** We needed to spend more time on providing actual functionality to the application, and thus would not have time to spend on adhering to ALL the web content accessibility guidelines. We tried our best to make the application generally accessible. The problem with the original requirement and the word "all" is that it would take an entire engineering team several weeks to do.
  - [x] ~The software will never have any view containing a contrast ratio of below 4.5:1~
  - **COMPLETE**
- [x] ~All UI text will be black or white, chosen by whichever has a better contrast ratio.~
  - **COMPLETE BUT REMOVED** We completed this requirement, but it is arbitrary. Some of the best apps do not use purely black or white text. Instead, they mix black with colors like blue (see GitHub itself).

## Login/Logout
- [x] ~Once the app opens, a splash screen with our logo with text is displayed at the center of any screen for half a second.~
  - **REMOVED** because this requirement is from when we were planning on making a mobile app. It would not make sense to have a splash screen for a desktop application because there are no dependencies that would take that long to load compared to a mobile application. 
- [x] ~After the aforementioned half a second, the logo will animate and move upwards to the top quarter of the screen, with a “Continue with Google” button taking its place if user is not signed in.~
  - **REMOVED** because of the same reason as the last one.
- [x] The “Continue with Google” button has the ~application’s~ Google's primary color ~(which has yet to be determined)~, ~will change the user’s cursor to a pointer on desktop devices, and will be darkened on mousedown/touchdown on top of the button.~
  - **REVISED** we use Google's colors to meet their brand requirements and did not deem hover effects important enough from a UX perspective to implement.
- [x] When the “Continue with Google” button is clicked on, the page will ~redirect to~ pop up Google’s sign in page. Upon successful sign in, the user will be ~redirected~ taken back to the application.
  - **REVISED** because a pop up window with Firebase is more supported than a redirect sign in and is just as convenient. 
- [x] Software's user registration and sign in must be handled by Google authentication. The user is authenticated once signed in.
  - [x] Because the sign in process uses Google authentication, the software does not need to worry about any forgotten password flows.  
- [x] ~If the login process has an issue, an error message appears under the “Continue with Google” button saying “Something went wrong! Please try signing in again.”~
  - **REMOVED** because we cannot detect expired sessions since Firebase automatically logs out the user for us. 
- [x] ~If the user’s session has expired, the user will be brought back to the login screen, without having the splash screen animation, and there will be an error message under the “Continue with Google” button saying “Your session has expired. Please sign in again.” that persists until the user tries again~
  - **REMOVED** because firebase deals with this functionality for us and if we wanted to truly keep track of it we would have to use cookies to keep track of the last state the user on, etc, but this is a worthless requirement and is thus not worth investing time into creating.
- [X] After the user has logged in successfully, the software will show a loading spinner in the middle of the page while the software loads the user’s content from the online database. While loading, the heading bar ~and navigation bar on the bottom~ will be displayed by the software.
  - **REVISED** Navigation bar and heading bar are now the same since we are not creating a mobile application.
  - [X] ~This heading bar has the current month and year with full month name and 4 digits of the year format.~
  - **REMOVED** Displaying the month/year at all times is distracting and suboptimal use of a navigation bar. It does not fit into our vision of supporting different email cadences (every day, every month) in the future. Someone who sends an email every day doesn't care which month it is.

  - [X] If the user content downloading from the online database has hit any error, a message saying “Oops! An error occurred.” will appear where the write and preview content should appear (defined below). Under the “Oops! An error occurred.” message, there is a button that will refresh the page with the text “Refresh page”. The error message persists until the user hits the refresh button.
  - **REVISED** To make the authentication module incredibly easy to work with for developers (see our useAuth hook), we automatically sign users out and redirect them to the home page when an error occurs. In the case of an error while signing in, we display it on the home page.

- [x] The ~heading bar~ *settings menu* additionally has a button ~on the top right that when pressed will show a dropdown~ where the user can choose to log out.
  - **REVISED** Just moved around to the settings menu because logging out is fairly rare.

## Write and Preview
- [x] The user must be authenticated to see the write and preview page.
- [x] Once the content has finished downloading, the software immediately shows the current user’s write tab, explained below.
- [x] The notebook menu has a “write” and “preview” tab that the user can choose. The default tab is “write”. 
- [x] In the Write tab, there is an insert image button ~as well as a send button right above the navigation menu at the bottom~. This insert image button is a picture icon~, while the send button just has the text “SEND”~ (functionality defined below)
  - **REVISED** because we have redesigned the page slightly to not have a navigation menu at the bottom, but rather the top. It is a small difference. The Send Button belongs in the Preview mode. It will not show up in the Write tab. This was for confirmation purposes describes below.
- [x] If the user has not input anything for that day, the software will guide the user’s writing process by providing a prompt in gray text in the Write tab. 
- [x] These prompts are season and time appropriate by being based on the day of month and time of day.
  - **COMPLETE**
- [x] When the user clicks on the “insert image” button, *then the file selection,* the user’s native image selector appears.
  - **REVISED** Because the React draft wysiwyg library doesn't allow for immediate file insertion, it allows the user to enter a URL as well.
- [x] The software will use a third party rich text editor that allows for images to be uploaded and text to be bolded and styled.
  - [x] Specifically https://www.npmjs.com/package/react-draft-wysiwyg
  - **COMPLETE**
- [x] Software must support input of plain text and all images towards the user's newsletter.
  - **COMPLETE**
- [x] If the user’s image is greater than 10 MB or there is an error uploading the image, an error box will appear over the write content and above the “send” button that says “Failed to upload image” along with “Image too big” if the image was too big or “An error occurred” if an error occurred.
  - **COMPLETE**
- [x] Software must allow the user to see the contents of their notebook for the current month under the Preview tab.
  - **COMPLETE**

## Recipients
- [X] Software must allow authenticated users to add contact information containing name and email to their list of recipients under the Recipients page (accessible through the nav bars).
  - **COMPLETE**
- [X] App will alert the user on current screen if duplicate recipients are added as well as any emails that are invalid for a recipient
  - **COMPLETE**
- [X] All recipients will have a first name and email address. Last name is optional.
  - **COMPLETE**
- [X] App will alert the user on current screen if recipient is missing any required fields and will persist until user fixes issue.
  - **COMPLETE**
- [X] Software must allow the user to edit recipients at any point the user wants to using by tapping on the recipient.
  - **COMPLETE**

## Send
- [x] Software must allow authenticated user to send their notebook with all the data from the user’s current month as an email at any time before the end of the current month
 - **COMPLETE**
- [x] Software notifies user by alerts under the Send Button ~a push notification (or popup on startup if push notifications are disabled)~ when their email fails to send and ~will prompt them to try again~ the Send Button will not be disabled for the purpose of the option of resending.
  - **IMPOSSIBLE SO REVISED** The SendGrid API that we are using does not properly have a way to do this. Email failures can't be notified to us in a manner that we can realistically implement within weeks. Instead we will show Errors from the API or any errors with Sending below the Send button if there are any. 
- [x] Software must prompt as push notification (or popup on startup if push notifications are disabled) to user when the month is almost over as well when the month is over allowing the user to send the email
  - **REVISED** For testing purposes this is impossible to test unless we wait till the end of the month. However the functionality is there.
- [x] Software shows a preview of the email to the user and requires user to hit a confirmation button on the header bar before formally sending
  - **REVISED** Technically the preview functionality is the Preview button. Only after clicking the Preview button, the user can Send, which acts as a confirmation itself.
- [x] The software must send a responsive output of the notebook in the email, mirroring the contents of the preview tab, to a recipient list that the user defines.
  - **COMPLETE** The contents of email can be viewed in the email sent to recipients.

## Push Notifications
- [x] Software must prompt the authenticated user to receive any and all push notifications from the application.
  - **COMPLETE**
- [x] The software will still allow usage of the application without push notifications. ~but will notify the user to enable them on startup.~
  - **REVISED** For better user experience, we do not prompt the user again after the initial prompt. They can go back to the settings to re-enable them.
