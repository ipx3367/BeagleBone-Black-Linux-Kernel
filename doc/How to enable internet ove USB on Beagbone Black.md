## How to enable internet ove USB on Beagbone Black

* ### BBB settings

  * add the dns on the /etc/systemd/resolved.conf

    ```
    DNS=8.8.8.8 168.95.1.1
    ```

  * add default gateway on the shell command

    ```
    route add default gw 192.168.7.1
    ```

  * restart the service

    ```
    sudo systemctl restart systemd-resolved
    ```

* ### HOST setting

  * enable IP Forward on /etc/sysctl.conf

    ```
    # Uncomment the next line to enable packet forwarding for IPv4
    net.ipv4.ip_forward=1
    ```

  * allow iptable

    ```
    sudo iptables --table nat --append POSTROUTING --out-interface [wlp2s0] -j MASQUERADE
    
    sudo iptables --append FORWARD --in-interface [wlp2s0] -j ACCEPT
    ```

  * enable ip forward on /proc

    ```
    sudo echo 1 > /proc/sys/net/ipv4/ip_forward
    ```

  * restart networking service

    ```
    service networking restart 
    ```

    
