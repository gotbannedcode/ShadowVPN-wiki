1. Download [chnroutes script](https://github.com/clowwindy/ShadowVPN/blob/master/tools/chnroutes.sh).

2. Save it to `/etc/shadowvpn/chnroutes.sh`. Then

        chmod +x /etc/shadowvpn/chnroutes.sh

3. Create `/etc/hotplug.d/iface/35-chnroutes`

        #!/bin/sh
        [ ifup = "$ACTION" ] && {
          [ wan = "$INTERFACE" ] && {
             /etc/shadowvpn/chnroutes.sh
          }
        }

4. Restart network

        /etc/init.d/network restart