---
title: "How does Khronos work?"
description: "Learn more about the Khronos Project"
---

# How does Khronos work?

#### Khronos is a watchdog

A watchdog is a mechanism that runs in the background, continuously monitoring client clock (which is updated by NTPv4) and calculating an estimated offset. When the offset exceeds a predefined threshold, this is interpreted as the client experiencing a time shifting attack. In this case, Khronos updates the client's clock.

When the client is not under attack, Khronos is passive, allowing NTPv4 to control the client's clock and providing the ordinary high precision and accuracy of NTPv4.

***

#### Khronos design 

Khronos periodically queries a set of m (tens) servers at random out of a large (hundreds) server pool in each Khronos poll interval.

Then, given a sample from each server, Khronos discards outliers by discarding the lowest third of the samples' offset values and highest third of the samples' offset values. Khronos checks that the following two conditions hold for the remaining sampled offsets:

* The maximal distance between every two offsets does not exceed 2w.
* The distance between the offsets average and Khronos inter-poll offset is at most ERR+2w.

If both conditions are satisfied, the average of the offsets is set to be the "Khronos time offset". Otherwise, resampling is performed.

This resampling process continues in subsequent Khronos poll intervals until the two conditions are both satisfied or the number of times the servers are re-sampled exceeds a "Panic Trigger" (K), in which case Khronos enters a "Panic Mode".

In panic mode, Khronos queries all the servers in its local Khronos pool, orders the collected time samples from lowest to highest and eliminates the lowest third and the highest third of the samples. The client then averages over the remaining samples, and sets this average to be the new "Khronos time offset".

For recommended parameters see section 3.3 of the [IETF draft](https://datatracker.ietf.org/doc/draft-ietf-ntp-chronos/).


Note that to minimize the load on NTP servers while providing high security, the Khronos poll interval is around 10 times the NTPv4 poll interval. In each Khronos poll interval, if the Khronos time offset exceeds a predetermined threshold (denoted as H), an attack is indicated.

***