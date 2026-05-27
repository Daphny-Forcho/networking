# Lab 3 – Default Gateway Configuration

## Objective
Configure the default gateway on all end devices in a multi-network topology so that devices can communicate beyond their local subnet. Without a default gateway, a device can only reach other hosts on the same network — it has no way to forward traffic to a router and on to other networks.

## What I Did

Opened the topology in Cisco Packet Tracer and identified all end devices (PCs and servers) across the network. For each device, navigated to the IP configuration settings and entered the appropriate default gateway address — the IP address of the router interface on that device's local subnet.

This tells each device where to send traffic that is destined for an IP address outside its own network. The router then takes responsibility for forwarding that traffic to the correct destination.

## Key Concept

A default gateway is required any time a device needs to communicate outside its local subnet. In practice this is the IP address of the nearest router interface. If this is not set, pings and connections to remote hosts will fail even if the device has a valid IP address and subnet mask.

## Project File

[`assigning_default_gateways.pka`](./assigning_default_gateways.pka) — open with Cisco Packet Tracer to view the completed topology.
