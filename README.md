# AdGuard-Home-One-Script-Docker-Install
## Description
This repo was created to automate pulling and running the AdGuard Home docker container. It is already pretty simple, but now its one (very basic) shell script. You can even just copy and paste the script contents into a file on your Linux host and run it without pulling the repo.

The AdGuard Home docker container is a DNS server to which you can implement ad, tracker, and malware blocking. It is similar to PiHole, but in my testing it comes out ahead.
It also does not interrupt use of Apple's 'Private Relay' feature, whereas PiHole does. 
## Requirements
1. Linux VM, machine, Raspberry Pi, etc
2. Network connectivity
3. Assign the Linux host a static IP address
3. A device to access the GUI from (if using Linux device headless)
## Install
1. Download the repo
2. Unzip the .ZIP `unzip download.zip`
3. `cd` into the directory
4. Run the install file with `sudo bash ./adhuard_home_setup.sh`
5. Enter your sudo password if prompted
6. Once complete, terminal will output the IP address and port to access the GUI
7. Enter the IP address into a web browser, i.e. `127.0.1.1` or `127.0.1.1:80`
8. Follow the on-screen prompts to compelte the final setup
## Further Setup
### Enable Log Retention
1. Navigate to `Settings` `>` `General Settings`
2. Under `Logs Configuration` enable logs and increase retention to `90 days`
3. Click `Save`
4. Under `Statistics Configuration` enable and increase retention to `90 days`
5. Click `Save`
### Edit Upstream DNS Servers
1. Navigate to `Settings` `>` `DNS Settings`
2. In the text box, replace the defaults with the following, one per new line:
      1. `https://doh.opendns.com/dns-query`
      2. `https://dns.google.com/dns-query`
      3. `https://dns.cloudflare.com/dns-query`
3. Click on `Test Upstreams` and `Apply`
4. Under `DNS Server Configuration` select `Enable DNSSEC`
5. Click `Save`
### Enable More Filters and Add Custom Lists
1. Drafting
## Notes
Most of this is already documented, I'm writing just as a personal project so I can replicate and (hopefully) help others.
