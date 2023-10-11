---
title: "Khronos Guarantees"
description: "Learn more about the Khronos Project"
---

# Khronos Guarantees

<div class="container-fluid">
  <div class="row">
    <div class="col-xl-6 col-lg-6 col-md-6">
	  <h4>Time shifting attacks</h4>
	  <p>Analytical results show that if a local Khronos pool consists of 500 servers, 1/7 of whom are controlled by a machine-in-the-middle attacker, and 15 servers are queried in each Khronos poll interval, then success in shifting time of a Khronos client by even a small degree (100 ms), takes many years of effort (over 20 years in expectation).</p>
	  <h4>Dos Attacks</h4>
	  <p>In addition to evaluating the probability of an attacker successfully shifting time at the client's clock, we also evaluated the probability that the attacker succeeds in launching a DoS attack on the servers by causing many clients to enter a panic mode (and query all the servers in their local Khronos pools).</p>
	  <p>This probability is negligible even for an attacker who controls a large number of servers in client's local Khronos pools, and it is expected to take decades to force panic mode.</p>
	  <p>For further details see <a href="/downloads/ndss18-final231.pdf">Preventing (Network) Time Travel with Khronos</a>.</p>
	</div>
    <div class="col-xl-6 col-lg-6 col-md-6">
      <figure class="figure">
        <img src="/about/khronos-improvement.jpg" class="figure-img img-fluid" style="margin-left: 40px;">
        <figcaption class="figure-caption">
          <p>The ratio (in log scale) between the probability that the attacker controls at least half of the queried servers (and can thus successfully attack today’s NTP clients) and the probability that the attacker controls two thirds of the queried servers (and can thus successfully attack Khronos) in one sampling iteration.</p>
        </figcaption>
       </figure>
    </div>
  </div>
</div>

***