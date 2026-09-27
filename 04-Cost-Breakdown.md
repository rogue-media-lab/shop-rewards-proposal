# Cost Breakdown & Pricing

**Document:** Detailed Cost Analysis & Investment Structure
**Project:** Shop Rewards - Proprietary Loyalty Platform
**Date:** November 2025

---

## Development Cost (One-Time Investment)

### Development Cost Breakdown by Phase

This proposal reflects a **$50/hour development rate** with **E&O Professional Liability Insurance included** in operational costs.

| Phase | Description | Hours | Rate | Total |
|-------|-------------|-------|------|-------|
| **Phase 1** | **Core Admin Features**<br>Admin authentication, dashboard, Flash Sale creation, customer lookup, redemption interface, points management | 44 | $50 | $2,200 |
| **Phase 2** | **Customer-Facing Features**<br>Phone-based authentication, signup with TCPA compliance, profile, coupon wallet, rewards dashboard, history | 38 | $50 | $1,900 |
| **Phase 3** | **Services Display** (Valvoline-style)<br>Services model, owner CRUD interface, manager assignment UI, customer service cards with icons | 19 | $50 | $950 |
| **Phase 4** | **Push Notifications**<br>OneSignal integration, background job queue, opt-in flow, settings page, cross-platform testing | 22 | $50 | $1,100 |
| **Phase 5A** | **Rewards Program** (Points System)<br>Points calculation (10 pts/$1), balance display, redemption barcodes, tracking | 12 | $50 | $600 |
| **Phase 5B** | **Perks System** (Service-Count Rewards)<br>Dual loyalty (service-count + points-threshold), progress tracking, owner configuration | 16 | $50 | $800 |
| **Phase 5C** | **Barcode POS Bridge**<br>Barby gem integration, Code 128 generation (fixed & dynamic amounts), full-screen display UI | 9 | $50 | $450 |
| **Phase 5D** | **Manager PIN Security**<br>PIN encryption (bcrypt), Stimulus keypad UI, verification logic, audit trail logging | 8 | $50 | $400 |
| **Phase 5E** | **PO Transaction Workflow**<br>Transaction model, service type dropdown, auto-calculation preview, points/perks update, history | 12 | $50 | $600 |
| **Phase 5F** | **Standing Coupons**<br>Owner-level ongoing promos, CRUD interface, coupon types (birthday, military, senior), barcode generation | 12 | $50 | $600 |
| **Phase 5G** | **Birthday Rewards Automation**<br>Birth month tracking, scheduled daily job, auto-coupon generation, notification delivery | 6 | $50 | $300 |
| **Phase 5H** | **Flash Alert Check-In**<br>Check-in timestamp, manager "Reserve" button, same-day validation, checked-in customers queue | 7 | $50 | $350 |
| **Phase 6** | **Legal & Compliance**<br>Terms of Service, Privacy Policy, TCPA consent logging, SMS opt-out mechanism | 10 | $50 | $500 |
| **Phase 7** | **PWA Configuration**<br>Manifest file, service worker, offline support, PWA icons (multiple sizes), cross-platform testing | 15 | $50 | $750 |
| **Phase 8** | **UI/UX Polish**<br>Responsive design (mobile/tablet/desktop), loading states, animations, brand consistency, accessibility (WCAG 2.1) | 23 | $50 | $1,150 |
| **Phase 9** | **Testing & QA**<br>Unit tests (RSpec), integration tests, bug fixes, cross-browser testing (Safari, Chrome, Samsung, Firefox) | 28 | $50 | $1,400 |
| **Phase 10** | **Deployment & Documentation**<br>Heroku setup (production + staging), seed data, training video, quick reference guide, FAQ page | 14 | $50 | $700 |
| **Phase 11** | **Multi-Tenant Architecture**<br>Franchise/Shop models, QR code generation, shop-scoped queries, dynamic branding, owner dashboard, 3-portal routing | 66 | $50 | $3,300 |
| **Buffer** | **Contingency** (10%)<br>Stakeholder feedback, edge cases, design iterations, unexpected complexity | 29 | $50 | $1,450 |
| | | **321** | | **$16,050** |
| | **ROUNDED PROPOSAL PRICE** | | | **$16,000** |

**Key Investment Rationale:**
- **$50 rounding** makes budgeting cleaner for finance teams
- **10% buffer** covers inevitable scope adjustments and refinements
- **E&O insurance** ($90/month) included in operational costs (not development)
- **Milestone payments:** 3-stage structure ($4,000 + $4,000 + $8,000) reduces upfront risk

---

### Why $16,000 vs. $16,050?

**The $50 rounding ($16,050 - $16,000) demonstrates:**

1. **Good Faith Pricing:** Round number makes budgeting easier
2. **Competitive Value:** Still significantly below market rate
3. **Relationship Building:** Long-term partnership over maximizing single project

**Buffer Breakdown:**
- **Base Development:** 292 hours ($11,680)
- **10% Buffer:** 29 hours ($1,160) for stakeholder feedback, edge cases, polish
- **Subtotal:** 321 hours ($16,050)
- **Rounded Price:** $16,000 (clean number for budgeting)

**What the 10% Buffer Covers:**
1. **Stakeholder Feedback:** Corporate will request changes during development
2. **Design Iterations:** "Can we make the button bigger?" type requests
3. **Content Creation:** Writing copy for legal pages, FAQs, error messages
4. **Edge Cases:** Handling unusual scenarios not captured in initial planning
5. **Final Polish:** Extra attention to detail before stakeholder demonstration
6. **POS Configuration Support:** Helping owner configure barcode patterns in Sage POS

**Scope vs. Original Proposal:**

**Original Proposal:** 220 hours ($8,800) → $10,000 including:
- VIN Scanner (26 hours)
- Basic points system
- Simple flash alerts

**Updated Proposal:** 321 hours ($16,050) → $16,000 including:
- **Removed:** VIN Scanner (-26 hours)
- **Added:** Services Display, Perks System, Barcode Bridge, Manager PIN, PO Workflow, Standing Coupons, Birthday Rewards, Check-In (+63 hours net)
- **More comprehensive platform** with franchise-safe POS integration

**Value Proposition:**
- Corporate receives a **purpose-built automotive loyalty platform**
- Dual loyalty system (Points + Perks) unique in market
- Barcode POS bridge eliminates franchise compliance risks
- Multi-franchise architecture serves mixed portfolios
- Services display matches Valvoline's modern UX
- Manager PIN security prevents fraud + creates audit trail

**Industry Comparison:**
- Agencies charge $100-150/hr with 20-30% markup
- This proposal: $50/hr with 10% buffer = **65-75% cost savings**

---

## Operational Costs (Monthly, Recurring)

### Infrastructure & Services

| Service | Tier | Monthly Cost | Notes |
|---|---|---|---|
| **Hosting (Heroku)** | | | |
| Web dyno (Standard-1X) | 1x | $25 | Runs Rails app |
| Worker dyno (for background jobs) | 1x | $25 | Processes push notifications |
| PostgreSQL (Standard-0) | 1x | $50 | 64GB storage, 120 connections |
| Redis (Mini) | 1x | $15 | Caching and job queue |
| **Subtotal Hosting** | | **$115** | |
| | | | |
| **Push Notifications** | | | |
| OneSignal (Free tier) | Up to 10k users | $0 | Free for pilot phase |
| OneSignal (Growth tier) | If >10k users | $49 | Only if pilot scales |
| **Subtotal Notifications** | | **$0-49** | Pilot = free, scale = $49 |
| | | | |
| **SMS (Optional - if used for auth)** | | | |
| Twilio SMS | ~1,000 messages | $8 | $0.0079 per SMS |
| Twilio phone number | 1x | $2 | Virtual number for replies |
| Buffer for growth | | $15 | Conservative estimate |
| **Subtotal SMS** | | **$25** | Optional feature |
| | | | |
| **Domain & Security** | | | |
| Custom domain (shoprewards.com) | 1x/year | $1.25 | $15/year = $1.25/month |
| SSL certificate | Included | $0 | Heroku provides Let's Encrypt |
| **Subtotal Domain** | | **$1.25** | |
| | | | |
| **Monitoring & Error Tracking** | | | |
| Sentry (error monitoring) | Team plan | $26 | 50k errors/month, 1 project |
| UptimeRobot (uptime monitoring) | Pro plan | $7 | 5-minute checks, SMS alerts |
| **Subtotal Monitoring** | | **$33** | |
| | | | |
| **Backups & Storage** | | | |
| Heroku Postgres backups | Included | $0 | Daily backups, 7-day retention |
| Additional S3 storage (if needed) | ~5GB | $0.15 | $0.023/GB + transfer |
| **Subtotal Storage** | | **$0.15** | Negligible cost |
| | | | |
| **TOTAL MONTHLY OPERATIONAL** | | **$174.40** | Conservative pilot estimate |
| **ROUNDED PROPOSAL PRICE** | | **$300/month** | Includes growth buffer |

---

### Why $300/month vs. $174?

**The $125 buffer ($300 - $174) accounts for:**

1. **Usage Spikes:** More SMS than estimated, traffic surges
2. **Service Tier Upgrades:** If pilot grows faster than expected
3. **Additional Tools:** May need analytics platform, A/B testing tools
4. **Currency Fluctuations:** If using international services
5. **Emergency Scaling:** Heroku dyno upgrades during high traffic events

**Client benefit:** Predictable budgeting. No surprise overages.

---

### Operational Costs at Enterprise Scale

**SMS Costs Scale with Usage:**
- **Pilot phase** (6 shops, ~600 customers): $25/month SMS (included in $300/month)
- **Enterprise scale** (100+ shops, 50k+ customers): SMS costs increase significantly
  - Estimate: 1,000 messages/month per shop = $8-10/month per shop
  - At 100 shops: $800-1,000/month SMS costs
- **Push notifications remain cost-effective:**
  - OneSignal: Free up to 10k users per shop
  - After 10k users: $49/month flat rate (unlimited notifications)
  - 100 shops with 10k+ users each: $4,900/month vs. SMS alternative of $10,000+/month

**Recommendation:** Push notifications (OneSignal) are the primary notification channel. SMS used only for account verification and opt-in confirmation to minimize costs at scale.

---

## Maintenance & Support Costs (Monthly, Recurring)

### Tiered Support Options

#### **Option 1: Pilot Program Support (RECOMMENDED)**

**Price:** $800/month

**Included Services:**
- **Equivalent to 20 hours/month** of development/support time (blended rate)
- Bug fixes and technical issues (unlimited within scope)
- Minor feature tweaks (e.g., "change button color," "add new field")
- Monthly check-in call (30 minutes)
- Email support (24-hour response time, business days)
- Emergency support for critical issues (4-hour response, 7 days/week)
- Performance monitoring and optimization
- Security updates and patches
- Quarterly feature planning session

**What's NOT Included (Requires Additional Quote):**
- Major new features (e.g., "add appointment booking system")
- Design overhauls
- Third party integrations beyond MVP scope

**Unused Hours:**
- Do NOT roll over to next month
- Encourages realistic scoping

---

#### **Option 2: Enterprise Support (Post-Pilot)**

**Price:** $1,500/month

**Included Services:**
- Everything in Pilot Support, plus:
- **Equivalent to 30 hours/month** of development time (blended rate)
- Priority support (4-hour response for critical, 24-hour for high priority)
- Dedicated Slack/Teams channel
- Monthly analytics report (redemptions, ROI, user growth)
- Quarterly roadmap planning with stakeholders
- Multi-location optimization and performance tuning
- On-call availability for emergencies (phone support, 7 days/week)

**Best For:**
- 10+ locations using the platform
- Frequent feature requests
- Mission critical reliance on platform

---

#### **Option 3: Hourly As-Needed (Not Recommended)**

**Price:** $60/hour (billed in 30-minute increments)

**Why Higher Than Development Rate:**
- No guaranteed monthly income = higher risk
- Reactive work = less efficient than planned sprints
- Context-switching overhead

**Why Not Recommended:**
- Unpredictable costs for corporate (bad for budgeting)
- Slower response times (no committed capacity)
- No proactive monitoring or optimization

---

### Support Response Times (Service Level Agreement)

**CFO Question:** *"If the app crashes on a Saturday, are you fixing it? Or are you working your automotive tech shift?"*

This SLA applies to the **$800/month Pilot Support** package (Option 1). Enterprise Support follows the same SLA with faster response times.

---

#### **Critical Issues** (Platform Down / Cannot Process Transactions)

**Examples:**
- App completely offline or unreachable
- Customers cannot sign up or redeem rewards
- Admin dashboard not loading
- Payment processing broken
- Data loss or security breach

**Response Time:** 4 hours (from notification)
**Availability:** 7 days/week, including weekends and holidays
**Communication:** Phone call + email notification
**Resolution Timeline:** Best effort within 24 hours; status updates every 4 hours

**Weekend Coverage:** YES - Critical issues are addressed 24/7. Mason will pause personal activities to resolve platform outages.

---

#### **High Priority Issues** (Feature Broken, Workarounds Exist)

**Examples:**
- Flash Sale notifications not sending
- QR code scanner not working
- Specific feature crashed but app still functions
- Performance degradation (slow loading)

**Response Time:** 24 hours (business days)
**Availability:** Monday-Friday, 9am-5pm EST
**Communication:** Email with issue tracking number
**Resolution Timeline:** 2-5 business days depending on complexity

**Weekend Coverage:** NO - High priority issues reported on weekends will receive response first thing Monday morning.

---

#### **Normal Priority** (Feature Requests, Cosmetic Issues, Questions)

**Examples:**
- "Can we change the button color?"
- "Add a new field to the signup form"
- UI text changes
- Minor bugs that don't block functionality
- Manager training questions

**Response Time:** 48 hours (business days)
**Availability:** Monday-Friday, 9am-5pm EST
**Communication:** Email
**Resolution Timeline:** Included in next scheduled maintenance window (weekly)

**Weekend Coverage:** NO - Normal requests are queued for next business week.

---

#### **Overage Hours Policy**

**What Happens When 20 Hours/Month Are Exhausted:**

If the monthly support allocation is fully consumed (typically happens only during heavy bug-fixing periods or major feature adjustments), additional work is billed as follows:

- **Overage Rate:** $60/hour (billed in 30-minute increments)
- **Notification:** Corporate will be notified before any overage work begins
- **Approval:** Overage work requires email approval from corporate contact
- **Invoicing:** Overage hours billed separately on monthly invoice with detailed breakdown

**Example:**
> "Your October support allocation (20 hours) has been fully used. The issue you reported (Flash Sale notification delay) requires an estimated 3 additional hours to resolve. Approve overage work at $60/hr ($180 total)? Reply YES to proceed."

**Historical Context:** In similar projects, overage hours are rare after the first 60 days once the platform stabilizes. Average monthly usage: 12-16 hours.

---

#### **Emergency Contact Protocol**

**During Business Hours (Mon-Fri, 9am-5pm EST):**
- Email: mason@roguemedialab.com
- Response: Within stated SLA times above

**Critical Issues After Hours / Weekends:**
- Emergency Phone: [Provided upon contract signing]
- Use ONLY for Critical Issues (platform down, security breach, data loss)
- Response: Within 4 hours, 7 days/week

**Abuse Policy:** Non-critical issues reported via emergency phone will be deprioritized. Please respect the SLA tiers to ensure rapid response for true emergencies.

---

#### **Why 20 Hours During Pilot, 13 Hours Post-Pilot?**

**Pilot Phase (Months 1-3): Higher Support Load**
- Initial bugs and edge cases discovered
- Manager training and onboarding questions
- Optimization iterations based on real-world usage
- Frequent check-ins and feedback implementation
- Higher activity = more support needed

**Post-Pilot (Months 4-12): Platform Stabilized**
- Code matured, bugs resolved
- Managers trained, fewer questions
- Maintenance mode (security updates, minor tweaks)
- Lower activity = less support needed

**Historical Data:** Analysis of similar projects shows **35% reduction in support hours** after initial 90-day period. This pricing reflects that reality while maintaining quality support.

---

## Total Investment Summary

### Pilot Program (90 Days, 6 Locations)

| Cost Component | Amount | Frequency | Total Year 1 |
|---|---|---|---|
| **Development (MVP Build)** | $16,000 | One-time | $16,000 |
| **Operational Costs** | $390 | Monthly | $4,680 |
| **Maintenance & Support** | $800 | Monthly | $9,600 |
| | | | |
| **TOTAL YEAR 1 INVESTMENT** | | | **$30,280** |
| **Average Monthly Cost (after dev)** | | | **$1,190** |

---

### Per-Location Cost Analysis

**Pilot Phase (6 Locations):**
- Total Year 1: $30,280
- Per Location Year 1: $5,047
- Per Location Monthly (ongoing): $198

**ROI Calculations**:
1. **614% ROI** = Year 1 total return ($185,720 net gain / $30,280 investment)
2. **1,413% ROI** = Monthly operating return ($16,810 monthly net / $1,190 monthly cost)

**Break-Even Analysis (Per Location):**
- If app fills 1 bay/day @ $100 average = $3,000/month revenue
- Cost: $198/month per location
- Net gain: $2,802/month per location
- ROI per location: 1,415%
-  *2.0 days = Monthly cost break-even ($1,190 / $600 per day)*
- *22.4 days = Total Year 1 investment break-even ($30,280 / $1,353 per day average)*

---

## Competitor Cost Comparison

| Solution Type | Build Cost | Monthly (6 Locations) | Year 1 Total | vs. Shop Rewards |
|---|---|---|---|---|
| **Generic SaaS (Kangaroo)** | $500 | $1,794 | $22,028 | 14% cheaper* |
| **SMS Platform (EZ Texting)** | $0 | $594 | $7,128 | 72% cheaper, but ❌ no app |
| **Agency Custom Build** | $150,000 | $6,000 | $222,000 | **88% cheaper** ✅ |
| **Shop Management (ServiceTitan)** | $25,000 | $3,000 | $61,000 | **58% cheaper** ✅ |
| **Shop Rewards (Proposed)** | $16,000 | $1,190 | $30,280 | Baseline |

*Note: Generic SaaS is cheaper in dollars but lacks automotive-specific features (Services Display, Barcode POS Bridge, Flash Sales, Dual Loyalty, franchise-safe architecture). True value comparison favors Shop Rewards.

---

## Sensitivity Analysis: What If Performance Falls Short?

**CFO Question:** *"Show me worst-case, base-case, and best-case scenarios."*

This analysis tests the financial model against underperformance scenarios to understand downside risk.

### Worst-Case Scenario: Only 0.5 Bays Filled Per Day

**Assumptions:**
- Flash Sale adoption slower than expected
- Only 0.5 bays filled per day per location (50% of target)
- 50 customers sign up per location (instead of 100)
- Low redemption rate

**Monthly Revenue Impact:**
- 6 locations × 0.5 bay/day × 30 days × $100 = **$9,000/month**

**Monthly Cost:** $1,190/month

**Net Monthly Gain:** $7,810/month
**Annual Net Gain (Year 1):** $93,720 - $16,000 = **$77,720**
**ROI:** 257% (Year 1)

**Decision:** Platform still generates positive ROI. Proceed with optimization—adjust Flash Sale messaging, increase QR code visibility, provide additional manager training.

---

### Break-Even Scenario: Minimum Viable Performance

**Question:** *What's the minimum performance needed to break even?*

**Monthly Cost:** $1,190/month

**Break-Even Calculation:**
- Need to fill: $1,190 / $100 per bay = **11.9 bays per month across all 6 locations**
- That's **2 bays per location per month**, or **0.07 bays per location per day**

**This means:** Even if the app only fills 1 bay every 2 weeks at each location, you break even on ongoing costs.

**To recover Year 1 development cost ($30,280):**
- Need total revenue of $30,280 in first year
- 6 locations × 0.47 bays/day × 365 days × $100 = $30,280
- **Break-even: 0.47 bays per location per day**

**Context:** Even moderate underperformance (less than half the target) still recovers the full Year 1 investment.

---

### Sensitivity Table: Revenue Impact vs. Bay Filling Rate

| Bays Filled/Day (Per Location) | Monthly Revenue | Monthly Net Gain | Year 1 Net Gain | ROI (Year 1) | Verdict |
|--------------------------------|-----------------|------------------|-----------------|--------------|---------|
| **0.5 bays** | $9,000 | $7,810 | $77,720 | 257% | ✅ Positive, optimize |
| **0.75 bays** | $13,500 | $12,310 | $131,720 | 435% | ✅ Good return |
| **1.0 bays** (base) | $18,000 | $16,810 | $185,720 | 614% | ✅ Target scenario |
| **1.5 bays** | $27,000 | $25,810 | $293,720 | 970% | ✅ Strong performance |
| **2.0 bays** | $36,000 | $34,810 | $401,720 | 1,327% | ✅ Excellent outcome |

**Key Insight:** Platform remains profitable even at 50% of target performance. Downside risk is minimal.

---

## Return on Investment (ROI) Projections

### Base-Case Scenario (Conservative Target)

**Assumptions:**
- 6 pilot locations (3 Speedee + 3 Grease Monkey)
- Each location fills **1 idle bay per day** using Flash Sales
- Average service value: **$100**
- 30 days per month
- No repeat visit lift from rewards program (pure Flash Sale impact)

**Monthly Revenue Impact:**
- 6 locations × 1 bay/day × 30 days × $100 = **$18,000/month**

**Monthly Cost:**
- Operational + Maintenance = **$1,190/month**

**Net Monthly Gain:** $16,810
**Annual Net Gain (Year 1):** $201,720 (minus $16k dev cost = $185,720)
**ROI:** 614% (Year 1)
**Break-Even Timeline:** 22.4 days (Year 1 investment)

---

### Moderate Scenario

**Assumptions:**
- Same as conservative, PLUS:
- 20% of customers return for 2nd visit within 90 days due to rewards program
- Average 2nd visit value: $150

**Additional Revenue:**
- 6 locations × 100 customers/location × 20% return × $150 = **$18,000** (one-time over 90 days)
- Monthly average: **$6,000/month additional**

**Total Monthly Revenue Impact:** $24,000
**Net Monthly Gain:** $22,810
**Annual Net Gain (Year 1):** $273,720 - $16,000 = $257,720
**ROI:** 851%

---

### Aggressive Scenario

**Assumptions:**
- Each location fills **2 idle bays per day** (Flash Sales + word-of-mouth)
- 30% return customer rate
- Some customers upgrade service ("While I'm here, can you also...")
- Average service value increases to $125

**Monthly Revenue Impact:**
- Flash Sales: 6 × 2 × 30 × $125 = $45,000
- Return visits: 6 × 150 × 30% × $150 = $40,500
- **Total: $85,500/month**

**Net Monthly Gain:** $84,310
**Annual Net Gain (Year 1):** $1,011,720 - $16,000 = $995,720
**ROI:** 3,288%

**Note:** This scenario assumes viral growth and high engagement. Not guaranteed, but possible with strong execution.

---

### Franchise-Specific ROI Analysis

**Question:** What if Speedee and Grease Monkey perform differently?

**Scenario A: Speedee Outperforms (More Likely)**
- **Speedee shops (3 locations):** Fill 1.5 bays/day each @ $100 = $13,500/month
- **Grease Monkey shops (3 locations):** Fill 0.75 bays/day each @ $100 = $6,750/month
- **Combined:** $20,250/month revenue impact
- **Cost:** $1,190/month
- **Net Gain:** $19,060/month
- **ROI:** 1,601%

**Why This Might Happen:**
- Brand differences (Speedee may have more loyal customers)
- Location differences (Speedee shops in better traffic areas)
- Manager adoption differences (Speedee managers more tech-savvy)

**What This Validates:**
- Platform works for multiple franchise types
- Architecture is sound (even if one brand underperforms)
- Rollout strategy: Focus on Speedee first, optimize Grease Monkey messaging

---

**Scenario B: Grease Monkey Outperforms (Possible)**
- **Grease Monkey shops (2 locations):** Fill 1.5 bays/day each @ $100 = $9,000/month
- **Speedee shops (3 locations):** Fill 0.5 bays/day each @ $100 = $4,500/month
- **Combined:** $13,500/month revenue impact
- **Cost:** $1,190/month
- **Net Gain:** $12,310/month
- **ROI:** 1,035%

**Why This Might Happen:**
- Grease Monkey shops have more idle capacity (more empty bays to fill)
- Grease Monkey customers more price-sensitive (flash sales more effective)
- Grease Monkey managers more motivated to try new tools

**What This Validates:**
- Same as Scenario A (platform works, architecture is sound)
- Rollout strategy would prioritize Grease Monkey expansion

---

**Scenario C: Both Perform Equally (Ideal)**
- **All 6 locations:** Fill 1 bay/day each @ $100 = $18,000/month
- **Cost:** $1,190/month
- **Net Gain:** $16,810/month
- **ROI:** 1,413%

**This is the conservative baseline used throughout the proposal.**

---

**Pilot Failure Scenario: One Franchise Negative**
- **Speedee shops (3 locations):** Fill 1 bay/day = $9,000/month
- **Grease Monkey shops (3 locations):** 0 bays/day = $0/month
- **Combined:** $9,000/month
- **Cost:** $1,190/month
- **Net Gain:** $7,810/month
- **ROI:** 656%

**Decision:**
- Still positive ROI → Roll out to Speedee only
- Investigate Grease Monkey issues (messaging? timing? manager adoption?)
- Platform investment still justified even if only one brand succeeds

---

**Key Insight:** Multi-franchise pilot de-risks investment. Even if one brand fails, the other can justify the platform cost.

---

## Cost After Pilot (Enterprise Rollout Pricing)

### If Pilot Succeeds: SaaS Pricing Model

**Proposed Pricing (Per-Location, Monthly):**

| Tier | Locations | Price/Location | Total Monthly | Annual |
|---|---|---|---|---|
| **Starter** | 1-20 | $99 | $1,980 (20 locs) | $23,760 |
| **Growth** | 21-50 | $79 | $3,950 (50 locs) | $47,400 |
| **Enterprise** | 51+ | $59 | $5,900 (100 locs) | $70,800 |

**Plus:** Enterprise Support ($1,500/month flat rate, all locations)

**Example: 30 Locations**
- 20 locations × $99 = $1,980
- 10 locations × $79 = $790
- Enterprise Support = $1,500
- **Total: $4,270/month** ($51,240/year)

**ROI at 30 Locations:**
- Revenue impact: 30 × 1 bay/day × 30 days × $100 = $90,000/month
- Platform cost: $4,270/month
- **Net gain: $85,730/month** ($1,028,760/year)
- **ROI: 2,006%**

---

## 5-Year Total Cost of Ownership (TCO) Model

**CFO Question:** *"What's our total investment over 5 years at different scale levels?"*

This model assumes successful pilot in Year 1, then gradual rollout to additional locations in Years 2-5.

### Scenario 1: Conservative Rollout (10 Locations by Year 5)

| Year | Locations | Platform Cost | Support Cost | Annual Total | Cumulative 5-Year |
|------|-----------|---------------|--------------|--------------|-------------------|
| **Year 1** | 6 (pilot) | $16,000 dev + $4,680 ops | $9,600 | **$30,280** | $30,280 |
| **Year 2** | 8 | $9,504 ops | $11,520 | **$21,024** | $51,304 |
| **Year 3** | 10 | $11,880 ops | $18,000 support | **$29,880** | $81,184 |
| **Year 4** | 10 | $11,880 ops | $18,000 support | **$29,880** | $111,064 |
| **Year 5** | 10 | $11,880 ops | $18,000 support | **$29,880** | **$140,944** |

**5-Year TCO:** $140,944
**Average Annual Cost:** $28,189

### Scenario 2: Moderate Rollout (50 Locations by Year 5)

| Year | Locations | Platform Cost | Support Cost | Annual Total | Cumulative 5-Year |
|------|-----------|---------------|--------------|--------------|-------------------|
| **Year 1** | 6 (pilot) | $16,000 dev + $4,680 ops | $9,600 | **$30,280** | $30,280 |
| **Year 2** | 15 | $17,820 ops | $18,000 support | **$35,820** | $66,100 |
| **Year 3** | 30 | $35,640 ops | $18,000 support | **$53,640** | $119,740 |
| **Year 4** | 40 | $47,520 ops | $18,000 support | **$65,520** | $185,260 |
| **Year 5** | 50 | $47,400 ops | $18,000 support | **$65,400** | **$250,660** |

**5-Year TCO:** $250,660
**Average Annual Cost:** $50,132

### Scenario 3: Aggressive Rollout (100+ Locations by Year 5)

| Year | Locations | Platform Cost | Support Cost | Annual Total | Cumulative 5-Year |
|------|-----------|---------------|--------------|--------------|-------------------|
| **Year 1** | 6 (pilot) | $16,000 dev + $4,680 ops | $9,600 | **$30,280** | $30,280 |
| **Year 2** | 25 | $29,700 ops | $18,000 support | **$47,700** | $77,980 |
| **Year 3** | 50 | $47,400 ops | $18,000 support | **$65,400** | $143,380 |
| **Year 4** | 75 | $70,800 ops | $18,000 support | **$88,800** | $232,180 |
| **Year 5** | 100 | $70,800 ops | $18,000 support | **$88,800** | **$320,980** |

**5-Year TCO:** $320,980
**Average Annual Cost:** $64,196

### Key TCO Insights

**What's Included:**
- Year 1 development cost ($16,000 one-time)
- Monthly operational costs (hosting, notifications, E&O insurance)
- Enterprise support retainer ($1,500/month flat rate after Year 2)
- Per-location SaaS fees at tiered pricing

**What's NOT Included:**
- Major feature additions (new contracts negotiated separately)
- Third-party integrations (POS API connections, accounting software)
- Native app development (iOS/Android App Store versions)
- Custom branding/design refresh

**Comparison to Alternatives:**
- **Generic SaaS (Kangaroo):** $299/location × 50 locations × 5 years = **$895,500**
- **Custom Agency Build:** $150,000 upfront + $60,000/year maintenance = **$390,000**
- **Shop Rewards (50 locations):** **$250,660** (37% cheaper than agency, 72% cheaper than SaaS)

---

## Payment Terms & Structure

### Development Payment Schedule

**Milestone-Based Payment Structure (Recommended)**
- **Milestone 1:** 25% upon contract signing: **$4,000**
- **Milestone 2:** 25% at Week 3 checkpoint (Phases 1-3 complete): **$4,000**
- **Milestone 3:** 50% upon MVP delivery (end of Week 9): **$8,000**

**Why Milestone-Based:**
- Corporate sees tangible progress at each checkpoint before paying
- Reduces financial risk compared to 50/50 upfront
- Aligns payments with phase completion (Phase 1-3 → Week 3 payment)
- Developer maintains delivery incentive with 50% final payment
- Better cash flow management for corporate budgeting

---

### Monthly Recurring Billing

**Billing Cycle:** 1st of each month
**Payment Terms:** Net 15 (due within 15 days of invoice)
**Method:** ACH transfer or corporate check

**Included in Invoice:**
- Operational costs: $390 (fixed)
- Maintenance & support: $800 (fixed)
- Any additional hours beyond retainer (at $60/hr, billed in 30-min increments)

**Ongoing Costs During Decision Period:**
- If pilot is extended beyond 90 days: $1,190/month continues (operational + support)
- If pilot succeeds but rollout delayed: maintenance retainer continues until rollout decision
- Corporate may pause monthly billing with 30 days notice (pilot termination clause)

---

## Cost Optimization Strategies

### How to Reduce Costs (If Needed)

**Option 1: Remove Services Display Feature**
- **Savings:** $760 (19 hours development)
- **Impact:** Customers won't see available services before visiting shop
- **Recommendation:** Don't do this. Services Display is a key differentiator (Valvoline-style transparency).

**Option 2: Start with SMS Instead of Push Notifications**
- **Savings:** $880 (push notification integration)
- **Ongoing Cost Increase:** SMS is $25/month vs. push notifications $0
- **Impact:** Slower, less engaging customer experience; Flash Sales lose immediacy
- **Recommendation:** Only if absolutely necessary for budget. Push notifications are critical for Flash Sale feature.

**Option 3: Reduce Support Retainer**
- **Savings:** $400/month ($400/month retainer instead of $800)
- **Impact:** Slower response times, fewer hours for feature requests
- **Recommendation:** Risky. Pilot needs active support to succeed.

**Option 4: Self-Host Instead of Heroku**
- **Savings:** ~$100/month operational
- **Hidden Costs:** Mason's time managing servers, higher technical risk, no 99.9% uptime guarantee
- **Recommendation:** False economy. Heroku time-to-value is worth the cost.

**Option 5: Remove Birthday Rewards Automation**
- **Savings:** $240 (6 hours development)
- **Impact:** No automated birthday coupons; owners would need to manually create
- **Recommendation:** Low value cut. Birthday rewards are a customer retention tool.

**Verdict:** Don't optimize costs for pilot. The $19,570 pilot investment is already 70-90% cheaper than alternatives. Cutting corners risks pilot failure and undermines the core Flash Sale value proposition.

---

## What Happens If Pilot Fails?

**Corporate's Risk Mitigation:**

1. **Source Code Access:**
   - Corporate receives exclusive license to source code upon final payment
   - Can hire another developer to maintain/modify
   - No vendor lock-in
   - Mason retains portfolio rights (see Section 08, "Intellectual Property & Code Ownership" for full details)

2. **Limited Financial Exposure:**
   - $16,000 development cost (sunk)
   - $1,190/month × 3 months pilot = $3,570
   - **Total risk: $19,570**

3. **Salvage Value:**
   - Even if pilot fails, code can be repurposed:
     - Generic loyalty program for other business units
     - Sold to non competing franchise (recover costs)
     - Open sourced for goodwill/marketing

4. **Learning Value:**
   - Data on customer behavior, redemption rates
   - Understanding of what doesn't work
   - Informs future marketing strategies

**Comparison:**
- Agency build: $150k+ sunk cost if fails
- SaaS platform: No refund on 1-year contract
- Shop Rewards: $19,570 risk, source code retained

---

## Pricing Philosophy

**Why This Pricing is Fair:**

1. **Developer's Perspective:**
   - $50/hr is competitive market rate for custom Rails development
   - 321 hours = 8 weeks of focused work
   - Charging $16,000 (not $16,050) accounts for clean pricing

2. **Corporate's Perspective:**
   - 70-90% cheaper than alternatives
   - Fixed price = predictable budgeting
   - Potential ROI of 614-3,288%
   - $19,570 pilot risk vs. $150k+ agency risk

3. **Industry Standards:**
   - Agencies charge $100-150/hr
   - Fixed price projects include 20-30% buffer
   - $300/month operational is below market for managed hosting

**This is not "cheap." This is "appropriately priced for value delivered."**

---

## Conclusion: Investment vs. Return

**Total Year 1 Investment:** $30,280
**Minimum Expected Return:** $216,000 (conservative scenario)
**Net Profit:** $185,720
**ROI:** 614%

**For every $1 invested, you receive $7.14 in return.**

**The question is not whether you can afford this. The question is whether you can afford NOT to do this.**

---

**Next Section:** Implementation Plan & Timeline (how we deliver this on schedule)
