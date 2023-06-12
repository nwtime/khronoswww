---
title: "Welcome to The Khronos Project"
---

The Khronos Project aims to provide an extension to the [NTPv4](https://www.ntp.org/) client, designed to achieve:

* Provable security in the face of fairly powerful MitM attacks with negligible probability for successful timeshifting attacks.
* Backwards-compatibility so that there are no changes to NTP servers and limited software changes to the NTP client's system process.
* Low computational and communication overhead with few queries to NTP servers.

Since Khronos does not affect the wire protocol, the Khronos mechanism is applicable to any current or future time protocol.

Khronos is currently an [IETF draft](https://datatracker.ietf.org/doc/draft-ietf-ntp-chronos/). A Python and a C implementation are [available](https://github.com/netars/chronos).