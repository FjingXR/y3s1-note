# Tutorial 2 — Q4

## OSPF Challenges on Multiaccess Networks

### The Two Challenges

1. **Creation of multiple adjacencies** — On an Ethernet (multiaccess) network with *n* routers, every router would form an adjacency with every other router. That is *n(n-1)/2* adjacencies, which becomes unmanageable on large networks.

2. **Extensive flooding of LSAs** — Every router floods its LSAs to all other routers. This creates massive redundant traffic that wastes bandwidth and CPU on every router.

---

### The Solution

1. **Elect a Designated Router (DR)** — The DR acts as the central collection and distribution point for all LSAs on the multiaccess segment. All other routers (DROTHERs) form a full adjacency **only with the DR** (and the BDR), not with each other. LSAs are sent to the DR, which then forwards them to all other routers.

2. **Elect a Backup Designated Router (BDR)** — The BDR forms adjacencies with all routers the same way the DR does, but stays idle. If the DR fails, the BDR takes over immediately without needing a new election.

> **Result:** Adjacencies drop from *n(n-1)/2* down to *2n-1*, and LSA flooding is centralized through the DR/BDR.
