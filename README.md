# rumpshaker
Zoom Vulnerability URL path that allows an unauthenticated attacker to guess a meeting room id. Successful exploitation may lead to sensitive information disclosure as well as access to a valid meeting id.     

Code: N/A













# Zoom Meeting Vulnerability & Best practices guide.

Zoom meetings have an inherent vulnerability that allows an actor to guess the Meeting ID and gain access to the meeting room.  Once the Meeting ID is obtained the actor can use the meeting room to host their own meeting and utilize any extra services that might be enabled. One of these services is the call back feature, this allows a meeting attendee to initiate an outbound call from Zoom to a mobile or landline number.  The caller receives an automated message that the call is from Zoom and if they want to join the meeting to press 1. Once the caller is connected to the room the Meeting ID’s organization is charged a per min fee for this connection. Potential abuse and fraud could also occur if the actor would be able to call a pay per call number. This would allow an actor to call a pay per call number that they control and press 1 to initiate a pay per minute fee of their own.  More information about Zoom rates can be found here. https://zoom.us/zoomconference/rates

Another issue would be that Meeting IDs also contain sensitive information about the meeting owner, organization,when the meeting will occur, how to dial into the meeting and what the meeting topic is about. Some examples of potential sensitive information may include: 
* Potential business acquisitions 
* Company operations
* Breach investigation 
* Health and patient information
* School Classroom details

It should be noted that calling into a meeting via a toll free number or toll based numbers are also charged back to the organization under the same rates discussed earlier.

The vulnerability is stealthy enough to obtain sensitive information without even connecting to the meeting itself. Utilizing a specially crafted web request to the zoom platform all the details of the meeting is provided back to the actor. Zoom’s throttling protections to prevent an actor from guessing multiple Meeting IDs is easily defeated by 'low and slow' techniques as well as dynamic addressing. Zoom’s newest feature ‘waiting room’ is also vulnerable to exposing sensitive information even when the host has not even allowed the participant into the meeting. The only sure way to defeat this attack is the lock down the room with a password. There are other options that you would have to use in combination with allowing or removing unauthorized participants. Each organization and or user will need to understand that without the use of a password or preventing participants from joining before the host any information listed within a meeting can be potentially exposed. 

Some ways to protect yourself and your organization:
* Use the 'Generate Automatically' Meeting ID option when creating a meeting. This allows you to delete the meeting once you are finished using it. 
* Review past meetings and delete those meetings that have occurred in the past. https://zoom.us/meeting?type=previous 
* Require a meeting password when possible. This should be enabled by default as a new customer or a trial user. Legacy organizations will need to check their administration settings to make sure this is enabled. You can also enable ‘Embed password in meeting link for one-click join’, this prevents an actor from accessing your meeting without losing the usability of sharing a link to join. Remember not to post your meeting links in public settings like facebook or twitter. https://zoom.us/profile/setting
* Disable “Allow participants to join the meeting before the host arrives”. If you have to have this feature enabled at least enable “Notify host when participants join the meeting before them”. This will notify you that someone might be using your meeting without your knowledge.   https://zoom.us/profile/setting
* If you must keep your meeting unprotected you should enable “Mask phone number in the participant list”   https://zoom.us/profile/setting?tab=telephony
Using the waiting list feature will prevent unwanted participants from accessing your meeting but it will still expose your meeting details if used without a password.

Other resources and tips.
- https://blog.zoom.us/wordpress/2020/03/20/keep-the-party-crashers-from-crashing-your-zoom-event/
- https://support.zoom.us/hc/en-us/articles/360033331271-Account-Setting-Update-Password-Default-for-Meeting-and-Webinar
- https://www.fbi.gov/contact-us/field-offices/boston/news/press-releases/fbi-warns-of-teleconferencing-and-online-classroom-hijacking-during-covid-19-pandemic

