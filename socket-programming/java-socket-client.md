Java client socket cheats
=========================

<h4>Create File</h4>
<pre>
nano socketClient.java
</pre>

<pre>
import java.net.*;
import java.io.*;

  public class socketClient {

  public static void main(String[] args) throws IOException {
  int port = 6666;
  String server = "localhost";

    try {
    System.out.println("Attempting to provide clarity to " + server + " on " + port);
    Socket socket = new Socket(server, port);

    System.out.println("thump, thump, thump...... " + socket.getRemoteSocketAddress());

    InputStream input = socket.getInputStream();
    OutputStream output = socket.getOutputStream();

    DataOutputStream dataOut = new DataOutputStream(output);
    DataInputStream dataIn = new DataInputStream(input);

    dataOut.writeUTF("This is your destiny from "+ socket.getLocalSocketAddress());
    System.out.println("The path of the righteous man is beset on all sides by the iniquities of the selfish 
    and the tyranny of evil men"+ dataIn.readUTF());
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
javac serverClient.java
</pre>

<h4>Connect client to server</h4>
<pre>
java serverClient
</pre>
