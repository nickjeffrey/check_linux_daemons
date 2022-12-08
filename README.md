# check_linux_daemons
nagios check for linux daemons controlled by systemd

# Requirements
perl, SSH key pair auth

# Configuration
Add a section similar to the following to the services.cfg file on the nagios server.

define service{
        use                             generic-service
        host_name                       linux01.example.com
        service_description             linux daemons
        check_command                   check_by_ssh!"/usr/local/nagios/libexec/check_linux_daemons"
        }
        
# Output
You will see output similar to the following:
```
linux daemons OK container-gitlab.service:active ngt_guest_agent.service:active sshd.service:active snmpd.service:active rsyslog.service:active firewalld.service:active fail2ban.service:active crond.service:active chronyd.service:active auditd.service:active  Linux version:Oracle Linux Server 8.6|
```
