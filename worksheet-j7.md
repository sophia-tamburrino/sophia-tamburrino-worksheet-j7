## 1. What is inside a packet?
A header, that stores the web address, and a payload that contains the data to send along in the package.


## 2. What is the purpose of an internet layer in the TCP/IP protocol? What do you, as a client, need to specify in this protocol?
The internet layer in the TCP/IP protocol contains all the information about networking and where to send a packet in order to reach a specific destination. The internet layer is what connects these networks together, kind of like a map. We must specify the packet contents, protocol address and IP address.


## 3. What is the purpose of the transport layer in the TCP/IP protocol? What do you, as a client, need to specify in this protocol?
When two processes are running, the transport layer offers ports to have those processes communicate with each other. 

## 4. What is the difference between SMTP and HTTP?
SMTP is used to transmit email messages in the application layer, and HTTP is used to download content from the web in the application layer.


## 5. What is the difference between an IP address and a domain name?
An IP address is a bit number that can help a computer understand where to send a packet. A domain name is used to identify a networked device so we don't have to memorize an IP address.


## 6. How does the operating system use ports?
The port address is used to deliver the packets to the correct process. As multiple processes occur in one computer, port addresses help guide the packet to a specific process. 


## 7. Write code that creates a socket connection to ip address 123.45.678.900 at port 4040. Then, print a color to that socket’s output.
Code from website:
```Java
public static void main(String args[]){

        Socket sock=null;        
        try{
           sock = new Socket("123.45.678.900",4040);
        }catch(Exception e){
            System.err.println("Cannot Connect");
            System.exit(1);
        }

        try{
            PrintWriter pw = new PrintWriter(sock.getOutputStream());
            pw.println("Red");
            pw.close(); //close the stream
            sock.close();//close the socket
        }catch(Exception e){
            System.err.print("IOException");
            System.exit(1);
        }

    }
```

## 8. What is the difference between a socket’s input stream and its output stream?
An input stream can read, and an output stream can write, turning them into buffered readers/writers.


## 9. What is the difference between a Socket and a SocketServer?
SocketServer is exactly like Socket, except requires the server to accept() a connect. A new socket is created every time the server accepts, allowing multiple connections.


## 10. How are threads useful with servers? How does a server manage to always be listening for sockets trying to connect?
If we create a new thread for each thread, the main thread is given the ability to continuously listen and accept other connections. This can allow the queueing of other clients, and will do so until you manually close the program. 

