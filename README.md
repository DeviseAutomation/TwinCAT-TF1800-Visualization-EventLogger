# TwinCAT 3 TF1800 Visualization Event Logger Sample
The Idea behind this is to create an Event Logger and Visualize this on TwinCAT HMI TF1800.  

Using the FUNCTION_BLOCK FB_AlarmLogEvent we can create another Event instance to log
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



### Information
- Build 4026.19
- TF1800 Visualization
