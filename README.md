# wyze_cam_notes

After installing wz_wini, turn on IP tables and create following file to add some basic firewall rules



nano /media/mmc/wz_mini/etc/rc.local.d/firewall.sh

#!/bin/sh
#set some basic firewall rules
/opt/wz_mini/bin/iptables -A INPUT -m state --state RELATED,ESTABLISHED -j ACCEPT
/opt/wz_mini/bin/iptables -A INPUT -i lo -j ACCEPT
/opt/wz_mini/bin/iptables -A INPUT -p tcp --dport 22 -j ACCEPT
/opt/wz_mini/bin/iptables -A INPUT -p tcp --dport 80 -j ACCEPT
/opt/wz_mini/bin/iptables -A INPUT -p tcp --dport 1984 -j ACCEPT
/opt/wz_mini/bin/iptables -A INPUT -p tcp --dport 8554 -j ACCEPT
/opt/wz_mini/bin/iptables -A INPUT -p tcp --dport 8555 -j ACCEPT
/opt/wz_mini/bin/iptables -A INPUT -j DROP


chmod +x /media/mmc/wz_mini/etc/rc.local.d/firewall.sh

