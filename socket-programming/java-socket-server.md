Java socket server cheats
=========================

<h4>Create File</h4>
<pre>
nano socketServer.java
</pre>

<pre>
import java.net.*;
import java.io.*;

   public class socketServer extends Thread
{
    private ServerSocket serverSocket;

    public socketServer(int port) throws IOException
 {
    serverSocket = new ServerSocket(port);
    System.out.println("System Available");
    serverSocket.setSoTimeout(50000);
 }

   public void run()

 {
    while(true) 
 {

    try
 {
    System.out.println("Awaiting clarity " + serverSocket.getLocalPort());
    Socket socket = serverSocket.accept();
    System.out.println("Received clarity from " +  socket.getRemoteSocketAddress());
    
    DataInputStream input = new DataInputStream(socket.getInputStream());
    DataOutputStream output = new DataOutputStream(socket.getOutputStream());

    System.out.println(input.readUTF());
    output.writeUTF("\nThank you for this clarity. I will not forget it\n");
    output.writeUTF("\nGood Bye from p00gz ************^^^^***************");
    socket.close();

    }
    catch(SocketTimeoutException s)
    {
      System.out.println("socket timeout");
      break;
  }
    catch(IOException e)
      {
        e.printStackTrace();
        break;
      }
}

}

public static void main(String [] args)
   {
      int port = 6666;
      try
      {
         Thread t = new socketServer(port);
         t.start();
      }catch(IOException e)
      {
         e.printStackTrace();
      }
   }
}

</pre>

<h4>Compile</h4>
<pre>
javac serverSocket.java
</pre>

<h4>Run Server in Background</h4>
<pre>
java serverSocket &
</pre>


