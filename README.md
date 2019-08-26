# RPC

Remote Procedure Call is a powerful technique for constructing distributed client-server based applications.It is based on extending the conventional local procedure calling so that the called procedure need not exist in the same address space as the calling procedure.
Here I have implemented a remote procedure to add two numbers.This program will accept two numbers from the command line,then call the remote procedure to add the two numbers and print the result.

## The Steps Involved Are:

#### Step 1:
Create The IDL:
Create an add.x file which contains the type definitions and the definitions of the remote procedures.
<br> Compile this file using:<br />
**rpcgen -a -C add.x**
<br >After compiling we get:<br />
- add.h
- add_svc.c
- add_clnt.c
- add_xdr.c

#### Step 2:
After compiling the above files,we get two executables:add_client and add_server.Move the add_server to another computer.
Start the portmapper on the somputer on which the server is going to be run by using:
<br >**/etc/init.d/rpcbind start**<br />
Then run the command:
<br >**./add_server**<br />
On the computer on which the client is to be run execute the command:
<br >**./add_client ip_address_of_server_computer**<br />



