Load balancer

Concepts
HTTP Header
Debian/UbuntuHAProxy Packages
Introduction to Load Balancing.
Requirements
Allowed editors: vi, vim, emacs
All your files will be interpreted on Ubuntu 16.04 LTS
All your files should end with a new line
A README.md file, at the root of the folder of the project, is mandatory
All your Bash script files must be executable
Your Bash script must pass Shellcheck (version 0.3.7) without any error
The first line of all your Bash scripts should be exactly #!/usr/bin/env bash
The second line of all your Bash scripts should be a comment explaining what is the script doing.
Installing HAProxy and configuring HAProxy
$ sudo apt-get install -y haproxy=1.6.\*

$ sudo vi /etc/haproxy/haproxy.cfg
# Add the below code to the file opened using vi editor
frontend sammykingx.tech
        bind 0:80
	mode http
        default_backend web_servers

backend web_servers
        balance roundrobin
        server 64820-web-01 100.26.152.157:80
        server 64820-web-02 52.86.102.6:80
~
~
:wq(to save and exit)
--------------- or ----------------------- 
$ echo '
frontend sammykingx.tech
        bind 0:80
	mode http
        default_backend web_servers

backend web_servers
        balance roundrobin
        server 64820-web-01 100.26.152.157:80
        server 64820-web-02 52.86.102.6:80
' >> /etc/haproxy/haproxy.cfg

$ service haproxy restart

# git clone this repo on your terminal and run the file
# install_haproxy_safely or 1-install_load_balancer to 
# configure yours on a fly.
