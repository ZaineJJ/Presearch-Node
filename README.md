# Presearch-Node
 Set Up Guide For Multiple Presearch Node
<h3>Requirements</h3>
<br>1. VPN <a href="https://windscribe.com/yo/jtwxu32v" target="_blank">Sign Up "Windscribe" & Download</a> Optional, If you only want to set up 1 Node, Don't need VPN.
<br>2. Virtual Box with Ubuntu Server |<a href="https://www.virtualbox.org/wiki/Downloads" target="_blank">Download VM Virtual Box</a> |<a href="https://ubuntu.com/download/server" target="_blank">Download Ubuntu</a>
<br>3. Filezilla <a href="https://filezilla-project.org/" target="_blank">Download</a> Optional, If you only want to set up 1 Node, Don't need Filezilla.
<br>4. Putty <a href="https://www.putty.org/" target="_blank">Download</a>
<br>5. Own a Presearch Account <a href="https://presearch.com/signup?rid=3735748" target="_blank"> Register here </a>
<br>6. 4,000 PRE per Node <a href="https://bit.ly/SignUpKucoinToday" target="_blank">Buy PRE</a>
<br>7. Watch this <a href="https://youtu.be/h_QcIbNLK2c" target="_blank">Video</a> and <a href="http://bit.ly/Simplyeverythingcrypto" target="_blank">Subscribe!</a>
<br>
<h3>Step 1</h3>
<br> Setting Up Virtual Box
<br> Watch <a href="https://youtu.be/h_QcIbNLK2c" target="_blank">Video</a> [04:43] 

<h3> Step 2</h3>
<br> Installing Ubuntu Server
<br>a. Select Install Ubuntu Server and wait
 <br>b. Select your langugage 
 <br>c. Select your keyboard layout 
 <br>d. Configure Proxy, Just leave blank and select <b>"Done".</b>
 <br>e. Configure Ubuntu archive Mirror, leave it as default and select <b>"Done".</b>
 <br>f. Guided Storage Configuration
 <br><b>Important</b>, Unselect "Set Up this disk as an LVM group" & select <b>"Done".</b> <a href="https://drive.google.com/file/d/1jNh_tSOvw2VvCtbO8WD_c-JG7CKnP00o/view?usp=sharing" target="_blank">[Reference]</a>
 <br>g. Storage configuration - Leave it as default and select <b>"Done".</b> Then confirm destrutive action "<b>"Continue".</b>
 <br>h. Profile Setup - Fill up the details 
<br>-Your name = just ur profile name on the linux server not username.
<br>-Server's name = is how you want the server to be called, will be shown on your router as input. 
<br>-Username = to use when logging into the server
<br>-Password = to log into the server.
<br>i. SSH Setup enable "Install OpenSSH server" & <b>"Done".</b>
<br>j. Featured Server Snaps leave it as default & <b>"Done".</b>
<br><b>Finally Install complete!</b>
<br>-You will see <b>"Cancel update and reboot"</b> but wait till you see <b>"Reboot Now"</b> option and select it
<br>-Press <b>"Enter"</b> Once reboot you will see <b>"[FAILED] Failed unmounting/cdrom. blah blah blah.</b> 
<br>Press <b>"Enter"</b> if you see the loading stops and it's not moving
<br> Enter your Username and Password to login

<h3>Step 3</h3>
<br> Installing Presearch On Virtualbox
<br> Install Docker first 
<br> Input "sudo apt update ; sudo apt upgrade -y ; sudo apt install docker.io"
<br> Input "sudo usermod -aG docker $USER"
<br> Install Presearch with this bunch, do input your own registeration code at "$YOUR_REGISTRATION_CODE_HERE" below
<br>
<blockquote>
docker stop presearch-node ; docker rm presearch-node ; docker stop presearch-auto-updater ; docker rm presearch-auto-updater ; docker run -d --name presearch-auto-updater --restart=unless-stopped -v /var/run/docker.sock:/var/run/docker.sock presearch/auto-updater --cleanup --interval 900 presearch-auto-updater presearch-node ; docker pull presearch/node ; docker run -dt --name presearch-node --restart=unless-stopped -v presearch-node-storage:/app/node -e REGISTRATION_CODE=<b>$YOUR_REGISTRATION_CODE_HERE</b>  -e STAKE="disconnected:oldest,wallet:minimum" -e ALLOW_DISCONNECTED_STAKE_TRANSFER_AFTER="30m" presearch/node ; docker logs -f presearch-node
</blockquote>
<br>
<h3>Step 4 VPN Optional</h3>
<br>Download VPN Package Input "wget https://github.com/ZaineJJ/Presearch-Node/releases/download/release/windscribe-cli_1.4-51_amd64.deb"
<br>Input "sudo dpkg -i windscribe-cli_1.4-51_amd64.deb" 
<br>Input "sudo apt --fix-broken install" Prompted windscribe default just click "enter"
<br> Input "sudo dpkg -i windscribe-cli_1.4-51_amd64.deb" 
<br> Input "windscribe login" to login to your windscribe account
<br> Input "windscribe connect" to connect to the best location [Note if you are setting multiple Nodes connect to other locations]
<br> Test by inputing "ping google.com" if there is replies exit it by pressing CTRL+C 
<br> Another test "ping 1.1.1.1" if there is replies exit it by pressing CTRL+C 
<br> Your VPN is finally set up
<br> Go to your VirtualBox and input "sudo docker logs -f presearch-node" 

<h3>Congrats you can repeat these steps and set up multiple Presearch Nodes! </h3>
