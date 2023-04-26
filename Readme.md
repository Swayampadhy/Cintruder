<h2><u>DISCLAIMER</u></h2><br>
<h3>This tool is created for educational purposes. Please use responsibly. 
I will NOT be held liable if any damages are caused due to misuse of this tool.</h3><br>
<h2><u>Description</u>-></h2><br>
				<h5> This is a windows backdoor program which when run on a victim computer is capable of several actions including:
				  <ul>
  <li>Remotely issuing shell commands to the victim computer</li>
  <li>Keylogging the victim</li>
  <li>Creating persistence and running on boot</li>
</ul>
The payload can be delivered to the victim computer either as just an executable file or embedded inside an file such as an image.</h5>
<br><br>

<h2><u>Architecture</u> -></h2><br>
<h5>This malware works on a client-server architecture.The server issues commands remotely to the backdoor .The backdoor is the client which receives these commands, executes them and sends the output back to the server . The backdoor tries to connect to the server every 10 seconds .</h5><br><br>
<h2><u>Commands</u> -></h2><br>
<h5>The server specific commands for the backdoor are:<ul>
  <li>1. <u>persist</u>: This command will create an entry in the windows registry which will boot the malware on startup.In order to remove persistance of the backdoor, go to windows registry and remove the entry at the path which is prompted on the command line after the command.</li>
  <li>2. <u>keylog_start</u>: This command will start the inbuilt Keylogger of the backdoor. The keystroke data is stored locally on "windows.txt" on the same folder as the backdoor.</li>
  <li>3. <u>cd</u>: This command will switch directories while inside a program.</li>
</ul></h5><br>
<h2><u>Compilation</u> -></h2><br>To compile the server go the the folder containing the file server.c . There enter the following command-
<br>
<br>
&emsp;&emsp;&emsp; gcc -o server server.c
<br><br>
To compile the backdoor , you can compile it directly on a windows machine through mingw. If you are on linux , then install mingw on your system and compile it using the command-
<br><br>
&emsp;&emsp;&emsp; i686-w64-mingw32-gcc -o backdoor.exe backdoor.c -lwininet -lwsock32
<br><br>
Also remember to change the IP Address in the backdoot to your PC's IP before compiling.
