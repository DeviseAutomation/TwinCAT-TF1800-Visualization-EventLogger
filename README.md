# TwinCAT 3 TF1800 Visualization Event Logger Sample
The Idea behind this is to create an Event Logger and Visualize this on TwinCAT HMI TF1800.  

## Option 1 - Recommended
Using the FUNCTION_BLOCK FB_AlarmEX and FB_Message derived from the TC3_EventLogger Library we can create Alarms and Messages that will be displayed on an Event Grid.
<br />

https://github.com/user-attachments/assets/016dfa7f-5f8d-4e93-8490-a511603b5d15

## How To

### Add Event Class
https://github.com/user-attachments/assets/74478d28-2e49-4a20-9f59-3f821493f26d

### Create Events
https://github.com/user-attachments/assets/95abde2a-5a57-4dde-8079-c044d07ba4ee

### Add the Event Table Library
FB_ReadTc3Events will also need to be called
Reference - https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_plc_intro/3524166155.html&id=
<br />

<img width="372" height="307" alt="EventGrid_Library" src="https://github.com/user-attachments/assets/8458c4ee-ac48-4fa9-a572-c8d4c662fc98" />
<img width="1137" height="275" alt="ReadEvents" src="https://github.com/user-attachments/assets/2ee227a5-733b-4ec4-9482-231e8cb6bdda" />



### Enable the Event Table Object
Found within the PLC Project Properties
Reference - https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_plc_intro/3524180363.html&id=
<br />

<img width="958" height="497" alt="EnableEventTable" src="https://github.com/user-attachments/assets/31303d70-562d-45b9-882d-9ae91209ad7f" />

### Add the Event Table and link FB_ReadTc3Events FB

https://github.com/user-attachments/assets/03e84a56-7d42-4c7a-a929-184480b88ee9

<br />

The Event Logger is now linked to the Event Table.  Toggling the Test message and Alarm bits will now display on the Event Table within the "TC3_EventLogger" Action.
<br />

<img width="757" height="393" alt="EventTable" src="https://github.com/user-attachments/assets/83e260ae-e8ed-4195-8abf-8179c0548159" />






## Option 2 - Legacy

Using the FUNCTION_BLOCK FB_AlarmLogEvent_TextList we can create another Event instance to log
<br />

Event ID's are passed into the FB which in the end is tied to the Alarm_Text List.  The Reason behind this is for Localization.  Within a Text List you can add other languages and switch between them with little effort.
<br />



https://github.com/user-attachments/assets/96ab0a9b-36f4-4f58-893f-d03ef3707812



A Class ID is also passed in, for example, Message, Warning, Alarm to differentiate different events.

Alarm Frames are used to display the information with a pass in value of Index.  Based on the Index value in the list (1-10) an active event will be displayed.
<br />


### Trigger Alarm
https://github.com/user-attachments/assets/a5e02550-0a1a-454c-9515-8aae0f1f393c


### Reset Alarm
https://github.com/user-attachments/assets/6b542177-6d8a-41b3-b35f-66e72c671ad5

## Option 3 - Legacy
Using the FUNCTION_BLOCK FB_AlarmLogEvent_Table we can create another Event instance to log
<br />

Event Text is passed directly into the function block which will get passed into an active alarm array.  Using a Table element allows the use of scrolling through an alarm array.  Option 1's limitation is you can only display as many alarms as there are Alarm Row Frames present.  You can choose to enable or disable column headers and possibly use the information provided, for example "Class" to show colors or symbols within the Row.
<br />

https://github.com/user-attachments/assets/256beb0e-46cb-4748-be79-cd3538534df3

https://github.com/user-attachments/assets/d7ae9310-b337-49c3-a064-5e526bbc9b95

Information
- Build 4026.19
- TF1800 Visualization
