Mirth Connect server configuration cheats
=========================================

<H4>Create Channel</h4>
<p>
Select Channels<br>
Select New Channel in Channel Tasks<br>
Enter Name in Channel Name field<br>
</p>

<H4>LLP Mode with MySql</h4>
<p>
Click source tab<br>
Set LLP listener mode to accept incoming HL7 messages<br>
Select Destinations tab<br>
Choose Database Writer Connector Type<br>
Change Driver to MySql<br>
Set URL field to jdbc:mysql://localhost:3306/mirthdb<br>
Set Username to mirthdb MySQL Username<br>
Set Password to mirthdb MySQL Password<br>
Set Use Javascript to Yes<br>
</p>

<H4>Create Transformer Templates</h4>
<p>
Under Channel Tasks select Edit Transformer<br>
Select Message Templates tab<br>
Paste an HL7 message into the form box<br>
Select Message Trees tab to view the values that can be saved to the database<br>
Drag the values that you need to save into the box to the left<br>
This creates mapping variables for use later with scripts<br>

<h4>Create Script to run on message</h4>
Select Back to Channel<br>
Connection variable (var dbConn) should already be created<br>
dbConn.close() function should already be present<br>
Create variables using the mappings created in the templates:<Br>
<pre>
var patientalias = $('patientIdentification_patientAlias');
var patientbirthOrder = $('patientIdentification_birthOrder');
var patientmilitaryStatus = $('patientIdentification_veteransMilitaryStatus');
var patientsecurity = $('messageHeader_security');
</pre>





















