Minimal Lower Layer Protocol anatomy cheats
===================================

OSI session layer framing protocol<br>
Wraps the HL7 message in the TCP/IP transmission so that the beginning and end of the message can be identified<br> 
Release 1: no reliable delivery assurance<br>
Release 2: ACK delivery assurance<br>

Sender: maintains persistent or transient connection<br>
Receiver: contains singular GET command. Enters into a listening state<br>
only one sender can be connected to a receiver at a time<br>

<h4>MLLP Construction</h4>
<pre>
SB = Start Block
Message = HL7 Message
EB = End Block
CR = Carriage Return
</pre>

<h4>Default HEX values</h4>
<pre>
SB: VT character; 11 decimal; 0013 oct; x0b hex;
EB: FS character; 28 decimal; 0034 oct; x1c hex;
CR: CR character; 13 decimal; 0015 oct; x0d hex;
</pre>

Permanant Connection: Only one connection used to exchange all messages<br>
Transient Connection: New Socket is created for each message. Socket is closed after the ACK is received.<br> 






