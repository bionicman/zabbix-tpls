Zabbix templates
================

This is my collection of Zabbix templates.

It's free for reuse, you can use it in your infrastructure for commercial or uncommercial usage.

Cisco Router
------------

SNMP based template. SNMPv2 community name from `{$SNMP_COMMUNITY}` macro.

Need for next MIB's (and their depends):
* BGP4-MIB
* CISCO-BGP4-MIB
* ENTITY-MIB
You can found MIB files in `mibs` directory in this repo.

### BGP peers discovery

Discovered all BGP peers from router in IPv4/IPv6/VPNv4 (VRF) address-families.

Separate graphs for each peer:
* BGP informations for peer %peer_addr% in IPv4 multicast address-family
* BGP informations for peer %peer_addr% in IPv4 unicast address-family
* BGP informations for peer %peer_addr% in IPv6 multicast address-family
* BGP informations for peer %peer_addr% in IPv6 unicast address-family
* BGP informations for peer %peer_addr% in VPNv4 address-family
* BGP informations for peer %peer_addr% in VPNv6 address-family

All graphs contains information:
* prefixes accepted (bold green)
* prefixes advertised (bold blue)
* prefixes denied (red)
* prefixes suppressed (purple)
* prefixes withdrawn (yellow)

Separate triggers for each peer:
* BGP peer %peer_addr% from ASN %as_num% administratively down (information severity)
* BGP peer %peer_addr% from ASN %as_num% has lost more than 20% of (IPv4|IPv6|VPNv4) (unicast|multicast) prefixes on %router% (average severity, separate for each AF)
* BGP peer %peer_addr% from ASN %as_num% has not received (IPv4|IPv6|VPNv4) (unicast|multicast) prefixes on %router% (info severity, separate for each AF)
* BGP peer %peer_addr% from ASN %as_num% down and has state %state% (high severity, if state not established and peer not admin down)

### Inventory discovery

Discovered all HW-modules on router and provide information about:
* entry class
* entry manufacturer
* entry model
* entry name
* entry description
* entry serial number
* entry FW revision
* entry HW revision
* entry SW revision
