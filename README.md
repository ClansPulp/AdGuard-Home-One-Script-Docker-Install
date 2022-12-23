# AdGuard-Home-One-Script-Docker-Install
## Description
This repo was created to automate pulling and running the AdGuard Home docker container. It is already pretty simple, but now its one (very basic) shell script. You can even just copy and paste the script contents into a file on your Linux host and run it without pulling the repo.

The AdGuard Home docker container is a DNS server to which you can implement ad, tracker, and malware blocking. It is similar to PiHole, but in my testing it comes out ahead.
It also does not interrupt use of Apple's 'Private Relay' feature, whereas PiHole does. 

<img src="https://github.com/ClansPulp/AdGuard-Home-One-Script-Docker-Install/blob/main/adguard_home/img/Dashboard.jpg?raw=true" alt="Dashboard Example" width="600"/>

## Requirements
1. Linux VM, machine, Raspberry Pi, etc
2. Network connectivity
3. Assign the Linux host a static IP address
3. A device to access the GUI from (if using Linux device headless)
## Install
1. Download the repo or copoy the script contents into a new script on the Linux host
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

<img src="https://github.com/ClansPulp/AdGuard-Home-One-Script-Docker-Install/blob/main/adguard_home/img/DNS%20Servers.jpg?raw=true" alt="DNS Servers Example" width="600"/>

1. Navigate to `Settings` `>` `DNS Settings`
2. In the text box, replace the defaults with the following, one per new line:
      1. `https://doh.opendns.com/dns-query`
      2. `https://dns.google.com/dns-query`
      3. `https://dns.cloudflare.com/dns-query`
3. Click on `Test Upstreams` and `Apply`
4. Under `DNS Server Configuration` select `Enable DNSSEC`
5. Click `Save`
### Enable More Filters and Add Custom Lists
1. Navigate to `Filters` `DNS Blocklists`
2. Click `Add Blocklist`
3. Click `Choose From List`
4. `Enable` the ones you want
5. Click `Add Blocklist`
6. Click `Add a Custom List`
7. `Name` your rule and `paste` the `URL` of the list (the **32** lists I currently use will be pasted below)
8. Once you have added all your custom lists, click `Check For Updates` and wait for it to apply
### Custom Lists
1. `https://raw.githubusercontent.com/PolishFiltersTeam/KADhosts/master/KADhosts.txt` 
2. `https://raw.githubusercontent.com/FadeMind/hosts.extras/master/add.Spam/hosts`
3. `https://v.firebog.net/hosts/static/w3kbl.txt`
4. `https://v.firebog.net/hosts/AdguardDNS.txt`
5. `https://v.firebog.net/hosts/Admiral.txt`
6. `https://raw.githubusercontent.com/anudeepND/blacklist/master/adservers.txt`
7. `https://s3.amazonaws.com/lists.disconnect.me/simple_ad.txt`
8. `https://v.firebog.net/hosts/Easylist.txt`
9. `https://pgl.yoyo.org/adservers/serverlist.php?hostformat=hosts&showintro=0&mimetype=plaintext`
10. `https://raw.githubusercontent.com/FadeMind/hosts.extras/master/UncheckyAds/hosts`
11. `https://raw.githubusercontent.com/bigdargon/hostsVN/master/hosts`
12. `https://v.firebog.net/hosts/Easyprivacy.txt`
13. `https://raw.githubusercontent.com/FadeMind/hosts.extras/master/add.2o7Net/hosts`
14. `https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/hosts/spy.txt`
15. `https://hostfiles.frogeye.fr/firstparty-trackers-hosts.txt`
16. `https://raw.githubusercontent.com/DandelionSprout/adfilt/master/Alternate%20versions%20Anti-Malware%20List/AntiMalwareHosts.txt`
17. `https://osint.digitalside.it/Threat-Intel/lists/latestdomains.txt`
18. `https://s3.amazonaws.com/lists.disconnect.me/simple_malvertising.txt`
19. `https://v.firebog.net/hosts/Prigent-Crypto.txt`
20. `https://raw.githubusercontent.com/FadeMind/hosts.extras/master/add.Risk/hosts`
21. `https://bitbucket.org/ethanr/dns-blacklists/raw/8575c9f96e5b4a1308f2f12394abd86d0927a4a0/bad_lists/Mandiant_APT1_Report_Appendix_D.txt`
22. `https://phishing.army/download/phishing_army_blocklist_extended.txt`
23. `https://gitlab.com/quidsup/notrack-blocklists/raw/master/notrack-malware.txt`
24. `https://v.firebog.net/hosts/RPiList-Malware.txt`
25. `https://v.firebog.net/hosts/RPiList-Phishing.txt`
26. `https://raw.githubusercontent.com/Spam404/lists/master/main-blacklist.txt`
27. `https://raw.githubusercontent.com/AssoEchap/stalkerware-indicators/master/generated/hosts`
28. `https://urlhaus.abuse.ch/downloads/hostfile/`
29. `https://zerodot1.gitlab.io/CoinBlockerLists/hosts_browser`
30. `https://raw.githubusercontent.com/AdguardTeam/cname-trackers/master/combined_disguised_trackers_justdomains.txt`
31. `https://raw.githubusercontent.com/AdguardTeam/cname-trackers/master/combined_original_trackers.txt`
32. `https://raw.githubusercontent.com/AdguardTeam/cname-trackers/master/combined_disguised_trackers.txt`
## Notes
Most of this is already documented, I'm writing just as a personal project so I can replicate and (hopefully) help others.
