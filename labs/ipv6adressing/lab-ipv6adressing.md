## VNE Lab: IPv4 Address Configuration and Resolution

This lab explores IPv6 addressing auto-configuration. The objective of the experiments is to observe how stateless IPv6 Autoconfiguration and Neighbour Discovery Protocol (NDP)
works.

### Step 1: Creating and Setting up the Laboratory

The first step is to setup a virtual laboratory. This is done by completing step 1 from the IPv4 adressing lab:

https://github.com/lmkr/vine/blob/master/labs/ipv4adressing/lab-ipv4adressing.md

### Step 2: Configure IPv6 Router

In order to see how IPv6 autoconfiguration works with a router present, we
need to configure the Router Advertisement Daemon (radvd) on the router node:

- Login to the "Router" node and assign an IPv6 address to `eth0` of the router by issuing the following commands:

    ```
    ifconfig eth0 add 2001:878:402:2::1/64
    ifconfig eth0 up
    ```

- Edit `/etc/radvd.conf` using the nano editor (or vim if you prefer), so that it contains the following:

    ```
    interface eth0 {
        AdvSendAdvert on;
        prefix 2001:878:402:2::/64 {
        };
    };
    ```

 This tells the radvd daemon to send out router advertisements on interface 0, containing the prefix `2001:878:402:2::/64`


- Start the radvd daemon by:

  ```  
    /etc/init.d/radvd start
  ```

  In Wireshark you will now see a number of router advertisements.


### Step 3: Configure Hosts using Autoconfiguration

We now have a node on the network which acts as an IPv6
router. Next step is to see how the two hosts (node 1 and node 2)
can be autoconfigured using the prefix advertised by the IPv6
router.

- Login to one of the two hosts (node 1 or node 2) and bring up the eth0 interface using:

  ```
    ifconfig eth0 up
  ```
- Inspect the interface by typing:

  ```
    ifconfig eth0
  ```

  **Question:** What IPv6 addresses are configured for the interface prior to autoconfiguration?

- Enable IPv6 autoconfiguration and Duplicate Address Detection by issuing the following 4 commands:

    ```
    echo 1 > /proc/sys/net/ipv6/conf/eth0/autoconf
    echo 1 > /proc/sys/net/ipv6/conf/eth0/dad_transmits
    echo 1 > /proc/sys/net/ipv6/conf/eth0/accept_ra
    echo 3 > /proc/sys/net/ipv6/conf/eth0/router_solicitations
    ```

- Force autoconfiguration by bringing the interface down and up again:
    ```
    ifconfig eth0 down
    ifconfig eth0 up
    ```
    Watch the Wireshark window.

- Inspect the configuration of eth0:

    ```
    ifconfig eth0
    ```

    **Question:** What IPv6 addresses are configured for eth0?

    **Question:** What is the IPv6-network address used, and how can you tell?

    **Question:** Briefly explain the ICMPv6 packets capture by Wireshark. You can ignore packets destined for `ff02::16`.
    </div>


- Ping the router (`2001:878:402:2::1`):

    ```
     ping6 -c 5 2001:878:402:2::1
    ```

    **Question:** Briefly explain the ICMPv6 packets exchanged.


### Step 4: IPv6 Address Calculation

Having configured one of the hosts using IPv6
autoconfiguration, the final step is to predict the IPv6 address
that will be assigned to the other node.  Recall that the EUI-64
identifier is calculated from the MAC-address by taking the lower
24-bits and the upper 24-bits and inserting `FF:FE` between them and inverting the UL-bit. The EUI-64 identifier is then used together with the network prefix to construct the global unicast
address.

An example:

```
MAC address   : 00:B0:D0:66:6F:54
Network prefix: 2001:1:1:1::/64
EUI-64        : 02:B0:D0:FF:FE:66:6F:54
Global unicast: 2001:1:1:1::02B0:D0FF:FE66:6F54
```

- Login to the non-configured node, and obtain the MAC-address by running

 ```
 ifconfig eth0
 ```

 **Question:** Calculate the global unicast address by listing MAC, Network Prefix, EUI-64, and Global unicast.


- Now enable autoconfiguration:

 ```
 echo 1 > /proc/sys/net/ipv6/conf/eth0/autoconf
 echo 1 > /proc/sys/net/ipv6/conf/eth0/dad_transmits
 echo 1 > /proc/sys/net/ipv6/conf/eth0/accept_ra
 echo 3 > /proc/sys/net/ipv6/conf/eth0/router_solicitations
 ```
  and reconfigure the interface:

  ```
  ifconfig eth0 down
  ifconfig eth0 up
  ```

 **Question:** Inspect the assigned IPv6-addresses. Does the address configured for the interface match the one calculated? If not try to calculate it again.

- As a final test, ping the node which was autoconfigured using the command (replacing the x's with the address):

 ```
 ping6 -c 5 xxxx:xxxx:xxxx:xxxx::x
 ```
