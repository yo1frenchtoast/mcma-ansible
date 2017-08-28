# Ansible playbook for McMyAdmin 2 [Minecraft Control Panel](https://www.mcmyadmin.com/#/home) deployment

Based on https://www.mcmyadmin.com/#/download

>>>
### Installing on 64-bit Linux

Run the following as root:
```
cd /usr/local
wget http://mcmyadmin.com/Downloads/etc.zip
unzip etc.zip; rm etc.zip
```

Then run the following as a non-root user:
```
mkdir ~/McMyAdmin
cd ~/McMyAdmin
wget http://mcmyadmin.com/Downloads/MCMA2_glibc26_2.zip
unzip MCMA2_glibc26_2.zip
rm MCMA2_glibc26_2.zip
./MCMA2_Linux_x86_64 -setpass [YOURPASSWORD] -configonly
```

You can then start McMyAdmin by running:
```
cd ~/McMyAdmin; ./MCMA2_Linux_x86_64
```

Note that you must change to the directory McMyAdmin is installed to before running it. You cannot run it using a relative or absolute path.

Once McMyAdmin is running, you can connect to the web interface on http://localhost:8080 if it's running locally, or ar your servers external IP address on port 8080.

You may need to allow ports 8080 TCP and 25565 TCP (the default ports for McMyAdmin and Minecraft) through your firewall. For most distributions this is done by running the following as root:
```
iptables -A INPUT -p tcp -m tcp --dport 8080 -j ACCEPT iptables -A INPUT -p tcp -m tcp --dport 25565 -j ACCEPT /sbin/service iptables save
```
Otherwise consult with your Linux distributions documentation for how to manage the firewall.
>>>
