# Multiserver and clients (Sockets TCP and threads)
## Java, Network, Processes, Threads 
### URL: https://www.jesusninoc.com/2012/10/12/multiserver-and-clients-sockets-tcp-and-threads/
```Java
import java.io.*; 
import java.net.*;

public class MultiServer
{
	public static void main(String[] args)
	{
		int port=2050;
		try
		{
			ServerSocket serverSocket = new ServerSocket(port);
			while(true)
			{ 
				new ThreadClient(serverSocket.accept()).start(); 
				} 
			}
		catch(IOException ex){ }
		}
	}

```
```Java
import java.io.*; 
import java.net.*;

public class ThreadClient extends Thread 
{
	private Socket clientSocket = null;
	public ThreadClient(Socket param)
	{
		this.clientSocket = param;
		}
	
	public void run() 
	{
		try
		{
			PrintWriter out = new PrintWriter(clientSocket.getOutputStream(), true);
			BufferedReader in = new BufferedReader(new InputStreamReader (clientSocket.getInputStream()));
			
			String inputLine = in.readLine();
			System.out.println("Receive: " + inputLine); 
			String outputLine = inputLine.toUpperCase(); 
			System.out.println("Send: " + outputLine); 
			out.println(outputLine); 
			
			out.close(); 
			in.close(); 
			
			clientSocket.close();
			}
		catch (UnknownHostException e){
			System.out.println(e);
		} catch (IOException e) {
			System.out.println(e);
		}
		}
	}

```
```Java
import java.io.*; 
import java.net.*;

public class Client
{
	public static void main(String[] args)
	{
		int port=2050;
		try
		{
			Socket clientSocket = new Socket("192.168.1.37",port);
			
			PrintWriter out = new PrintWriter(clientSocket.getOutputStream(),true);
			BufferedReader in = new BufferedReader(new InputStreamReader (clientSocket.getInputStream()));
			
			System.out.println("Send: Hi"); 
			out.println("Hi");
			System.out.println("Receive: " + in.readLine());
			
			out.close();
			in.close();
			clientSocket.close();
			}
		catch (UnknownHostException e){
			System.out.println(e);
		}
		catch (IOException e) {
			System.out.println(e);
		}
		}
	}

```
