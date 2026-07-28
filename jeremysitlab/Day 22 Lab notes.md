# 1
- root bridge is at SW1
Not all interfaces are D - Fa0/3 is Backup. This is because it has the higher port id than Fa0/2 - 128.3 vs 128.2. This is required because Fa0/2 and Fa0/3 share the same collision domain, and only one D port exists per collision domain.

# 2
## SW2
- F0/1 R
- F0/2 D
- G0/1 A
- F0/23 D
- F0/24 D

## SW3
- F0/2 R
- F0/1 D
- G0/1 D
- F0/24 D

## SW4
- F0/1 R
- F0/2 A
- F0/24 D

# 3
The correct type for F0/24 is edge - it is connected only to client devices in its collision domain, not to any other switches. At the same time, it is connected to a hub, so it is also a shared port.