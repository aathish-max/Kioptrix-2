# Kioptrix-2
Local Privilege Escalation:
After gaining access to the target system through the SQL injection vulnerability, it is observed that the current user is not the root user. Further research reveals that the Linux kernel being used on the system is susceptible to local privilege escalation.

To exploit this vulnerability, you can leverage an existing exploit from the Exploit Database. You can search for local privilege escalation exploits for the Linux kernel version 2.6 using the "searchsploit" command.

In your case, the path to the exploit can be found by prepending "/usr/share/exploitdb/exploits/" to the path shown in the screenshot. Once you locate the appropriate exploit, you need to find a way to transfer it to the target machine.

One method is to set up a folder on your attacker machine and serve it using a Python web server. You can create a simple Python web server using the command "python3 -m http.server 8080". Verify that your web server is functioning correctly by accessing it through the browser using your attacker machine's IP address and the specified port.

Once your web server is up and running, you can use commands like "wget" or "curl" in the reverse shell to download the exploit onto the target machine. However, you may encounter permission issues while downloading the exploit file. In such cases, you can navigate to a directory where you have write access, such as "/tmp", and then use "wget" to download the exploit file from your web server.

Once the exploit file is downloaded to the target machine, you can compile and run the code to exploit the local privilege escalation vulnerability. Execute the necessary commands to compile the code and gain root access on the target machine.
