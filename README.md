DNSSEC Monitoring
=================

This repository wants to supply tools for probing and monitoring DNSSEC-signed zones in an easy way.

Complexity of DNSSEC
--------------------

The DNS Security Extensions (DNSSEC) are a great step towards a more secure internet with trusted communication partners.
Unfortunately it's hard to dig into that topic - but if your have learned to drive the bicycle you may never want to walk by foot or forget about it.
Espacially transforming a insure DNS zone to a trusted and secure DNSSEC-signed zone is a cirtical step that want's to be observed.
These tools want to give DNS administrators a good feeling and overview about their zones and infrastructre.
Misconfigurations or critical trends should be reported immediately and possible approaches need to be offered to fix problems before escalating into incidents.

Monitoring DNSSEC components
----------------------------

DNS zones signed by DNSSEC depend on various information, components and configurations:
* EDNS0 support in nameserver
* TCP for querying long records
* DNSKEY in your zone
* Signing records with your DNSKEYs
* Validity period of RR signatures
* Progress of DNSKEY rollovers
* DNSKEY lifetimes and metadata
* Cover NXDOMAIN by NSEC chaining
* Relation between DS and DNSKEY records
* Master-Slave replication (integrity, operability)
* Timing: TTL, SOA expiration, validity period
* Secure delegations / resolving

One check for one component
---------------------------

The tools supplied by this repository should be reuseable for different tasks.
Probing a zone while implementing DNSSEC or continuous monitoring of your signed zones are examples for use cases.
Checks executed by that tools need to be smart, fast and without implifications for your infrastructure or systems.

Prototyping
-----------

First I want to implement prototyps within bash to set up basic functionality.
In the following these scripts should be transformed into faster languages.

Integration with other systems
------------------------------

Other monitoring systems or components collecting information should be able to take standarized output of the programs and generate useful relations.
This project does not want to provide an all-in-one solution for monitoring DNSSEC setups.
