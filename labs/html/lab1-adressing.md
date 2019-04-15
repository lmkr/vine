<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.0 Transitional//EN"
"http://www.w3.org/TR/REC-html40/loose.dtd">
<html>
<head>
<meta http-equiv="expires" content="Fri, 02 Jan 1970 00:00:00 GMT">
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
<link href="http://daimi.au.dk/NPaI/style/style.css" rel=stylesheet type="text/css">
<title>NPaI - VNE Workshop 1</title>
<style type="text/css">
    .question { 
        border-width: 2px;
        border: solid;
        font-weight: bold;
        padding-top: 0.5em;
        padding-left: 0.5em;
        padding-right: 0.5em;
        margin-top: 0.3em;
    }
</style>
</head>
<body bgcolor="white">

<table cellspacing="0" cellpadding="0" border="0" width="100%">
  <tr>
    <td width="1%" valign="bottom">
      <table cellspacing="0" cellpadding="0" border="0">
	<tr valign="bottom">
	  <td width="179">
	    <img alt="" border="0" height="124" width="179"
	    src="http://daimi.au.dk/NPaI/img/segla.gif" align="bottom"> 
          </td>
	  <td width="465">
            <h2>Network Protocols and Internetworking</h2>
	    <img alt="" border="0" width="465" src="http://daimi.au.dk/NPaI/img/seglb.gif"
	    align="bottom"> 
          </td>
	</tr>
      </table>
    </td>
    <td width="99%" valign="bottom">
      <img alt="" border="0" height="124" width="100%" src="http://daimi.au.dk/NPaI/img/seglc.gif"
      align="bottom"> 
    </td>
  </tr>
</table>
<div class="body">

<table border="0" cellspacing="5" cellpadding="0" width="92%"><tr>


<td width="175" valign="top">
    <b>NPaI</b><br>
    <ul class="au-nav">
      <li><a href="./index.html">Home</a><p></li>
      <li><a href="./schedule.html">Schedule</a></li>
      <li><a href="./material.html">Material</a></li>
      <li class=markeret><a href="./projects.html">Projects</a></li>
      <li><a href="./exam.html">Exam</a></li>      
      <li><a href="./participants.html">Participants</a></li>      
      <li><a href="./links.html">Links</a></li>      
    </ul>
  </td>
  <td valign="top">

    <div class="au-sti">
    <a href="http://www.daimi.au.dk/">DAIMI</a> /
    <a href="http://www.daimi.au.dk/studies/map/CoursesOverviewFrame.html">Courses</a> /
    NPaI
    </div>

    <p>

    <h2>VNE Workshop 1</h2>

    <h2> IPv4 and IPv6 Address Resolution and Configuration</h2>

    <p>This workshop consists of two parts. The first part is dealing
    with IPv4 static address configuration, address resolution (ARP),
    and autoconfiguration (DHCP). The second part is dealing
    with IPv6 autoconfiguration and address resolution which is part
    of the Neighbour Discovery Protocol (NDP).</p> 

    <p>The overall goal of the workshop is to consolidate the material
    that has been covered in the lectures on IPv4 and IPv6 and get
    some experience working with basic IP concepts in practice.</p>


    <h2>Creating and Setting up the Laboratory</h2>

    <p>The same VNE laboratory is used for all the
    experiments. The first step is to create this laboratory using
    VNE:</p>

    <ul>
        <li>Start VNE, the VNE Manager application, and create a new
            laboratory. Remember that spaces are not allowed in
            the laboratory name. </li>

        <li>Add three nodes and one hub. Rename the nodes to "Router", "Node 1"
        and "Node 2", and connect all three nodes to the hub as
        illustrated below:</br>
        <img src=vne/step1-img1.png>
        </li>

        <li>Save the laboratory.</li>

        <li>Start the laboratory. Wait until the login prompt appears for all
        three nodes.</li>
        <li>Start Wireshark. Go to the <i>Capture</i>-menu, and select "Options...". Select the tap0-interface from the interface dropdown box. If tap0 is not in the list, close the "Capture Options"-dialog, stop the laboratory, start it again, and try again.</li>

        <li>Make sure that the "Update list of packets in real-time"-option is
        checked, and press the "Start" button in the "Capture Options" dialog. All traffic
            sent through the hub in the laboratory will now show up in Wireshark.
    </ul>


    <h2>Part 1: IPv4 Configuration and Address Resolution</h2>

    <p>The objective of these experiments is to configure the network
    with IPv4 addresses statically and automatically using the Dynamic
    Host Configuration Protocol (DHCP), and observe the behaviour of
    the ARP and ICMP protocols. DHCP can be used to configure more
    than just IP-addresses, but for simplicity this will not be
    covered in this workshop.</p>

    <p>The experiments consists of the following steps. When asked
    to fill in information, do so before continuing to the next step.

    <h3>Step 1: Static IPv4 Address Configuration</h3>
    <ul>
        <li>Login to "Router" and configure it with the IPv4 address 10.0.0.1 using the command:
        <pre>
        ifconfig eth0 up 10.0.0.1 netmask 255.255.0.0
        </pre>
        </li>
        <li>Login to "Node 1", and configure it with the IPv4 address 10.0.0.2
        using the command:
        <pre>
        ifconfig eth0 up 10.0.0.2 netmask 255.255.0.0
        </pre>
    </ul>

    <h3>Step 2: Observe ARP and Ping Packets</h3>
    <ul>
        <li>From "Router" ping "Node 1":
        <pre>
        ping -c 5 10.0.0.2
        </pre>
        This will send 5 ping packets to "Node 1".

        <div class="question" style="height: 20em;">
        Identify the ARP and Ping packets captured by Wireshark. Briefly explain the flow of the ARP
        and Ping packets that have been sent and received as an effect of the ping-command:
        <div>
        </li>
    </ul>

    <h3>Step 3: Setup DHCP Server</h3>
    <ul>
        <li>On the "Router" node, edit /etc/default/dhcp3-server using nano (or
        vim if you prefer), such that the last line looks like this:
        <pre>
        INTERFACES="eth0"
        </pre>
        </li>
        <li>Add the following to the end of /etc/dhcp3/dhcpd.conf:
        <pre>
            subnet 10.0.0.0 netmask 255.255.0.0 {
                range 10.0.0.3 10.0.0.255;
            }
        </pre>
        This tells the DHCP server to configure the network 10.0.0.0 with the
        netmask 255.255.0.0 such that addresses ranging from 10.0.0.3 to
        10.0.0.255 are assigned to clients.
        </li>
        <li>Start the DHCP server:
        <pre>
        /etc/init.d/dhcp3-server start
        </pre>
        </li>
    </ul>


    <h3>Step 4: Automatic IPv4 Address Configuration</h3>
    <ul>
        <li>Login to "Node 2", and run the command
        <pre>
        dhclient eth0
        </pre>
        This will start the DHCP client for autoconfiguration of eth0.
        <div class="question" style="height: 15em;">
            Identify the DHCP packets, and briefly explain the exchange of DHCP
            packets. What IPv4 address has been assigned to "Node 2"?
        <div>
        </li>
        <li>Finally, try to ping both "Node 1" and "Router", in order to see if
        the network has been configured successfully.
    </ul>


    <h2>Part 2: IPv6 Autoconfiguration and the Neighbour Discovery Protocol</h2>

    <p>The objective of these experiments is to observe how stateless
    IPv6 Autoconfiguration and Neighbour Discovery Protocol (NDP)
    works.</p>

    <p>Start this part by opening the laboratory that was created in
    the beginning of the workshop and connect WireShark to the
    hub.</p>

    <p>The experiments consists of the following steps. When asked
    to fill in information, do so before continuing to the next step.</p>

    <h3>Step 1: Configure IPv6 Router</h3>
    
    <p>In order to see how IPv6 autoconfiguration works with a router present, we
    need to configure the Router Advertisement Daemon (radvd) on the router node:

    <ul>
        <li>Login to the "Router" node and assign an IPv6 address to eth0 of the router by issuing the following command:
        <pre>
        ifconfig eth0 add 2001:878:402:2::1/64
        </pre>
        </li>
        <pre>
        ifconfig eth0 up
        </pre>
        <li>Edit /etc/radvd.conf using the nano editor (or vim if you prefer), so that it contains the following:
        <pre>
        interface eth0 {
            AdvSendAdvert on;
            prefix 2001:878:402:2::/64 {
            };
        };
        </pre>

        <p>This tells the radvd daemon to send out router advertisements on interface 0, containing the prefix 2001:878:402:2::/64.</p>

        </li>
        <li>Start the radvd daemon by:
        <pre>
        /etc/init.d/radvd start
        </pre>
        In Wireshark you will now see a number of router advertisements.
        </li>
    </ul>

    <h3>Step 2: Configure Hosts using Autoconfiguration</h3>

    <p>We now have a node on the network which acts as an IPv6
    router. Next step is to see how the two hosts (node 1 and node 2)
    can be autoconfigured using the prefix advertised by the IPv6
    router.</p>

    <ul>
        <li>Login to one of the two hosts (node 1 or node 2) and bring up the eth0 interface using:
        <pre>
        ifconfig eth0 up
        </pre>

        <li>Inspect the interface by typing:
        <pre>
        ifconfig eth0
        </pre>
        <div class="question" style="height:8em;">
            What IPv6 addresses are configured for the interface prior to autoconfiguration?
        </div>

        </li>
        <li>Enable IPv6 autoconfiguration and Duplicate Address Detection by issuing the following 4 commands:
        <pre>
        echo 1 > /proc/sys/net/ipv6/conf/eth0/autoconf
        echo 1 > /proc/sys/net/ipv6/conf/eth0/dad_transmits
        echo 1 > /proc/sys/net/ipv6/conf/eth0/accept_ra
        echo 3 > /proc/sys/net/ipv6/conf/eth0/router_solicitations
        </pre>
        </li>

        <li> Force autoconfiguration by bringing the interface down and up again:
        <pre>
        ifconfig eth0 down
        ifconfig eth0 up
        </pre>
        Watch the Wireshark window.
        </li>
        <li>Inspect the configuration of eth0:
        <pre>
        ifconfig eth0
        </pre>
        <div class="question" style="height:10em;">What IPv6 addresses are configured for eth0?
        </div>

        <div class="question" style="height:10em;">What is the IPv6-network
            address used, and how can you tell?
        </div>

        <div class="question" style="height:20em;">Briefly explain the ICMPv6
            packets capture by Wireshark. You can ignore packets destined for
            ff02::16.
        </div>

        </li>
        <li>Ping the router (2001:878:402:2::1):
        <pre>
         ping6 -c 5 2001:878:402:2::1
        </pre>
        <div class="question" style="height: 20em;">Briefly explain the ICMPv6
            packets exchanged.</div>
        </li>
    </ul>

    <h3>Step 3: IPv6 Address Calculation</h3>

    <p>Having configured one of the hosts using IPv6
    autoconfiguration, the final step is to predict the IPv6 address
    that will be assigned to the other node.  Recall that the EUI-64
    identifier is calculated from the MAC-address by taking the lower
    24-bits and the upper 24-bits and inserting FF:FE between them and
    inverting the UL-bit. The EUI-64 identifier is then used together
    with the network prefix to construct the global unicast
    address.</p>

    <p>An example: 
    
    <pre> 
    MAC address   : 00:B0:D0:66:6F:54 
    Network prefix: 2001:1:1:1::/64 
    EUI-64        : 02:B0:D0:FF:FE:66:6F:54 
    Global unicast: 2001:1:1:1::02B0:D0FF:FE66:6F54 </pre>

    <li>Login to the non-configured node, and obtain the MAC-address by running
    <pre>
    ifconfig eth0
    </pre>

    <div class="question">Calculate the global unicast
        IPv6 address from the MAC-address and the prefix which the router is
        configured for.
    <pre>
    MAC            :

    Network Prefix : 
    
    EUI-64         :

    Global Unicast :

    </pre>
        </div>
    </li>
    <li>Now enable autoconfiguration:
    <pre>
    echo 1 > /proc/sys/net/ipv6/conf/eth0/autoconf
    echo 1 > /proc/sys/net/ipv6/conf/eth0/dad_transmits
    echo 1 > /proc/sys/net/ipv6/conf/eth0/accept_ra
    echo 3 > /proc/sys/net/ipv6/conf/eth0/router_solicitations
    </pre>
    and reconfigure the interface:
    <pre>
    ifconfig eth0 down
    ifconfig eth0 up
    </pre>
    </li>
    <li>Inspect the assigned IPv6-addresses. Does the address configured for the interface match the one calculated? If not try to calculate
    it again.
    </li>
    <li>As a final test, ping the node which was autoconfigured using the command (replacing the x's with the address):
    <pre>
    ping6 -c 5 xxxx:xxxx:xxxx:xxxx::x
    </pre>
    </li>

  </td>
</tr>
</table>

</div>
<p>
<hr noshade size=1>
<div align=right class=body>
<small>
<!-- hhmts start --> Last modified: Thu Sep 14 2006 <!-- hhmts end -->
</small>
</body>
</html>
