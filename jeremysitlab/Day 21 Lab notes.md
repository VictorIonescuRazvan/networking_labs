# 1. Current topo

## Root bridge
It is SW2:
- checked SW1, VLAN 1&2 point to SW2
- checked SW2, VLAN 1&2 point to self

## SW1
- Fa0/1 - ND
- Fa0/2 - D
- Fa0/3 - R

## SW2
- Fa0/1-3 - D

## SW3
### VLAN 1
- Fa0/1 - D
- Fa0/2 - R
- Fa0/3 - D // host connection

### VLAN 2
- Fa0/1 - D
- Fa0/2 - R

## SW4
### VLAN 1
- Fa0/1 - R
- Fa0/2 - ND

### VLAN 2
- Fa0/1 - R
- Fa0/2 - ND
- Fa0/3 - D // host connection

# 2. Changed topo
## VLAN 1
### SW1
- root
- Fa0/1-3 - D

### SW2
- Fa0/1 - D
- Fa0/2 - D
- Fa0/3 - R

### SW3
- Fa0/1 - R
- Fa0/2 - ND
- Fa0/3 - D

### SW4
- Fa0/1 - ND
- Fa0/2 - R

## VLAN 2
### SW1
- Fa0/1 - D
- Fa0/2 - D
- Fa0/3 - R

### SW2
- root
- Fa0/1-3 - D

### SW3
- Fa0/1 - B
- Fa0/2 - R

### SW4
- Fa0/1 - R
- Fa0/2 - ND
- Fa0/3 - D

# 3. Changed topo
- root port is changed - now F0/1
- cost on f0/1 is lower - cost to SW2 + cost SW2 - SW1 is 19 + 19 = 38 < 100 (F0/2 to SW1 directly)

# 4. Changed topo
- root port stays on F0/1
- neighbor port priority is only used when two ports have the same cost to root and the same neighbor bridge id. The cost is lower on F0/1 than F0/2, so F0/1 is elected as root port and neighbor id is not evaluated.

