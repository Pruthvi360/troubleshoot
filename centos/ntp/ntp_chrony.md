How to Install NTP Using Chrony in RHEL 8

NTP (Network Time Protocol) is a protocol which runs over port
123 UDP. NTP synchronize clients time and date with a master server. Chrony is
a default NTP client as well as an NTP server on Red Hat Enterprise Linux 8.

Service name = chronyd


Install chrony on system

# dnf install chrony -y

# yum install chrony -y



Now start the chronyd service, enable it to auto start at system boot and verify the running status:


# systemctl start chronyd

# systemctl status chronyd

# systemctl enable chronyd


Now Configure NTP Server Using Chrony:



set up your RHEL 8 server a master NTP time server. Open the /etc/chrony.conf:


# vim /etc/chrony.conf




Now search for the “allow” configuration directive and uncomment it and set the network addresses from which the clients are allowed:



#allow 192.168.0.0/16
now save and exit


Restart the chronyd service


# systemctl restart chronyd



Now open NTP service in firewalld configuration to allows for incoming NTP requests:


# firewall-cmd --permanent --add-service=ntp

# firewall-cmd –reload

# firewall-cmd --permanent --remove-service=chrony




Configure NTP Client


installing the chrony package on client side:


# yum install chrony


once installed, you can start, enable and verify the chronyd service status:


# systemctl start chronyd

# systemctl enable chronyd

# systemctl status chronyd

configure the system as a direct client of the NTP server. Open the /etc/chrony.conf


# vim /etc/chrony.conf



Now add the NTP server address




# Please consider joining the pool (http://www.pool.ntp.org/join.html).

pool2.rhel.pool.ntp.org iburst


comment out the default NTP servers set your RHEL 8 NTP server’s address.

Server 192.168.56.12


Save the changes in the file and close it.


restart the chronyd service


# systemctl restart chronyd



Now run the following command to show the current time sources (NTP server) that chronyd is accessing client side .


# chronyc sources


On the server, run the following command to display information about NTP clients information.




# chronyc clients
