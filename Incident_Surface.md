Key entry points for attack surface :
- Open ports
- Running services
- Running software or applications with vulnerabilities
- Network communication

Key points where incident trace can be found :
   
  - System logs
  - auth.log, syslog, krnl.log, etc
  - Network traffic
  - Running processes
  - Running services
  - The integrity of the files and processes


### To look for any running process in linux :
  `ps aux`
   If i want to know about specific process, use grep. 
   ![image](https://github.com/user-attachments/assets/89adbe3e-6087-4274-9347-a9b4804a5ed8)

   Outputs provide the following information :
   ![image](https://github.com/user-attachments/assets/9bc6d6ec-dafd-4518-a85a-52e922f4cacd)

   ### Can also list all files/resources connected with certain process.

    lsof -p <pid>
  ![image](https://github.com/user-attachments/assets/97fa8085-30b9-4899-b916-75d4248927a1)


### Investigating network connection
 It is worth to note about the process communicating via network to an external IP or server. 
 `lsof -n -P -i`
 
lsof: It stands of List Open Files. This command displays the information about the files opened by the processes.

-i: This flag shows information about the network connections, including sockets and open network files.

-P: This flag is used to display the port numbers.

-n: This flag shows the IP address instead of resolving them to hostnames.

### Osquery is also usesul to find lot more details about the processes and the connection. 
  `SELECT pid, fd, socket, local_address, remote_address FROM process_open_sockets WHERE pid = <pid(We want to investigate)>;`

   #### few use cases of the incidents related to processes:

  A process running from a tmp directory (context matters).
  
  A process with a suspicious network connection.
  
  Orphan process. Not all orphan processes are suspicious, but those with no parent process associated after execution are worth investigating.


 Suspicious processes that are running through a cronjob.
 
 System-related processes or binaries running from the tmp directory or user directories.
 

  

  
