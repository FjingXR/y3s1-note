# Q4. Multiaccess Networks — OSPF Challenges & Solutions

> Reference: ENSA Module 1 — Single-Area OSPFv2 Concepts

---

## The Two Challenges

On a multiaccess network (e.g. Ethernet), many OSPF routers can connect to the same link. This creates **two problems** for LSA flooding:

| # | Challenge | Explanation |
|--|-----------|-------------|
| **1** | **Excessive adjacencies** | Every router would need to form a full adjacency with *every other* router on the link. With `n` routers, that is `n(n-1)/2` adjacencies — an exponential explosion of neighbour relationships. |
| **2** | **Extensive LSA flooding** | Every router floods its LSAs whenever OSPF initialises or the topology changes. If every router flooded to every other router, the amount of LSA traffic would overwhelm the network. |

> These are directly from the Cisco ENSA curriculum (Module 1, "The Need for a DR").

---

## The Solution: DR / BDR Election

OSPF solves both challenges by electing a **Designated Router (DR)** and a **Backup Designated Router (BDR)** on each multiaccess network.

| Role | Description |
|------|-------------|
| **DR** | The collection and distribution point for all LSAs on the multiaccess link. All other routers (DROTHERs) send their LSAs **only** to the DR. The DR then forwards the LSAs to all other routers. |
| **BDR** | Listens passively and maintains adjacencies with all routers. Takes over as DR if the DR fails. |
| **DROTHER** | Any router that is neither the DR nor the BDR. Forms a full adjacency **only** with DR and BDR (not with other DROTHERs). |

### How it fixes the two challenges

| Challenge | How DR/BDR solves it |
|-----------|----------------------|
| Excessive adjacencies | Each DROTHER only needs **2 adjacencies** (DR + BDR) instead of one with every other router. Total adjacencies = `2(n-2) + 1` instead of `n(n-1)/2`. |
| Extensive LSA flooding | The DR is the single point for LSA collection and distribution. DROTHERs send LSAs to the DR only (multicast `224.0.0.6`), and the DR forwards them to all others (multicast `224.0.0.5`). — LSA flooding is now controlled and orderly. |

### Election process

1. The router with the **highest OSPF priority** (default = 1) becomes the DR.
2. The router with the **second highest priority** becomes the BDR.
3. If priorities are tied, the **highest router ID** wins.
4. A router with priority **0** never participates in the election.

> Note: DR and BDR are elected **per multiaccess segment**, not per area. Point-to-point links do **not** need DR/BDR.

### Key multicast addresses

| Address | Used by | Purpose |
|---------|---------|---------|
| `224.0.0.5` | All OSPF routers | General OSPF traffic |
| `224.0.0.6` | DROTHERs | Send LSAs to DR/BDR only |

---

## Summary

| Problem | Cause | Solution |
|---------|-------|----------|
| Too many adjacencies | Every router pairing on a shared link | DR/BDR election — DROTHERs only talk to DR & BDR |
| Too much LSA flooding | Every router floods to all others | DR collects & redistributes all LSAs centrally |
