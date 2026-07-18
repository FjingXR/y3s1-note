# Chapter 1 — Practice Quiz (No Answers)
## IP Static Routing & Troubleshooting · SRWE Modules 15-16

---

### Section A: Static Route Types & Concepts

1. What are the 4 types of static routes by purpose?

2. What are the 3 ways to specify the next hop when configuring a static route?

3. On what type of link should a "directly connected" static route (exit-interface only) be used?

4. A "fully specified" static route must be used in two scenarios. Name them.

5. What command must be enabled on a router before IPv6 static routes will work?

---

### Section B: Command Syntax

6. Write the full syntax for an **IPv4** static route command.

7. Write the full syntax for an **IPv6** static route command.

8. Write the command for an IPv4 default static route via next-hop 10.0.0.1.

9. Write the command for an IPv6 default static route via next-hop 2001:db8::1.

10. Write the command for a static host route (IPv4) to 209.165.200.238 via 198.51.100.2.

11. Write the command for a floating default static route (IPv4) via backup router 10.10.10.2 with AD 5.

---

### Section C: Administrative Distance

12. What does Administrative Distance (AD) represent?

13. What is the default AD of each of the following?
    - Directly connected route: ____
    - Static route: ____
    - OSPF: ____
    - RIP: ____

14. To make a floating static route, do you use a higher or lower AD than the primary route?

15. While the primary route is working, does the floating (backup) route appear in the routing table? Why or why not?

---

### Section D: Default Routes

16. What is an IPv4 default static route informally called?

17. What network address and subnet mask are used for an IPv4 default route?

18. What prefix/length is used for an IPv6 default route?

19. In `show ip route`, how can you identify which static route is the candidate default route?

20. Give two typical scenarios where a default static route would be used.

---

### Section E: Summary & Host Routes

21. What two conditions must be met to summarize multiple static routes into one?

22. Summarize these networks into one route: 192.168.1.0/24, 192.168.2.0/24, 192.168.3.0/24

23. What subnet mask identifies an IPv4 host route?

24. What prefix length identifies an IPv6 host route?

25. Name the three ways a host route can appear in a routing table.

---

### Section F: Packet Forwarding

26. When a packet arrives at a router, what are the three possible outcomes of the routing table lookup?

27. Does the source/destination IP address change as a packet travels from router to router?

28. What changes at each hop as a packet travels through multiple routers?

29. When the final router finds the destination is on a directly connected Ethernet interface, what protocol does it use to find the destination MAC address?

30. What does the router do if no ARP entry exists for the destination host?

---

### Section G: Troubleshooting

31. List 5 common IOS troubleshooting commands and what each one checks.

32. A user at PC1 cannot reach PC3. Pings from R1 to R2 succeed, and from R1 to R3 succeed. Where is the problem most likely located?

33. What is the recommended troubleshooting strategy when a packet cannot reach its destination across multiple routers?

34. Give four common reasons why a network might fail (related to routing).

35. What does `show cdp neighbors` tell you?

---

### Section H: Scenario / Application

36. Router R1 has three static routes all pointing to the same next-hop 172.16.2.2:
    - `ip route 192.168.1.0 255.255.255.0 172.16.2.2`
    - `ip route 192.168.2.0 255.255.255.0 172.16.2.2`
    - `ip route 192.168.3.0 255.255.255.0 172.16.2.2`
    Can these be summarized? If so, what is the summary route?

37. A router has `ip route 0.0.0.0 0.0.0.0 203.0.113.1` and `ip route 0.0.0.0 0.0.0.0 198.51.100.1 10`.
    - Which route is the primary? Which is the backup?
    - When will the backup be used?

38. For an IPv6 static route using a link-local address (fe80::1) as the next-hop, why must the exit interface also be specified?

39. Write the IPv6 fully specified static route to reach 2001:db8:acad:1::/64 via exit interface Serial0/1/0 with next-hop link-local address fe80::1.

40. A technician runs `show ip route` on R2 and sees: `S 10.1.1.0/24 [1/0] via 192.168.99.1`. If 192.168.99.1 is not a directly connected network, what is wrong?

---

### Quick Fire (True / False)

41. A static route is learned automatically by the router. T / F

42. IPv6 static routes use the same command syntax as IPv4 with `ipv6` instead of `ip`. T / F

43. The default AD for a static route is 0. T / F

44. A directly connected static route is recommended for Ethernet interfaces. T / F

45. A default route matches only packets with destination 0.0.0.0. T / F

46. A floating static route is used as the primary path. T / F

47. The `show ip route static` command displays only the static routes. T / F

48. Route summarization reduces the size of the routing table. T / F

49. A host route uses a /24 mask for IPv4. T / F

50. When a router has no matching route and no default route, it forwards the packet to all interfaces. T / F

---

Good luck with your midterm! 🎯
