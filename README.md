**Focus:** Mobile performance, SMB reliability, low-end device constraints
# Toing — Mobile Performance Audit (SMB Context)

## Problem
Field users (Kirana, Pharmacy, sales agents) rely on mobile apps for tracking and transactions. On low-end Android devices, performance issues can break workflows and cause data loss.

## Why it matters
India’s SMB users often operate on sub-₹15k devices (4GB RAM or less). If apps are not optimized for these constraints, reliability drops → business impact.

## What I analyzed
- Cross-device behavior (legacy vs modern Android)
- Battery usage during GPS tracking
- RAM consumption patterns
- User complaints from Play Store (200+ reviews)

## Key Findings
- ~5.5% battery drain within ~3 minutes of active GPS usage  
- ~600MB RAM spikes on 4GB devices → triggers Android OOM Killer  
- Frequent app interruptions → breaks transaction continuity  
- Issues confirmed through both telemetry + user reviews (not isolated)

## Insight
Performance problems are not edge cases — they are **systemic for low-end devices**, which represent a large portion of Indian SMB users.

## Proposed Improvements
- Adaptive asset loading based on device capability  
- Asynchronous data buffering (e.g., SQLite) to prevent data loss  
- Performance-aware feature scaling for low-end devices  

## Full Report
[Download PDF](./toing-mobile-performance-audit.pdf)

## Takeaway
Product reliability for SMB users is a **hardware + software problem**, not just UX. Optimizing for real-world constraints can directly improve retention and trust.
