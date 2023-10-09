---
title: "Khronos Guarantees"
description: "Learn more about the Khronos Project"
---

# Khronos Guarantees

**Time shifting attacks:** Analytical results show that if a local Khronos pool consists of 500 servers, 1/7 of whom are controlled by a machine-in-the-middle attacker, and 15 servers are queried in each Khronos poll interval, then success in shifting time of a Khronos client by even a small degree (100 ms), takes many years of effort (over 20 years in expectation).

**Dos Attacks:** In addition to evaluating the probability of an attacker successfully shifting time at the client's clock, we also evaluated the probability that the attacker succeeds in launching a DoS attack on the servers by causing many clients to enter a panic mode (and query all the servers in their local Khronos pools).

This probability is negligible even for an attacker who controls a large number of servers in client's local Khronos pools, and it is expected to take decades to force panic mode.

For further details see [Preventing (Network) Time Travel with Khronos](http://localhost:1313/downloads/ndss18-final231.pdf).

***