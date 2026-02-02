# Packet captures for Ansible ACI

Here are the packet captures that were used to show how Ansible authenticates. 

- ansible_three_tier.pcap: Packet capture showing how Ansible authenticates **Every** task!
- ansible_three_tier_http_api.pcap: Packet capture that shows how Ansible authenticates once via the HTTP API plugin.

In order to capture this, I needed to do a couple of different things:

1: Turn on HTTP on the ACI APIC
2: Use `use_ssl: false` in order to turn off using Secure Sockets for the REST API calls.

Username/Password are local to the APIC.