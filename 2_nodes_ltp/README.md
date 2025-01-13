# 2-node LTP configuration

This configuration sets up 2 nodes that communicates using the Licklider Transmission Protocol (LTP), the convergence layer protocol used by the Bundle Protocol.

## Overview

- **Protocol**: LTP (Licklider Transmission Protocol) & UDP as transport protocol.
- **Number of Nodes**: 2
- **Number of Hosts**: 1 (using virtual machines)
- **Purpose**: Designed for testing and validating communication between two nodes.
- **Use case**: Real-world communication scenarios.

## Quick start

Just `ionstart -I host1-2-nodes.rc` on node 1 and `ionstart -I host2-2-nodes.rc`on node 2.

## Sending bundles

To send bundles from node 1 to node 2, you can use the `bpdriver` and `bpcounter` utilities.:

1. Run bpcounter ipn:1.2 3 to be ready to receive 3 bundles on ipn:1.2 endpoint.
2. Run bpdriver 3 ipn:2.2 ipn:1.2 10000 to send bundles from ipn:2.2 to ipn:1.2.

## Explanation

- Why using UDP as transport protocol?

> LTP relies on UDP as its transport protocol since most systems > do not natively support LTP. While TCP could also be used, LTP > handles reliability and flow control independently. Therefore, > UDP is preferred to minimize the overhead associated with TCP.
