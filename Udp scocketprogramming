Write a program on datagram socket for client/server to display the messages on client side, typed 

at the server side.

UDP Client

import java.io.*;

import java.net.*;

class ucl

{

 public static void main(String args[]) throws Exception

 {

 BufferedReader clientRead =new BufferedReader(new InputStreamReader(System.in));

 DatagramSocket clientSocket = new DatagramSocket();

 InetAddress IP = InetAddress.getByName("127.0.0.1");

 byte[] sendbuffer = new byte[1024];

 byte[] receivebuffer = new byte[1024];

 System.out.print("\nClient: ");

 String clientData = clientRead.readLine();

 sendbuffer = clientData.getBytes(); 

 DatagramPacket sendPacket =

 new DatagramPacket(sendbuffer, sendbuffer.length, IP, 9876);

 clientSocket.send(sendPacket);

 DatagramPacket receivePacket =

 new DatagramPacket(receivebuffer, receivebuffer.length);

 clientSocket.receive(receivePacket);

 String serverData = new String(receivePacket.getData());

 System.out.print("\nServer: " + serverData);

 clientSocket.close();

 }

}

UDP SERVER

import java.io.*;
import java.net.*;

class usr

{

 public static void main(String args[]) throws Exception

 {

 DatagramSocket serverSocket = new DatagramSocket(9876);

 byte[] receivebuffer = new byte[1024];

 byte[] sendbuffer = new byte[1024];

 while(true)

 {

 DatagramPacket recvdpkt = new DatagramPacket(receivebuffer, receivebuffer.length);

 serverSocket.receive(recvdpkt);

 InetAddress IP = recvdpkt.getAddress();

 int portno = recvdpkt.getPort();

 String clientdata = new String(recvdpkt.getData());

 System.out.println("\nClient : "+ clientdata);

 System.out.print("\nServer : ");

 BufferedReader serverRead = new BufferedReader(new InputStreamReader (System.in) );

 String serverdata = serverRead.readLine();

 sendbuffer = serverdata.getBytes();

 DatagramPacket sendPacket = new DatagramPacket(sendbuffer, sendbuffer.length, IP,portno);

 serverSocket.send(sendPacket);

 }

 }

}
