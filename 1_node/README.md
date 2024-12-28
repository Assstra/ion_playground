# 1-node loopback configuration

This configuration sets up a single node that communicates with itself.

## Overview
- **Protocol**: TCP (used specifically for the loopback configuration, as LTP is not recommended in this case)
- **Number of Nodes**: 1
- **Number of Hosts**: 1
- **Purpose**: Designed for testing and validating single-node communication in isolation.
- **Use case**: Debugging and development.

## Quick start

You can use `ionscript` command to merge all configuration file.

```bash
ionscript -i loopback-1-node.ionrc -p loopback-1-node.ipnrc -b loopback-1-node.bprc -b loopbackstart-1-node.bprc -O host-loopback.rc
```

Then just ionstart -I host-loopback.rc to start the node.

## Sending bundles

To send bundles :
1. Run bpcounter ipn:1.2 3 to be ready to receive 3 bundles on ipn:1.2 endpoint.
2. Run bpdriver 3 ipn:1.1 ipn:1.2 10000 to send bundles from ipn:1.1 to ipn:1.2.

