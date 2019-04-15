<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.0 Transitional//EN"
"http://www.w3.org/TR/REC-html40/loose.dtd">
<html>
<head>
<meta http-equiv="expires" content="Fri, 02 Jan 1970 00:00:00 GMT">
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
<link href="http://daimi.au.dk/NPaI/style/style.css" rel=stylesheet type="text/css">
<title>NPaI - VNE Workshop 2</title>
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
    table.list {
        border-style: solid;
        border-width: 1px;
        border-spacing: 0px;
    }
    table.list td, table.list th {
        border-style: solid;
        border-width: 1px;
    }
    
    td.contents li {
        margin-top: 1.3em;
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
      <li class=markeret>Projects</li>
      <li><a href="./exam.html">Exam</a></li>      
      <li><a href="./participants.html">Participants</a></li>      
      <li><a href="./links.html">Links</a></li>      
    </ul>
  </td>
  <td valign="top" class="contents">

    <div class="au-sti">
    <a href="http://www.daimi.au.dk/">DAIMI</a> /
    <a href="http://www.daimi.au.dk/studies/map/CoursesOverviewFrame.html">Courses</a> /
    NPaI
    </div>

    <p>

    <h2>VNE Workshop 2</h2>
    <h3>Group Information</h3>
    <table class="list">
        <tr>
            <th style="width: 25em">Name</th>
            <th style="width: 10em">Student Id</th>
        <tr>
        <tr style="height: 3em">
            <td>&nbsp;</td>
            <td>&nbsp;</td>
        </tr>
        <tr style="height: 3em">
            <td>&nbsp;</td>
            <td>&nbsp;</td>
        </tr>
        <tr style="height: 3em">
            <td>&nbsp;</td>
            <td>&nbsp;</td>
        </tr>
        <tr style="height: 3em">
            <td>&nbsp;</td>
            <td>&nbsp;</td>
        </tr>
    </table>

    <h2>IP Routing</h2>

    <p>This workshop consists of two parts. The first part shows how
    routing can be setup statically in an IP network, while the second
    part uses the RIP protocol to perform dynamic routing.  We will
    only be using IPv4 in this workshop as the IPv4 addresses are
    shorter and hence easier to deal with. The basic concepts are the
    same for IPv6 networks.</p>

    <h2>Downloading the Laboratory</h2>

    <p>A precreated laboratory will serve as a base for all
    experiments in the workshop. In the second part it will be
    extended slightly to be used with dynamic routing. The topology of
    the laboratory is as follows:</p>

    <p><img src="ip-routing-lab.png"><br></li>

    <p>The laboratory can imported into VNE by the following
    steps:</p>

    <ul>

    <li> Start VNE.

    <li> In VNE, press ALT-F2 in order to bring up the "Execute
    program"-dialog. Type in "firefox", and wait for it to start.

    <li> Point FireFox to
<tt>http://www.daimi.au.dk/NPaI/routing-workshop.tar.bz2</tt> by typing it in
the location bar. When asked what to do with the file, choose "Save
As". The file will now be saved to the desktop.

    <li> When FireFox is finished downloading, close both FireFox
    windows.

    <li> Locate the "routing-excercise.tar.bz2" file in the
    desktop, and right-click it. Select "Extract To...".

    <li> A dialog will popup. Type in "/root/labs" in the "Extract
    to:"-field, and press the "Extract"-button. The process will
    start, and once finished the window will close.

    </ul>

    

    <h2>Setting up the Laboratory</h2>


    <p>The network nodes in the laboratory are to be configured with
    static IPv4 addresses that are retained between laboratory
    restarts as explained in the following.</p>

    <ul>

        <li>Start the VNE Manager application and open the
        "routing-workshop" lab that was downloaded in the previous
        step.


        <li>Start the laboratory and wait for all network nodes to
        startup (showing the login-prompt)</li>

        <li>The IP addresses of all network nodes are to be
        configured according to the following address allocation for
        the four networks (Net 1, Net 2, Net 3, and Net 4):<br><br>

            <table class="list">
                <tr>
                    <th>Hub</th>
                    <th>Network address</th>
                    <th>Network mask</th>
                </tr>
                <tr>
                    <td>Net 1</td>
                    <td>10.1.0.0</td>
                    <td>255.255.0.0</td>
                </tr>
                <tr>
                    <td>Net 2</td>
                    <td>10.2.0.0</td>
                    <td>255.255.0.0</td>
                </tr>
                <tr>
                    <td>Net 3</td>
                    <td>10.3.0.0</td>
                    <td>255.255.0.0</td>
                </tr>
                <tr>
                    <td>Net 4</td>
                    <td>10.4.0.0</td>
                    <td>255.255.0.0</td>
                </tr>
            </table>
            <br>

        The allocation of the IP addresses to the interfaces of each node is as follows:<br><br>

        <table class="list">
            <tr>
                <th>Node Name</th>
                <th>eth0 address</th>
                <th>eth0 netmask</th>
                <th>eth1 address</th>
                <th>eth1 netmask</th>
            </tr>
            <tr>
                <td>Host 1</td>
                <td>10.1.0.2</td>
                <td>255.255.0.0</td>
                <td>N/A</td>
                <td>N/A</td>
            </tr>
            <tr>
                <td>Host 2</td>
                <td>10.3.0.2</td>
                <td>255.255.0.0</td>
                <td>N/A</td>
                <td>N/A</td>
            </tr>
            <tr>
                <td>Host 3</td>
                <td>10.4.0.2</td>
                <td>255.255.0.0</td>
                <td>N/A</td>
                <td>N/A</td>
            </tr>
            <tr>
                <td>Router 1</td>
                <td>10.1.0.1</td>
                <td>255.255.0.0</td>
                <td>10.2.0.1</td>
                <td>255.255.0.0</td>
            </tr>
            <tr>
                <td>Router 2</td>
                <td>10.2.0.2</td>
                <td>255.255.0.0</td>
                <td>10.3.0.1</td>
                <td>255.255.0.0</td>
            </tr>
            <tr>
                <td>Router 3</td>
                <td>10.2.0.3</td>
                <td>255.255.0.0</td>
                <td>10.4.0.1</td>
                <td>255.255.0.0</td>
            </tr>
        </table>
        <br>

        <p>The IP address configuration is made persistent between
        laboratory shutdowns by adding the configuration lines to
        <tt>/etc/init.d/network</tt> which will be loaded during
        startup.</p>

        <p>Login to "Host 1", and add the following to the
        end of <tt>/etc/init.d/network:</tt></p>

        <pre>
        ifconfig eth0 up 10.1.0.2 netmask 255.255.0.0
        </pre>

        <p>This will configure eth0 of Host 1 with the IP address 10.1.0.2 and the
        netmask 255.255.0.0. The configuration will not be effectively
        immediately, run <tt>/etc/init.d/network</tt> to activate the
        configuration. 
        </li>

        <li>Configure the two other hosts as done in the previous
        step, using the correct address according to the IP address
        allocation table. The routers will be configured in the next
        step. Remember to run <tt>/etc/init.d/network</tt> in order to
        activate the IP configuration. </li>

        <li>The routers are configured by adding three lines to
        <tt>/etc/init.d/network</tt>. One for each interface, and one
        to enable IP packet forwarding. Login to "Router 1" and add
        the following to <tt>/etc/init.d/network</tt>:

        <pre>
        ifconfig eth0 up 10.1.0.1 netmask 255.255.0.0
        ifconfig eth1 up 10.2.0.1 netmask 255.255.0.0
        echo 1 > /proc/sys/net/ipv4/ip_forward
        </pre>

        Remember to run <tt>/etc/init.d/network</tt> in order to
        activate the IP configuration.

        </li>

        <li>Configure the remaining two routers in the same manner as
        "Router 1" was configured, using the IP addresses from the IP
        address allocation table. Remember to run
        <tt>/etc/init.d/network</tt> in order to activate the IP
        configuration.</li>

        <li>Test that "Host 1" can ping eth0 (10.1.0.1) of "Router 1".
	</li>
	<li>On "Host 1" run:
	<pre>
	route
	</pre>

	this will show the routing table of the host.
        <div class="question" style="height: 15em;">Use the output from route to explain why "Host 1" cannot ping eth1 (10.2.0.1) of "Router 1".</div>
        <div class="question" style="height: 20em;">Which nodes can ping each other, and which cannot? Explain why this is so (the output of the route command on each node might help you).</div>
        </li>
    </ul>

    <h2>Part 1: Static Routing</h2>

    <p>Having set up the laboratory and seen that the current routing
    information is not enough, we will add the missing routes
    manually, such that all nodes can communicate with each other.</p>

    <ul>
        <li>On "Host 1" add "Router 1" as default router (gateway) using the following command:
        <pre>
        route add default gw 10.1.0.1
        </pre>
        </li>
        <li>From "Host 1" ping eth1 (10.2.0.1) of "Router 1" (this should now work).
        <div class="question" style="height: 20em;">Which IP addresses can "Host 1" reach, i.e., receive a ping-reply from? Explain why.</div>
        </li>
        
                <div class="question" style="height: 20em;">For the same reasons as "Host 1" could not ping eth1 of "Router 1" before we added a default route, "Router 1" cannot reach eth1 of "Router 2". Is it reasonable to solve this problem by adding a default gateway?</div>

        <li>In order for "Router 1" to be able to communicate with eth1 of "Router 2", we need to setup
            a route to the network 10.3.0.0 with netmask 255.255.0.0. This is done by entering the following
            on the commandline of "Router 1":
            <pre>
        route add -net 10.3.0.0 netmask 255.255.0.0 gw 10.2.0.2
            </pre>
            This tells the routing system, that network 10.3.0.0 (with netmask 255.255.0.0) is available
            via the IP address 10.2.0.2.
            <div class="question" style="height: 20em;">Run the route command on "Router 1", and explain
            the contents of the routing table.</div>
            <div class="question" style="height: 30em;">What changes are to be made to the routing tables of the remaining network nodes, before all nodes can communicate with each other? Try it out.</div>
        </li>
    </ul>

    <h2>Part 2: Dynamic Routing</h2>

    <p>Having configured routing table entries manually, we now
    consider dynamic routing. We will use the Quagga routing suite
    which supports a number of routing protocols. Quagga consists of a
    number of daemons. For this workshop we will be using two Quagga
    daemons: Zebra and ripd. Zebra is responsible for making changes
    to the routing table of a node and communicating with the routing
    protocol daemon. Ripd is a router daemon implementing the RIP
    protocol.</p>

    <p> In order to be able to show that RIP can be used to change
    routes, we add a redundant router to the network:</p>

    <ul>

    <li>Stop the laboratory if it is running.</li>

    <li>Add a new network node, rename it to "Router 4", and connect
    it first to "Net 2" and then "Net 3". </li>

    <li>Start the laboratory, and configure "Router 4" by adding the
    following to /etc/init.d/network:

    <pre>
    ifconfig eth0 up 10.2.0.4 netmask 255.255.0.0
    ifconfig eth1 up 10.3.0.3 netmask 255.255.0.0
    echo 1 > /proc/sys/net/ipv4/ip_forward
    </pre>

    </li>

    </ul>
    
    <p>Next we configure zebra and ripd on "Router 1", such that it
    both announces routes and accepts routes from the other routers,
    but not "Host 1" (or generally RIP traffic from "Net 1"):</p>

    <ul>

    <li>Edit <tt>/etc/quagga/daemons</tt>, such that it contains "zebra=yes"
    and "ripd=yes".</li>

    <li>Create an empty zebra configuration by typing the following on
    the command line:

    <pre>
    touch /etc/quagga/zebra.conf
    chown quagga.quagga /etc/quagga/zebra.conf
    </pre>

    <p>The first line creates an empty configuration file, and the
    second changes the owner to the "quagga" user and the "quagga"
    group. It is a security requirement that the file exists and is
    owned by the right user.</p> </li>

    <li>Now create the ripd configuration by creating the file
    <tt>/etc/quagga/ripd.conf</tt> with the following contents:

    <pre>
    router rip
    network eth0
    network eth1
    
    timers basic 30 40 10
    
    redistribute kernel
    redistribute static
    
    interface eth1
      no ip rip authentication mode
    </pre>
    
    <p>The first three lines enable the RIP protocol (router rip), for
    the two interfaces.  "timers basic 30 40 10" changes the default
    timers of the RIP daemon, so that RIP announcements are send every
    30 seconds, routes timeout after 40 seconds, and are removed after
    10 seconds (in addition to the 40).</p>

    <p>The two "redistribute" lines means that the Quagga service will
    redistribute both kernel routes and static routes using RIP
    announcements.  Static routes are routes created manually, like we
    did in part 1, while kernel routes are routes which are
    automatically added when assigning IP addresses to interfaces.</p>

    <p>The last two lines tell the RIP daemon to accept updates on
    eth1 without authentication.  We do not use authentication here,
    as it will make configuration more difficult without yielding much
    new information. Also, we only want to receive updates from eth1,
    as "Host 1" should not be able to update routing information on
    the router.</p>

    <p>Change owner on <tt>/etc/quagga/ripd.conf</tt> using 

    <pre>
    chown quagga.quagga /etc/quagga/ripd.conf
    </pre>

    <p>Start the daemons by running</p>

    <pre>
     /etc/init.d/quagga start
    </pre>

    <li>Configure the remaining three routers using the previous step
    as a template. Remember to set the right interface in the second
    to last line (it has to be eth1 for "Router 1" and eth0 for all
    other routers). When Quagga has been successfully started on each
    router, inspect the routing tables using the "route" command.

    <p>Now, we setup Quagga on the hosts, such that they receive
    routing information, but do not redistribute any.</p>

    </li>
    
    
    <li>Edit <tt>/etc/quagga/daemons</tt>, such that it contains
    "zebra=yes" and "ripd=yes".</li>

    <li>Create an empty zebra configuration by typing the following on
    the command line:

    <pre>
    touch /etc/quagga/zebra.conf
    chown quagga.quagga /etc/quagga/zebra.conf
    </pre>

    </li>
    
    <li>Create the ripd configuration by creating the file
    <tt>/etc/quagga/ripd.conf</tt> with the following contents:

    <pre>
    router rip
    network eth0
            
    interface eth0
      no ip rip authentication mode
    </pre>

    <p>Remember to change owner with <tt>chown quagga.quagga
    /etc/quagga/ripd.conf</tt> and start Quagga, by running
    <tt>/etc/init.d/quagga start</tt>

    </li>
   
    <li>Ensure that you can ping "Host 2" from "Host 1". If not, there
        is a problem with the routing tables somewhere in the
        network.</li>
    
    <li>The program <tt>tracepath</tt> can be used to find out which
        paths packets travel in a network.  It works by setting the
        Time-To-Live (TTL) of a test packet to 1, and increasing it by
        one for each iteration. When a network node receives a packet
        with a TTL of 1, it responds with an ICMP message (TTL
        exceeded). Recall, that TTL is decreased by each node when
        handling it.

    <div class="question" style="height: 20em;">
        Run <tt>tracepath 10.3.0.2</tt> on "Host 1" to find the route
        packets travel from "Host 1" to "Host 2". Write down the
        IP addresses and the routers it corresponds to.
    </div>

    </li>
    
    <li>Packets destined to "Host 2", go either through "Router 2" or
        "Router 4". On the one that is being used, disable eth0 by
        typing <tt>ifconfig eth0 down</tt>. Inspect the routing table
        of "Router 1". After 10-30 seconds the route to 10.3.0.0 will
        be removed, and after yet another 10-30 seconds it will be
        replaced by a new routing entry, going through either "Router
        2" or "Router 4", depending on which was used before.

    <div class="question" style="height: 20em;"> Briefly explain what
        happens, both when the route is being removed and when it is
        being established again.  
    </div> 

    <div class="question" style="height: 20em;"> Run
        <tt>tracepath</tt> again on "Host 1" to find the route. Write
        it down and briefly explain if it is as expected.  
    </div>
    </li>

    <li>Finally, we want to investigate exactly which information is
        exchanged in the RIP messages. Start Wireshark, and open the capture
        options dialog, either by pressing CTRL+K or using the menu "Capture",
        and then the menu item "Options...". Select the any pseudo interface, and
        ensure that "Capture packets in promiscuous mode" is unchecked, and
        that "Update list of packets in real time" is checked. Press the
        "Start" button.
    </li>

    <li> Wait until you can see that a number of RIP messages have been
    captured by Wireshark, and then stop the capture. Inspect these packets.

    <div class="question" style="height: 15em;">
    Which routes does Router 1 advertise?  </div> </li>
   
    </ul>

    <h2>References</h2>

    <ul
    <li> <a href="http://www.quagga.net/ ">Quagga suite website</a></li>
    </ul>

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
