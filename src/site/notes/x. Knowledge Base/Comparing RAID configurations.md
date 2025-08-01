---
{"dg-publish":true,"permalink":"/x-knowledge-base/comparing-raid-configurations/"}
---

# Comparing RAID configurations

| **RAID Level**    | **Min. Drives** | **Fault Tolerance**                                                  | **Storage Efficiency**    | **Performance**                                           | **Typical Use Case**                                 |
| ----------------- | --------------- | -------------------------------------------------------------------- | ------------------------- | --------------------------------------------------------- | ---------------------------------------------------- |
| **RAID 0**        | 2               | **None!**                                                            | 100% (all space usable)   | Highest read & write (striping only)                      | Temporary high-speed storage, scratch disks          |
| **RAID 1**        | 2               | 1 drive can fail                                                     | 50% (data fully mirrored) | Fast reads, slower writes (writes duplicated)             | Small critical data sets needing redundancy          |
| **RAID 10 (1+0)** | 4               | 1 drive per mirrored pair (can survive multiple non-paired failures) | 50%                       | Very high read & write                                    | Databases, VMs, performance + redundancy             |
| **RAID 5**        | 3               | 1 drive can fail                                                     | (n-1)/n (\~67%-94%)       | Good reads, slower writes (parity calc)                   | General storage where capacity and redundancy matter |
| **RAID 6**        | 4               | 2 drives can fail                                                    | (n-2)/n (\~50%-88%)       | Good reads, slower writes than RAID 5 (extra parity calc) | Larger arrays needing higher fault tolerance         |

> [!tip] Extra tips
> 
> **RAID 0:** Zero fault tolerance. If one drive dies, ALL data is unreadable (because the data is striped).
> 
> **RAID 5 and 6:** Fault tolerance is fixed (1 or 2 drives) and doesn’t improve by adding more disks.
> 
> **RAID 1:** Adding drives increases fault tolerance significantly, since they're all mirrors (all drives but one can fail).
> 
> **RAID 10:** Adding drives increases fault tolerance, but the exact number of drives that can go down depends on which drives malfunction. Complete data loss can still occur if failure hits all drives in the same mirrored set.

> [!note] RAID calculators:
> - https://www.synology.com/en-us/support/RAID_calculator
> - https://www.seagate.com/products/nas-drives/raid-calculator/
> - https://www.qnap.com/en-us/selector/raid-selector
