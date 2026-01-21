# TwinCAT 3 TF1800 Visualization Event Logger Sample
The Idea behind this is to create an Event Logger and Visualize this on TwinCAT HMI TF1800.  

## Option 1

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

## Option 2
Using the FUNCTION_BLOCK FB_AlarmLogEvent_Table we can create another Event instance to log
<br />

Event Text is passed directly into the function block which will get passed into an active alarm array.  Using a Table element allows the use of scrolling through an alarm array.  Option 1's limitation is you can only display as many alarms as there are Alarm Row Frames present.  You can choose to enable or disable column headers and possibly use the information provided, for example "Class" to show colors or symbols within the Row.
<br />

https://github.com/user-attachments/assets/256beb0e-46cb-4748-be79-cd3538534df3

https://github.com/user-attachments/assets/d7ae9310-b337-49c3-a064-5e526bbc9b95

Information
- Build 4026.19
- TF1800 Visualization
