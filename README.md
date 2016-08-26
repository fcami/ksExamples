# ksExamples

### ksPythonPre-EL7.cfg

Demo of a fairly basic Python %pre script that:
* uses snack (UI)
* computes swap size according to RAM size
* detects if the system is virtual or physical

Instructions:
* copy the content of a CentOS 7.2+ or RHEL 7.2+ DVD in a webserver
* modify the kickstart's "url" line to point to your webserver
* host the kickstart on a webserver too
* boot CentOS or RHEL installation media
* add "ks=http://webserver/ksPythonPre-EL7.cfg" to the command line
* on VMware, add "net.ifnames=0 biosdevname=0" too

