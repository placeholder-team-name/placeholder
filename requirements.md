# Requirements

## Global
* The software will have a palette enforced throughout all views of the application, which will be determined later.
* The software will adhere to all Web Content Accessibility Guidelines.
  * The software will never have any view containing a contrast ratio of below 4.5:1
* All UI text will be black or white, chosen by whichever has a better contrast ratio.

## Login/Logout
* Once the app opens, a splash screen with our logo with text is displayed at the center of any screen for half a second.
* After the aforementioned half a second, the logo will animate and move upwards to the top quarter of the screen, with a “Continue with Google” button taking its place if user is not signed in.
* The “Continue with Google” button has the application’s primary color (which has yet to be determined), will change the user’s cursor to a pointer on desktop devices, and will be darkened on mousedown/touchdown on top of the button. 
* When the “Continue with Google” button is clicked on, the page will redirect to Google’s sign in page. Upon successful sign in, the user will be redirected to the application.
* Software's user registration and sign in must be handled by Google authentication. The user is authenticated once signed in.
  * Because the sign in process uses Google authentication, the software does not need to worry about any forgotten password flows.  
* If the login process has an issue, an error message appears under the “Continue with Google” button saying “Something went wrong! Please try signing in again.”
* If the user’s session has expired, the user will be brought back to the login screen, without having the splash screen animation, and there will be an error message under the “Continue with Google” button saying “Your session has expired. Please sign in again.” that persists until the user tries again
* After the user has logged in successfully, the software will show a loading spinner in the middle of the page while the software loads the user’s content from the online database. While loading, the heading bar and navigation bar on the bottom will be displayed by the software.
  * This heading bar has the current month and year with full month name and 4 digits of the year format.
  * If the user content downloading from the online database has hit any error, a message saying “Oops! An error occurred.” will appear where the write and preview content should appear (defined below). Under the “Oops! An error occurred.” message, there is a button that will refresh the page with the text “Refresh page”. The error message persists until the user hits the refresh button.
* The heading bar additionally has a button on the top right that when pressed will show a dropdown where the user can choose to log out.

## Write and Preview
* The user must be authenticated to see the write and preview page.
* Once the content has finished downloading, the software immediately shows the current user’s write tab, explained below.
* The notebook menu has a “write” and “preview” tab that the user can choose. The default tab is “write”. 
* In the Write tab, there is an insert image button as well as a send button right above the navigation menu at the bottom. This insert image button is a picture icon, while the send button just has the text “SEND” (functionality defined below)
* If the user has not input anything for that day, the software will guide the user’s writing process by providing a prompt in gray text in the Write tab. 
* These prompts are season and time appropriate by being based on the day of month and time of day.
* When the user clicks on the “insert image” button, the user’s native image selector appears.
* The software will use a third party rich text editor that allows for images to be uploaded and text to be bolded and styled.
  * Specifically https://www.npmjs.com/package/react-draft-wysiwyg
* Software must support input of plain text and all images towards the user's newsletter.
* If the user’s image is greater than 10 MB or there is an error uploading the image, an error box will appear over the write content and above the “send” button that says “Failed to upload image” along with “Image too big” if the image was too big or “An error occurred” if an error occurred.
* Software must allow the user to see the contents of their notebook for the current month under the Preview tab.

## Recipients
* Software must allow authenticated users to add contact information containing name and email to their list of recipients under the Recipients page (accessible through the nav bars).
* App will alert the user on current screen if duplicate recipients are added as well as any emails that are invalid for a recipient
* All recipients will have a first name and email address. Last name is optional.
* App will alert the user on current screen if recipient is missing any required fields and will persist until user fixes issue.
* Software must allow the user to edit recipients at any point the user wants to using by tapping on the recipient.

## Send
* Software must allow authenticated user to send their notebook with all the data from the user’s current month as an email at any time before the end of the current month
* Software notifies user by a push notification (or popup on startup if push notifications are disabled) when their email fails to send and will prompt them to try again.
* Software must prompt as push notification (or popup on startup if push notifications are disabled) to user when the month is almost over as well when the month is over allowing the user to send the email
* Software shows a preview of the email to the user and requires user to hit a confirmation button on the header bar before formally sending
* The software must send a responsive output of the notebook in the email, mirroring the contents of the preview tab, to a recipient list that the user defines.

## Push Notifications
* Software must prompt the authenticated user to receive any and all push notifications from the application.
* The software will still allow usage of the application without push notifications, but will notify the user to enable them on startup.




