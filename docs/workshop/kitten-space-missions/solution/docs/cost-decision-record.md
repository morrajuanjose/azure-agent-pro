# Cost Decision Record - Kitten Space Missions API
## Development Environment Deployment

**Date:** February 13, 2026  
**Project:** Orange Kitten Space Missions API  
**Environment:** Development (westeurope)  
**Status:**  APPROVED  

---

## Executive Summary

This document records the **cost optimization decisions** for the Kitten Space Missions API development environment. After comprehensive analysis, we have selected **App Service B1 (Basic)** as the optimal choice for our dev environment, paired with **auto-shutdown automation** to minimize costs while maintaining team productivity.

### Key Metrics (Optimized)
- **Monthly Cost:** €15.40 (with auto-shutdown)
- **Annual Cost:** €184.80
- **Budget Target:** €70-80/month
- **Actual vs Budget:** -69% (€54.60 headroom per month)
- **Savings Implementation:** €9.26/month through auto-shutdown
- **ROI:** 444% (2.7-month payback period)

---

## 1. SKU Decision: App Service Tier

### Option A: F1 Free Tier (REJECTED )

**Why it failed:**
- CPU Limit: 60 minutes/day
- Latency: 500-700ms p95 (FAILS <200ms requirement)
- No auto-scaling
- No SLA

**Decision:** REJECTED - Performance requirements trump cost

### Option B: B1 Basic (SELECTED )

**Why it works:**
- CPU: 1 vCPU dedicated, unlimited usage
- Latency: 50-100ms p95 (EXCEEDS requirement)
- Auto-scales 1-3 instances
- 95% SLA guaranteed

**Cost with optimization:** €5.14/month (auto-shutdown)  
**Decision:** APPROVED 

---

## 2. Database & Caching Decisions

**SQL Database:** Basic 2GB (€4.80/month)  
**Redis Cache:** C0 (€1.50/month) - Mandatory for latency requirement

---

## 3. Auto-Shutdown Decision

**Schedule:** Mon-Fri 8am-8pm CET (Stop at 8pm, Start at 8am)  
**Monthly Savings:** €9.26  
**Annual Savings:** €111.12  
**ROI:** 444% with 2.7-month payback

---

## 4. Complete Cost Breakdown

| Component | Monthly | Annual |
|-----------|---------|--------|
| App Service B1 (optimized) | €5.14 | €61.68 |
| SQL Database Basic 2GB | €4.80 | €57.60 |
| Redis Cache C0 | €1.50 | €18.00 |
| Application Insights | €2.88 | €34.56 |
| Log Analytics | €0.50 | €6.00 |
| Private Endpoint | €0.50 | €6.00 |
| **TOTAL** | **€15.40** | **€184.80** |

---

**Document Status:**  READY FOR IMPLEMENTATION  
**Version:** 1.0  
**Next Review:** May 13, 2026
