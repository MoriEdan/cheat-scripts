HL7 Java socket client cheats 
=============================

<h4>Create File</h4>
<pre>
nano hl7client.java
</pre>

<pre>
import java.net.*;
import java.io.*;

public class hl7client {

  private static final char end = '\u001c';
  private static final char start = '\u000b';
  private static final char carriage = 13;

  public static void main(String[] args) throws IOException {
  int port = 6666;
  String server = "localhost";

    try {
    System.out.println("Finding hl7 server " + " on " + port);
    Socket socket = new Socket(server, port);
    System.out.println("Conected to hl7 server on " + socket.getRemoteSocketAdd$

    StringBuffer hl7Message = new StringBuffer();

    hl7Message
    .append(start)
    .append("MSH|^~\\&|EPIC|EPICADT|SMS|SMSADT|199912271408|CHARRIS|ADT^A04|181$
    .append(carriage)
    .append("PID||0493575^^^2^ID 1|454721||DOE^JOHN^^^^|DOE^JOHN^^^^|19480203|M$
    .append(carriage)
    .append("NK1||ROE^MARIE^^^^|SPO||(216)123-4567||EC|||||||||||||||||||||||||$
    .append(carriage)
    .append("PV1||O|168 ~219~C~PMA^^^^^^^^^||||277^ALLEN MYLASTNAME^BONNIE^^^^|$
    .append(carriage)
    .append(end)
    .append(carriage);

     InputStream input = socket.getInputStream();
     OutputStream output = socket.getOutputStream();

     output.write(hl7Message.toString().getBytes());
     byte[]  byteBuffer = new byte[1024];
     input.read(byteBuffer);

     System.out.println("Received: " + new String(byteBuffer));

    socket.close();
  }

 catch(IOException e)
      {
        e.printStackTrace();
      }
}

}

</pre>

<h4>Compile</h4>
<pre>
javac hl7client.java
</pre>

<h4>Connect client to server</h4>
<pre>
java hl7client
</pre>
