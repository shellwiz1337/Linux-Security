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

  


  
