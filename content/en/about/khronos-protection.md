---
title: "What does Khronos protect from?"
description: "Learn more about the Khronos Project"
---

# What does Khronos protect from?

Khronos is designed to protect NTP clients from time _shifting attacks_.

<div class="container-fluid">
  <div class="row">
    <div class="col-xl-6 col-lg-6 col-md-6">
	  <h4>Who can enforce time shifting attacks?</h4>
	  <p><b>Time shifting</b> attacks on NTP clients can be based on interfering with the communication between the NTP clients and servers or compromising the servers themselves. Time shifting attacks on NTP are possible even if NTP communication is encrypted and authenticated. A weaker machine-in-the-middle (MitM) attacker can shift time simply by dropping or delaying packets, whereas a powerful attacker, who has full control over an NTP server, can do so by explicitly determining the NTP response content.</p>
	  <p><b>Khronos threat model:</b> Khronos is designed to protect NTP client against powerful attacker, including MitM, who is assumed to control a subset (e.g., third) of the servers in NTP pools and is capable of fully determining the values of the time samples returned by these NTP servers. The threat model encompasses a broad spectrum of attackers, ranging from fairly weak (yet dangerous) MitM attackers only capable of delaying and dropping packets (for example using the <a href="https://en.wikipedia.org/wiki/Bufferbloat">Bufferbloat</a> attack) to extremely powerful attackers who are in control of (even authenticated) NTP servers.</p>
	</div>
    <div class="col-xl-6 col-lg-6 col-md-6">
	  <figure class="figure">
        <img src="/about/Khronos_protection.jpg" alt="Khronos Protection" class="figure-img img-fluid">
      </figure>
    </div>
  </div>
</div>

The attackers covered by this model might be, for example, (1) in direct control of a fraction of the NTP servers (e.g., by exploiting a software vulnerability), (2) an ISP (or other Autonomous-System-level attacker) on the default BGP paths from the NTP client to a fraction of the available servers, (3) a nation state with authority over the owners of NTP servers in its jurisdiction, or (4) an attacker capable of hijacking (e.g., through DNS cache poisoning or BGP prefix hijacking) traffic to some of the available NTP servers.
***