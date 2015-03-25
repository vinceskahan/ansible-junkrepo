# ansible playbook for installing weewx over nginx

This is a simple playbook to install weewx 'current'
on top of an nginx webserver.

This expects:
 - weewx as available on sourceforge in tgz format
 - debian as the host operating system

To run:
 - edit the hosts file to fit your remote ip address
 - run "ansible-playbook -i hosts site.yml"

Notes:
 - nginx will listen on port 80
 - it takes 5 minutes for weewx to initially provision public_html

