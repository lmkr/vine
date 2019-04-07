<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
  <head>
    <meta http-equiv="expires" content="Fri, 02 Jan 1970 00:00:00 GMT">
    <meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
    <link href="./style/style.css" rel=stylesheet type="text/css">
    <title>NPaI - VNE Workshop 3</title><style type="text/css">
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
    <table cellspacing="0" cellpadding="0" border="0" width="100%" summary="">
      <tr>
        <td width="1%" valign="bottom">
          <table cellspacing="0" cellpadding="0" border="0" summary="">
            <tr valign="bottom">
              <td width="179">
                <img alt="" border="0" height="124" width="179" src="./img/segla.gif" align="bottom">
              </td>
              <td width="465">
                <h2>
                   Network Protocols and Internetworking 
                </h2>
                <img alt="" border="0" width="465" src="./img/seglb.gif" align="bottom">
              </td>
            </tr>
          </table>
        </td>
        <td width="99%" valign="bottom">
          <img alt="" border="0" height="124" width="100%" src="./img/seglc.gif" align="bottom">
        </td>
      </tr>
    </table>
    <div class="body">
      <table border="0" cellspacing="5" cellpadding="0" width="92%" summary="">
        <tr>
          <td width="175" valign="top">
            <b>NPaI</b>
            <br>
            <ul class="au-nav">
              <li>
                <a href="./index.html">Home</a>
                <br>
                <br>
              </li>
              <li>
                <a href="./schedule.html">Schedule</a>
              </li>
              <li>
                <a href="./material.html">Material</a>
              </li>
              <li class=markeret>
                 Projects 
              </li>
              <li>
                <a href="./exam.html">Exam</a>
              </li>
              <li>
                <a href="./participants.html">Participants</a>
              </li>
              <li>
                <a href="./links.html">Links</a>
              </li>
            </ul>
          </td>
          <td valign="top" class="contents">
            <div class="au-sti">
              <a href="http://www.daimi.au.dk/">DAIMI</a> / <a href="http://www.daimi.au.dk/studies/map/CoursesOverviewFrame.html">Courses</a> / NPaI 
            </div>
            <h2>
               VNE Workshop 3 
            </h2>
            <h3>
               Group Information 
            </h3>
            <table class="list" summary="People in group">
              <tr>
                <th style="width: 25em">
                   Name 
                </th>
                <th style="width: 10em">
                   Student Id 
                </th>
              </tr>
              <tr style="height: 3em">
                <td>
                   &nbsp; 
                </td>
                <td>
                   &nbsp; 
                </td>
              </tr>
              <tr style="height: 3em">
                <td>
                   &nbsp; 
                </td>
                <td>
                   &nbsp; 
                </td>
              </tr>
              <tr style="height: 3em">
                <td>
                   &nbsp; 
                </td>
                <td>
                   &nbsp; 
                </td>
              </tr>
              <tr style="height: 3em">
                <td>
                   &nbsp; 
                </td>
                <td>
                   &nbsp; 
                </td>
              </tr>
            </table>
            <h2>IPv6 Transition Mechanisms</h2> 

<p>The goal of this workshop is to get hands-on experience with
IPv4-IPv6 transition mechanisms and consists of two parts. The
first part deals with simple IPv6-in-IPv4 tunnelling, while the second
part explores the Dual Stack Transition Mechanism (DSTM).</p>
            
            <h2>Downloading the Laboratories</h2>
            Each of the two parts of the workshop have a precreated laboratory that must downloaded.
            The laboratory for the first part is preconfigured with topology and IP addresses, while the laboratory for the second
            part comes with a modified Linux OS kernel that supports DSTM. The precreated laboratories can be downloaded using the following steps: 
            <br/>
            <ul>
            	<LI>Start VNE.</LI>
            	<li>In VNE, press ALT-F2 in order to bring up the "Execute Program"-dialog. Type in "firefox", and wait for it to start.</li>
            	<li>Point FireFox to <tt>http://www.daimi.au.dk/NPaI/transition-workshop.tar.bz2</tt> by typing it in the location bar. When asked what to do with the file, choose "Save As". The file will now be saved to the desktop. </li>
            	<li>When FireFox has finished downloading, close both FireFox windows.</li>
            	<li>Locate the <tt>transition-workshop.tar.bz2</tt> file on the desktop and right-click it. Select "Extract to...".</li>
            	<li>A dialog will popup. Type in <tt>/root/labs</tt> in the "Extract to:"-field, and press the "Extract"-button. The process will start, and once finished the window will close.</li>
            </ul>
            
            <h2>Part 1: Simple Tunnel Setup</h2>
            <p>
            Before dealing with the more complex DSTM mechanism, we first consider the process of setting
            up a single IPv6-in-IPv4 tunnel.
            </p>
            
            <p>
            The IPv6-in-IPv4 tunnel allows connections to IPv6 networks through IPv4 networks. This
            is what is used when connecting to the <a href="www.hexago.com">Hexago network</a> or other IPv6 networks through the Internet.<br/>            
            </p>
            <ul>
            	<LI>Start the VNE Manager and load the "simple-tunnel-lab" laboratory. The topology of the laboratory is as follows:<br/>
            	<IMG src="workshop3-lab1.png" width="627" height="436" alt="Simple Tunnel lab">
            	</LI>
            	<li><p>Start the laboratory, and wait until all nodes have started up completely. The laboratory is preconfigured with
            	the following IP addresses:<br><br>
            	<table class="list" summary="IP Address Assignment">
            		<TR>
            			<TH>Network Node</TH>
            			<TH>eth0 (IP / netmask)</TH>
            			<th>eth1 (IP / netmask)</th>
            		</TR>
            		<tr>
            			<TD>Host 1</TD>
            			<td>2001:878:402:1:XX / 64</td>
            			<td>N/A</td>
            		</tr>
            		<tr>
            			<TD>Host 2</TD>
            			<td>10.0.0.3 / 255.255.255.0</td>
            			<td>N/A</td>
			</tr>
			<tr>
				<TD>Host 3</TD>
				<td>2001:878:402:2:XX / 64</td>
				<td>N/A</td>
			</tr>
            		<tr>
            			<td>Router 1</TD>
            			<td>2001:878:402:1::1 / 64</td>
            			<td>10.0.0.1 / 255.255.255.0</td>
			</tr>
			<tr>
				<TD>Router 2</TD>
				<td>10.0.0.2 / 255.255.255.0</td>
				<td>2001:878:402:2::1 / 64</td>				
			</tr>			
            	</table>
            	
                <p>An XX in an IPv6 address means that the interface is configured using stateless autoconfiguration and will configure an address with the prefix given to the router on the corresponding network.</p>
            	<p>
            	Try to ping "Router 1"(eth0) from "Host 1", "Router 1"(eth1) from "Host 2", and "Router 2"(eth1) from "Host 3".
            	This should work without any problems. 
            	<div class="question" style="height: 20em;">Try to ping eth1 of "Router 1" from "Host 1", why is this not possible?</div>
            	
            	</LI>
	</ul>
		
	Now, we setup a 6-in-4 tunnel between "Router 1" and "Router 2", such that "Host 1" and "Host 3" can communicate using
	IPv6.
	
	<ul>
		<li>Login to "Router 1" and execute the following commmand:
		<pre>
	iptunnel add tun0 mode sit ttl 64 remote 10.0.0.2 local 10.0.0.1
		</pre>
		This will create a virtual network interface called <tt>tun0</tt>. The tunnel uses <tt>sit</tt> mode, which stands for
		Simple Internet Transition. Packets sent to the interface are encapsulated in IPv4 packets and send to the remote endpoint (10.0.0.2). 
		IPv4 packets containing IPv6 packets received on the local endpoint (10.0.0.1) are decapsulated and delivered through 
		the tunnel interface. The
		<tt>ttl 64</tt> specifies that the TTL of the generated IPv4
		packets is to be set to 64. 
		</li>
		
		<li>Setup an IPv6 address on the <tt>tun0</tt> interface:
		<pre>
	ifconfig tun0 up
	ifconfig tun0 add 2001:878:402:3::1/64
		</pre>
		Note that we are using a new network prefix rather than one of the two already used. This makes the interface easier to use, as all packets for the 2001:878:402:3/64 prefix are automatically routed to the <tt>tun0</tt> interface.
		</li>
		
		<li>Login to "Router 2" and create the other endpoint of the tunnel:
		<pre>
	iptunnel add tun0 mode sit ttl 64 remote 10.0.0.1 local 10.0.0.2
	ifconfig tun0 up
	ifconfig tun0 add 2001:878:402:3::2/64
		</pre>
		</li>
		<li>Ensure that you can ping 2001:878:402:3::1 from "Router 2".
		<div class="question" style="height: 15em;">Currently, it is not possible to ping 2001:878:402:1::1 from "Router 2". 
		Briefly explain why.</div>
		</li>
		
		<li>On "Router 1" add a route to the 2001:878:402:2/64 network by running:
		<pre>
	route -6 add 2001:878:402:2::/64 gw 2001:878:402:3::2
		</pre>
		</li>
		
		<li>On "Router 2" add a route to the 2001:878:402:1/64 network:
		<pre>
	route -6 add 2001:878:402:1::/64 gw 2001:878:402:3::1
		</pre>
		</li>
		
		<li>Ensure that you can ping 2001:878:402:1::1 from both "Router 2" and "Host 3".</li>
		
		<li>Use the command <tt>route -6</tt> to inspect the routing
		tables on "Router 1" and "Router 2", and observe how
		the tunnel endpoints are being used as interfaces.

		<li>Start Wireshark, and capture packets from IPv4 Net. Ping "Host 3" from "Host 1".</li>
		
		<li>After a couple of ping requests have been answered, stop the ping and Wireshark capture.</li>
		
		<li>Inspect the ping packets captured.
		<div class="question" style="height: 20em;">Briefly explain the structure of the ping packets captured.</div>
		</li>
		<li>Stop the laboratory.</li>
            </ul>
            
            
          <h2>Part 2: DSTM</h2>
          Having worked with IPv6-in-IPv4 tunnelling, we now turn to dealing with the opposite, i.e., how to connect to IPv4 nodes through an
          IPv6 network. For this we use the implementation of the Dual Stack Transition Mechanism provided by ENST Bretagne.
          
          <ul>
          	<LI>Open the "dstm-lab" laboratory. The topology of this laboratory is as follows:<br/>
          	 <IMG src="workshop3-lab2.png" width="321" height="418" alt="DSTM Lab">

          	 <p>"DSTM GW" will act as both DSTM server and border
          	 router, and also be handling the IPv6 network
          	 prefix.</p>

          	 <p>As before, the laboratory comes preconfigured. The
          	 configuration of IP addresses is as follows:<br><br>

          	 <table class="list" summary="IP Address list">
          	 	<TR>
          	 		<Th>Network Node</Th>
          	 		<th>eth0 (IP / netmask)</th>
          	 		<th>eth1 (IP / netmask)</th>
          	 	</TR>
          	 	<tr>
          	 		<TD>Host 1</TD>
          	 		<td>2001:878:402:2::XX / 64</td>
          	 		<td>N/A</td>
			</tr>
			<tr>
				<TD>Host 2</TD>
				<td>2001:878:402:2::XX / 64</td>
				<td>N/A</td>
			</tr>
			<tr>
				<TD>Host 3</TD>
				<td>10.0.0.10 / 255.255.255.0 </td>
				<td>N/A</td>
			</tr>
			<tr>
				<TD>DSTM GW</TD>
				<td>2001:878:402:2::1 / 64</td>
				<td>10.0.0.1 / 255.255.255.0 </td>
			</tr>
          	 </table>

          	<p>An XX in an IPv6 address means that the interface is configured using stateless autoconfiguration and will receive
            	an address with the prefix given to the corresponding router.</p>
          	</LI>
          	
          	<li>Start the laboratory</li>
          	
          	<li>In order to familarise yourself with the IP addresses assigned (especially those autoconfigured), 
          	ping "Host 2" from "Host 1", and "Host 3" from "DSTM GW".
          	</li>          	          	
          	
          	<div class="question" style="height: 20em;">From "Host 1" ping "Host 3", this should not work, why not?</div>

	  </ul>
	  
	  We start by setting up the DSTM server/gateway. In the DSTM implementation used both the server and the gateway functionality
	  is implemented in the daemon program named <tt>rpcdstmd</tt>.
	  <ul>
	  	<LI>On the "DSTM GW", create <tt>/etc/rpcdstmd.args</tt> with the following content:
	  	<pre>
	tsp=3545
	authmode=anonymous	
	  	</pre>
	  	Create <tt>/etc/rpcdstmd.conf</tt> with the following content:
	  	<pre>
	default-lease-time 900;
	tep6 2001:878:402:2::1;
	tep4 10.0.0.1;
	
	subnet 10.0.1.0 netmask 255.255.255.0 {
		range 10.0.1.1 10.0.1.200;
	}
	  	</pre>
	  	Start the rpcdstmd daemon by running <tt>/etc/init.d/rpcdstmd start</tt>.
	  	</LI>
	  	
	  	<li>
	  	On "Host 1", create <tt>/etc/dstmd.args</tt> with the following content:
	  	<pre>
	tspserver=2001:878:402:2::1
	port=3545
	authmode=anonymous
	  	</pre>
	  	Start the DSTM daemon by running <tt>/etc/init.d/dstmd start</tt>. The logfile <tt>/var/log/dstmd.log</tt> will be used
	  	by the DSTM daemon to log information which can be useful for debugging purposes in case problems arise. 
	  	</li>
	  	
	  	<li>Use Wireshark to capture packets from the IPv6 network.</li>
	  	<li>From "Host 1" ping "Host 3", this time it should work.
	  	<div class="question" style="height: 15em;">Type <tt>ifconfig</tt> in order to see all interfaces configured on "Host 1".
	  	You will notice a new interface called <tt>dti0</tt>, what do you think the purpose of this interface is? (hint: check the IP 
	  	address it is configured with)</div>
	  	</li>	  	
	  	<li>Stop capturing packets with Wireshark, and inspect them.
	  	<div class="question" style="height: 25em;">You will notice a number of TCP packets sent between "Host 1" and "DSTM GW".
	  	Right click on one of them and choose "Follow TCP Stream". You will now get the raw contents of the communication. Red lines are messages sent by "Host 1", blue lines are messages sent by "DSTM GW". Briefly explain what the protocol does.</div>
	  	<div class="question" style="height: 20em;">Close the TCP Stream window, and clear the contents of the Filter text-field by pressing the "Clear" button in Wireshark. Explain how the IPv4 ping packets
	  	are sent over the IPv6 network.</div>
	  	</li>
	  	
	  	<li>Setup the DSTM daemon on "Host 2", and try to ping "Host 3" from "Host 2".
	  	<div class="question" style="height: 10em;">What IPv4 address is assigned to Host 2? How did you find out?</div>
	  	</li>
	  </ul>
          
          <h2>References</h2>
          <ul>
          	<LI>DSTM Website: <a href="http://www.ipv6.rennes.enst-bretagne.fr/dstm/">http://www.ipv6.rennes.enst-bretagne.fr/dstm/</a></LI>
          </ul>
          </td>
        </tr>
      </table>
    </div>
    <hr noshade=noshade size=1>
    <div align=right class=body>
      <small>
<!-- hhmts start --> Last modified: Thu Sep 24 2007 <!-- hhmts end -->
</small>
    </div>
  </body>
</html>
