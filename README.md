# Summary
This script will run every 5 minutes to import an email message that have been "Flagged" in Apple Mail to Things 3.

It includes a link to the flagged email that when clicked (or tapped in iOS Mail) opens the message.

This allows you to easily recall the message that built the Things todo without copying the content itself.  

This project includes an AppleScript that does the Mail -> Things To Do creation and a LaunchAgent to schedule the task for startup and to run every 5 minutes.

Hope you find it helpful!

# Requirements
* Things 3 (or later) for Mac
* macOS 10.4 or later 

# Installation
1. Download repository to your mac
2. Edit "Things3_Import_Script.scpt" and replace the Mail "Account" with the name of the Mailbox you want to monitor for flagged messages.
3. Move "Things3_Import_Script.scpt" to somewhere in your home directory, e.g. ~/Library/Documents
4. Edit "com.vlasach.MailToThings.plist" and modify the path parameter to include the full path leading to "Things3_Import_Script.scpt"
5. Move "com.vlasach.MailToThings.plist" into ~/Library/LaunchAgents/
6. In Terminal, set the LaunchAgent to occur at startup and start running immediately: `launchctl load ~/Library/LaunchAgents/com.vlasach.MailToThings.plist`

# Testing
After modifying the AppleScript, you can test things are working by launching it in Script Editor.  Flag a message then execute a script.  If all goes well the To Do will be created in Things.

