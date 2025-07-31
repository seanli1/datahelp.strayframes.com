---
{"dg-publish":true,"permalink":"/comparing-raid-configurations/"}
---

# Comparing RAID configurations

| **RAID Level**    | **Min. Drives** | **Fault Tolerance**                                                  | **Storage Efficiency**    | **Performance**                                           | **Typical Use Case**                                 |
| ----------------- | --------------- | -------------------------------------------------------------------- | ------------------------- | --------------------------------------------------------- | ---------------------------------------------------- |
| **RAID 0**        | 2               | **None!**                                                            | 100% (all space usable)   | Highest read & write (striping only)                      | Temporary high-speed storage, scratch disks          |
| **RAID 1**        | 2               | 1 drive can fail                                                     | 50% (data fully mirrored) | Fast reads, slower writes (writes duplicated)             | Small critical data sets needing redundancy          |
| **RAID 10 (1+0)** | 4               | 1 drive per mirrored pair (can survive multiple non-paired failures) | 50%                       | Very high read & write                                    | Databases, VMs, performance + redundancy             |
| **RAID 5**        | 3               | 1 drive can fail                                                     | (n-1)/n (\~67%-94%)       | Good reads, slower writes (parity calc)                   | General storage where capacity and redundancy matter |
| **RAID 6**        | 4               | 2 drives can fail                                                    | (n-2)/n (\~50%-88%)       | Good reads, slower writes than RAID 5 (extra parity calc) | Larger arrays needing higher fault tolerance         |

> [!summary]
> 
> **RAID 0, 5, and 6:** Fault tolerance is fixed by design (0, 1, or 2 drives) and doesn’t improve by adding more disks.
> 
> **RAID 1:** Adding drives increases fault tolerance significantly (all but one can fail).
> 
> **RAID 10:** Adding drives increases potential fault tolerance, but only if failures don’t hit all drives in the same mirrored set.
