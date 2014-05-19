Acknowledgement Protocol cheats
===============================

<h4>Message Ack Protocol</h4>
<p>
Some clients require an ack message sent back to the sending application after a message is accepted. <br>
MSA segment is sent to let the sending client know the status of the message

MSH message:
<pre>
MSH|^~/&|ACME Lab Sys|Endoscopy Lab|||||ACK|AADT.1.1698593|P|2.5|
</pre>

Corresponding MSA message:
<pre>
MSA|AA|ADT.1.1698593|
</pre>

ACK Modes:
<pre>
AA: Postiive ACK
AE: Negative ACK; Application Error
AR: Negative ACK; Application Reject; Problem with composite 9,11,12 of the MSH segment or 
    with receiving application
</pre>
