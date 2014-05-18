HL7 message anatomy cheats
==========================

<p>
Human readable ASCII<br>
Each segment is on a seperate line<br>
Each segment is made up of a number of composites (fields)<br>
A pipe | seperates composites in a segment<br>
Nested composites are seperated ^<br>
</p>

<h4>Delimeters</h4>
<p>
x0D: end of segment<br>
| : composite delimiter<br>
^ : nested composite delimiter<br>
& : nested nested composite delimiter<br>
~ : seperates repeating composites<br>
\ : escape character
</p>

<h4>MSH segment</h4>
<p>
The first part of the MSH segment which is the first segment of the message specifies what delimeters are used in the message<br>
<pre>
MSH|^~\&
</pre>
</p>

<h4>Message Type</h4>
<p>
Message type is usually the 9th composite of the MSH segment<br>
<pre>
MSH|^~\&|EPIC|EPICADT|SMS|SMSADT|199912271408|CHARRIS|ADT^A04|1817457|D|2.5|
</pre>
message type would be ADT^A04 or a  "Register Patient" message

<h4>Message Types</h4>
<pre>
ADT: Patient Administration
ORM: Orders
ORU: Lab Results
DFT: Charges
ACK: Acknowledgement
</pre>
</p>

<h4>Segment Grammar Notation</h4>
<p>
First composite of each segment
<pre>
MSH|^~\&|EPIC|EPICADT|SMS|SMSADT|199912271408|CHARRIS|ADT^A04|1817457|D|2.5|
PID||0493575^^^2^ID 1|454721||DOE^JOHN^^^^|DOE^JOHN^^^^|19480203|M||B|254 MYSTREET AVE^^MYTOWN^OH^44123^USA||(216)123-4567|||M|NON|400003403~1129086|
NK1||ROE^MARIE^^^^|SPO||(216)123-4567||EC|||||||||||||||||||||||||||
PV1||O|168 ~219~C~PMA^^^^^^^^^||||277^ALLEN MYLASTNAME^BONNIE^^^^|||||||||| ||2688684|||||||||||||||||||||||||199912271408||||||002376853
</pre>

Provides Segment Grammar Notation of:
<pre>
MSH PID NK1 PV1
</pre>

Optional segments enclosed in [ ]
<pre>
MSH PID NK1 PV1 [PV2]
</pre>

Repeating segments enclosed in { }
<pre>
MSH PID {NK1} PV1 [PV2]
</pre>

Optional and repeating {[ ]}
<pre>
MSH PID [{NK1}] PV1 [PV2]
</pre>

</p>

<h4>Null Fields and Values</h4>
<p>
Undefined Composite
<pre>
OBR||||||
</pre>

Null Value
<pre>
OBR|||""|||
</pre>
</p>

<h4>Escaping Delimiters</h4>
<pre>
& : \T\
^ : \S\
| : \F\
~ : \R\
\ : \E\
</pre>

<h4>Example HL7 message</h4>
<pre>
MSH|^~\&|EPIC|EPICADT|SMS|SMSADT|199912271408|CHARRIS|ADT^A04|1817457|D|2.5|
PID||0493575^^^2^ID 1|454721||DOE^JOHN^^^^|DOE^JOHN^^^^|19480203|M||B|254 MYSTREET AVE^^MYTOWN^OH^44123^USA||(216)123-4567|||M|NON|400003403~1129086|
NK1||ROE^MARIE^^^^|SPO||(216)123-4567||EC|||||||||||||||||||||||||||
PV1||O|168 ~219~C~PMA^^^^^^^^^||||277^ALLEN MYLASTNAME^BONNIE^^^^|||||||||| ||2688684|||||||||||||||||||||||||199912271408||||||002376853
</pre>
