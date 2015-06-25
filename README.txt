F5 WAF Security for Splunk by Nexinto
=====================================


Overview
--------
The app "F5 WAF Security for Splunk by Nexinto" analyzes attacks on your web infrastructure prohibited by F5 ASM.

Features:
	-	Displays attacks based on GeoIP
	-	Displays attacks based on Type
	-	Displays attacks based on Violation, Signature
	-	Displays attacks based on Country
	-	Displays attacks based on IPs
	-	Heatmap for Attack Type Distribution by Type, Country, Violation
	-	Security Stats table for displaying chronological attack requests and locations

Installation
------------

Deploy "F5 WAF Security for Splunk by Nexinto" like every other App by uploading  it using the WebGUI or extracting it to $SPLUNK_HOME$/etc/apps. 
Restart Splunk afterwards.

In a distributed environment the app has to be deployed to every Search head and Indexer. Make sure the app is also deployed on the Host or 
Forwarder receiving the events from the F5 devices. 

With default settings the app will create an index “f5_asm_live” and a TCP input on port 10005 using sourcetype syslog_f5asm. You can customize these 
settings by changing the TCP port in inputs.conf.

Creating a logging profile on F5 ASM for sending Events to Splunk
------------------------------------------------------------------

To integrate Splunk you will need to create a new logging profile on your F5 ASM which sends the events to your Splunk TCP input. 

To create a logging profile:

	1.	On the Main Tab select Security, expand Event Logs. The Edit Logging Profile page opens.
	2.	Check “Application Security” in the Logging Profile Properties.
	3.	At Application Security tab select “Advanced” for Configuration setting.
	4.	Select the Remote Storage check box, and for the Type select Reporting Server.
	5.	Set Response Logging to Off.
	6.	For the protocol setting, select TCP.
	7.	For the IP Address setting, type the name of the host providing the TCP input (forwarder or indexer)
	8.	For the Port setting type the default value 10005.
	9.	Within the Storage Filter tab choose Request type = “Illegal Requests Only”
	10.	Click the “Update” Button.
	
Feedback and Contact
--------------------

If you have Feedback, issues or questions please use issue tracker at Github page: http://github.com/Nexinto/f5_asm  ;). 
For direct Feedback please contact: splunkapps@nexinto.com. 

This app was created by:

Nexinto GmbH
Nagelsweg 33-35
20097 Hamburg

Telefon: +49 40-77175-0
Telefax: +49 40-77175-519

E-Mail: ITSolutions@nexinto.com
Internet: www.nexinto.com
	
