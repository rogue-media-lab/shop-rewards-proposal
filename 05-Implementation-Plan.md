# Implementation Plan & Timeline

**Document:** Development Schedule & Deployment Strategy
**Project:** Shop Rewards - Proprietary Loyalty Platform
**Date:** November 2025

---

## Project Timeline Overview

**Day 0:** Contract approval
**Weeks 1-9:** MVP development (9 weeks / 45 business days)
**End of Week 9:** MVP delivery and stakeholder demonstration
**Week 10:** Pilot preparation and manager training
**Week 11:** Pilot launch (2.5 months from contract approval)
**Weeks 11-23:** 90-day pilot phase (13 weeks)
**Week 24:** Rollout decision (6 months from contract approval)

**Total Development Time:** 9 weeks
**Total Pilot Duration:** 13 weeks
**Total Time to Decision:** 24 weeks (6 months)

---

## Development Phases (Weeks 1-9)

### Week 1: Foundation & Authentication
**Timeline:** Days 1-5 (Week 1)
**Goal:** Project setup, database, authentication for customers and admins

#### Deliverables:
- ✅ Rails 8 app initialized with PostgreSQL database
- ✅ Tailwind CSS configured with responsive design system
- ✅ **Franchise model with branding fields (logo, colors)**
- ✅ **Shop model with QR code token generation**
- ✅ **ShopAssignment join table (admin-to-shop relationships)**
- ✅ User model with phone-based authentication (Devise) + **preferred_shop_id**
- ✅ AdminUser model with separate authentication + **role enum**
- ✅ Profile model with user association
- ✅ Basic navigation and layout templates
- ✅ Development and staging environments on Heroku
- ✅ **Seed data: 2 franchises (Speedee, Grease Monkey), 6 pilot shops (3 per brand)**

#### Key Milestones:
- **Day 1-2:** Project scaffolding, database setup, Git repository
- **Day 3:** User authentication working (signup, login, logout)
- **Day 4:** Admin authentication working (separate namespace)
- **Day 5:** Deploy to Heroku staging, verify both auth systems work

#### Checkpoint Meeting (End of Week 1):
- Demo: User and admin can sign up and log in
- Review: Database schema and model relationships
- Discuss: Any questions about project direction

---

### Week 2: Admin Dashboard & Flash Sales
**Timeline:** Days 6-10 (Week 2)
**Goal:** Build core "Bay Filler" functionality for shop managers

#### Deliverables:
- ✅ **Manager dashboard with stats cards (shop-scoped metrics)**
- ✅ Coupon model (title, discount, duration, expiration) + **shop_id**
- ✅ Flash Sale creation form (simple, <60 second workflow) + **shop scoping**
- ✅ Active Flash Sales list view (**only THIS manager's shop**)
- ✅ Customer lookup by phone number (**shop-scoped results**)
- ✅ Coupon redemption interface (mark as used)
- ✅ Basic analytics: total customers, active coupons, redemptions (**per-shop**)

#### Key Milestones:
- **Day 1-2:** Coupon model and database migrations
- **Day 3:** Flash Sale creation form with validation
- **Day 4:** Customer lookup and redemption workflow
- **Day 5:** Admin dashboard polish and testing

#### Checkpoint Meeting (End of Week 2):
- Demo: Manager creates Flash Sale, looks up customer, redeems coupon
- Review: Admin user experience and workflow efficiency
- Adjust: Any UX improvements based on feedback

---

### Week 3: Customer Features & Rewards
**Timeline:** Days 11-15 (Week 3)
**Goal:** Build customer facing coupon wallet and rewards tracking

#### Deliverables:
- ✅ **Shop selection during signup (zip code → nearby shops → select)**
- ✅ **QR code signup flow (auto-select shop from token)**
- ✅ Customer coupon wallet (view active Flash Sales **from their shop only**)
- ✅ Countdown timer for time-sensitive offers
- ✅ Rewards points system (add points, view balance) + **shop_id tracking**
- ✅ Reward program model (define rules like "3 for 1 free") + **shop_id**
- ✅ Rewards dashboard with progress bar (**shop-scoped progress**)
- ✅ Redemption history page (past coupons and rewards **at their shop**)
- ✅ User profile edit page

#### Key Milestones:
- **Day 1-2:** Coupon wallet view with countdown timers
- **Day 3:** Rewards points logic and tracking
- **Day 4:** Rewards dashboard with visual progress indicators


#### Checkpoint Meeting (End of Week 3):
- Demo: Customer views coupons and tracks reward progress
- Review: Customer user experience and mobile responsiveness
- Plan: Week 4 priorities (Services, Barcode, Standing Coupons)
- **Staging Environment Access:** Corporate receives access to staging environment at Week 3 for early preview and testing

---

### Week 4: Services Display, Barcode Generation & Standing Coupons
**Timeline:** Days 16-20 (Week 4)
**Goal:** Implement automotive-specific features and POS integration bridge

#### Deliverables:
- ✅ Services model & database schema (icon, name, time estimate)
- ✅ Owner services CRUD interface (master service list)
- ✅ Manager service assignment UI (select services for shop)
- ✅ Customer service cards display (Valvoline-style)
- ✅ Barby gem integration (Code 128 barcodes)
- ✅ Barcode generation for fixed amount coupons
- ✅ Barcode generation for dynamic amounts (points redemption)
- ✅ Full-screen barcode display UI (customer shows to manager)
- ✅ Standing coupons model & schema (owner-level ongoing promos)
- ✅ Owner coupon CRUD interface
- ✅ Birthday coupon auto-generation (scheduled job)
- ✅ OneSignal account setup and integration
- ✅ Push notification opt-in flow
- ✅ Notification delivery testing (iOS, Android)

#### Key Milestones:
- **Day 1:** Services model and owner CRUD interface
- **Day 2:** Barcode generation system (Code 128)
- **Day 3:** Standing coupons + birthday rewards automation
- **Day 4:** OneSignal setup and Rails integration
- **Day 5:** Test full barcode flow: Customer → Manager scans → Discount applied

#### Checkpoint Meeting (End of Week 4):
- Demo: Services display, barcode scanning, push notifications working
- Review: POS barcode configuration requirements
- Test: Scan barcode with test POS system

---

### Week 5: Legal Compliance, PWA & Multi-Tenant Features
**Timeline:** Days 21-25 (Week 5)
**Goal:** Ensure legal compliance, configure PWA, and build owner features

#### Deliverables:
- ✅ TCPA opt-in checkbox on signup form
- ✅ TCPA consent logging (date/time stamp)
- ✅ Terms of Service page (legal content + design)
- ✅ Privacy Policy page (GDPR/CCPA compliant)
- ✅ SMS opt-out mechanism ("Reply STOP")
- ✅ **Owner dashboard (multi-shop aggregate view)**
- ✅ **Shop selector dropdown for owners**
- ✅ **Dynamic branding system (CSS variables, franchise-specific theming)**
- ✅ **Three-portal routing (/manager, /owner, /corporate namespaces)**
- ✅ **Authorization checks (Pundit gem, role-based access control)**
- ✅ PWA manifest file
- ✅ Service worker for offline support
- ✅ PWA icons (192x192, 512x512)
- ✅ "Add to Home Screen" prompt testing

#### Key Milestones:
- **Day 1:** TCPA checkbox and consent tracking implementation
- **Day 2-3:** Legal pages (Terms, Privacy) content and design
- **Day 4:** PWA manifest and service worker configuration
- **Day 5:** Test PWA installation on iOS and Android devices

#### Checkpoint Meeting (End of Week 5):
- Demo: Full legal compliance, PWA installable on phones
- Review: Legal pages for accuracy and clarity
- Plan: Final week testing and demo preparation

---

### Week 6: Perks System & Manager PIN Security
**Timeline:** Days 26-30 (Week 6)
**Goal:** Implement dual loyalty system and fraud prevention

#### Deliverables:
- ✅ Perks model & database schema (service-count + points-threshold types)
- ✅ Service-count tracking logic ("3 of 4 oil changes")
- ✅ Points-threshold perks ("500 pts = $50 off brakes")
- ✅ Perk progress display (customer dashboard with visual progress bars)
- ✅ Owner perk configuration interface (set thresholds per shop)
- ✅ Manager PIN digest field & encryption (bcrypt)
- ✅ PIN entry interface (Stimulus keypad UI)
- ✅ PIN verification logic (check before redemption)
- ✅ Audit trail logging (track which manager confirmed with admin_id)
- ✅ Redemption table updates (polymorphic for flash alerts, coupons, perks)

#### Key Milestones:
- **Day 1-2:** Perks model with two perk types implemented
- **Day 3:** Perk progress tracking integrated with PO workflow
- **Day 4:** Manager PIN system with encryption
- **Day 5:** Test complete redemption flow with PIN confirmation

#### Checkpoint Meeting (End of Week 6):
- Demo: Dual loyalty system (Points + Perks) working together
- Review: PIN security and audit trail
- Test: Manager confirms redemption with PIN

---

### Week 7: PO Transaction Workflow & Flash Alert Check-In
**Timeline:** Days 31-35 (Week 7)
**Goal:** Implement pain-free manager workflows for daily operations

#### Deliverables:
- ✅ Transaction model & database schema (PO, service_type, amount, points)
- ✅ Service type dropdown (manager UI with pre-populated list)
- ✅ Auto-calculation preview (show points + perk progress before submit)
- ✅ Points + perks update on submit (single workflow updates both systems)
- ✅ Transaction history view (manager sees customer service log)
- ✅ Flash alert check-in timestamp field (redemptions table)
- ✅ Manager "Check In" button UI (reserve discount for later)
- ✅ Same-day validation logic (expires at midnight)
- ✅ Checked-in customers list view (manager sees queue)

#### Key Milestones:
- **Day 1-2:** Transaction workflow with auto-calculation
- **Day 3:** Service type dropdown and points/perks integration
- **Day 4:** Flash alert check-in system
- **Day 5:** Test complete manager workflow: PO entry → Check-in → Redemption

#### Checkpoint Meeting (End of Week 7):
- Demo: Manager enters PO in ~30 seconds, points + perks auto-update
- Review: Check-in workflow for busy days
- Test: Full transaction workflow with real scenarios

---

### Week 8: Testing & Polish
**Timeline:** Days 36-40 (Week 8)
**Goal:** Comprehensive QA, bug fixes, and performance optimization

#### Deliverables:
- ✅ End-to-end testing (signup → service → redemption → reward)
- ✅ Bug fixes from QA testing
- ✅ Mobile responsiveness testing (iPhone, Android, tablets)
- ✅ Cross-browser testing (Safari, Chrome, Samsung Internet, Firefox)
- ✅ Performance optimization (page load <2 seconds, barcode generation <100ms)
- ✅ Security audit (SQL injection, XSS, CSRF protection verified)
- ✅ Accessibility testing (keyboard nav, screen readers)
- ✅ Staging environment seed data (sample customers, Flash Sales, perks unlocked)

#### Key Milestones:
- **Day 1-2:** Comprehensive testing across all features
- **Day 3:** Bug fixing and edge case handling
- **Day 4:** Performance tuning and optimization
- **Day 5:** Security review and vulnerability scanning

#### Checkpoint Meeting (End of Week 8):
- Demo: All features working smoothly on mobile
- Review: Bug fix list and resolution status
- Test: Load testing with simulated pilot traffic

---

### Week 9: Documentation, Training Materials & MVP Delivery
**Timeline:** Days 41-45 (Week 9)
**Goal:** Finalize documentation, training, and prepare for pilot launch

#### Deliverables:
- ✅ Admin training documentation (PDF guide: "How to Use Shop Rewards")
- ✅ Manager quick reference card (1-page cheat sheet for daily operations)
- ✅ POS barcode configuration guide (setup instructions for Sage POS)
- ✅ Customer FAQ page (common questions, troubleshooting)
- ✅ Pilot launch checklist (pre-flight verification steps)
- ✅ QR code printable PDFs for all 6 pilot shops
- ✅ Final staging environment review and data cleanup
- ✅ Production deployment preparation
- ✅ Source code repository organization and documentation
- ✅ Handoff materials for ongoing support

#### Key Milestones:
- **Day 1-2:** Write all training documentation and guides
- **Day 3:** Create QR codes and printable materials
- **Day 4:** Final staging review with corporate stakeholders
- **Day 5:** Deploy to production, verify all systems operational

#### Final Review Meeting (End of Week 9):
- **MVP Delivery:** Review all completed features with stakeholders
- **Review Checklist:** All MVP features working and tested
- **Production Environment:** Deployed and ready for pilot launch
- **Source Code Repository:** Corporate receives full access to Git repository upon final payment
- **Q&A Session:** Address any questions or concerns
- **Next Steps:** Schedule manager training for Week 10

---

## MVP Demonstration (End of Week 9)

### Demo Flow (5 Minutes)

**Setup (Before Demonstration):**
- Staging environment running with sample data
- Mobile device with app installed as PWA
- Laptop/tablet for admin dashboard demonstration
- Internet connection verified

**Demonstration Script:**

**1. Introduction (30 seconds)**
> "I'm excited to demonstrate Shop Rewards—the platform that turns empty bays into revenue-generating bays with one button click."

**2. The Problem (30 seconds)**
> "Here's the problem: It's 2 PM on a Tuesday. You have 3 empty bays and a full crew on payroll. That's $150/hour bleeding from your budget."

**3. The Solution - Manager View (90 seconds)**
- Log into manager dashboard on tablet (`/manager` portal)
- Show: "127 customers at Speedee Main Street, 3 Flash Sales sent this week"
- Click "Send Flash Sale" button
- Fill out form: "50% Off Oil Change - Next 2 Hours"
- Click "Send Now"
- Dashboard updates: "Flash Sale sent to 127 customers at Speedee Main Street at [current time]"
- **Key point:** "Only THIS shop's customers receive this, not other locations"

**4. The Magic - Customer View (90 seconds)**
- Switch to mobile device (already open to app)
- Push notification appears: "🚨 Flash Sale! 50% off oil change - next 2 hours"
- Tap notification → App opens to Coupon Wallet
- Show countdown timer: "1:57:34 remaining"
- Show customer's reward progress: "2 of 3 oil changes - one more for free!"

**5. The Differentiators - Services Display & Barcode Bridge (60 seconds)**
- Tap "Services" tab → Show service cards (icon, name, time)
- Example: "Full-Service Oil Change ~ 15 mins", "Air Conditioning ~ 30-60 mins"
- **Key point:** "Customer knows what you offer before they visit, Valvoline-style transparency"
- Tap coupon → Full-screen Code 128 barcode appears
- **Key point:** "Manager scans this at POS like a paper coupon—franchise-safe, no API integration"
- Show manager view: Enter 4-digit PIN to confirm → Points deducted
- **Key point:** "PIN prevents fraud, creates audit trail of who confirmed redemption"

**6. The Strategic Value - Owner Dashboard (60 seconds)**
- Log into owner dashboard on laptop (`/owner` portal)
- Show multi-shop view: "Owner Dashboard"
- Display:
  ```
  Speedee Main Street: 127 customers, $6,200 revenue recovery
  Speedee Downtown: 89 customers, $4,100 revenue recovery
  Grease Monkey West: 62 customers, $2,900 revenue recovery

  Total: 278 customers, $13,200 revenue recovery this month
  ```
- **Key point:** "One owner, multiple shops, multiple brands—all managed from one dashboard."
- "This is why it's a multi-franchise platform, not just an app."

**7. The Ask (30 seconds)**
> "This is ready for pilot launch. 6 locations: 3 Speedee + 3 Grease Monkey. 90 days. Total investment: $19,570 for the pilot. Conservative ROI: $185,720 in recovered revenue. Multi-franchise architecture proven with barcode POS bridge, dual loyalty system, and services transparency. Are we ready to move forward?"

**Q&A (5-10 minutes)**
- Laptop ready to show admin dashboard in detail
- Prepared to demonstrate customer redemption flow
- Address questions about TCPA compliance, costs, scalability

---

## Post-MVP Delivery: Pilot Launch (Weeks 7-8)

### Week 7: Pilot Location Selection & Setup
**Timeline:** Week 7 (Days 31-35)
**Goal:** Select pilot locations, set up accounts, train managers

#### Tasks:
1. **Location Selection:**
   - Corporate identifies 3-5 pilot locations
   - Criteria: Geographic diversity, willing managers, data tracking capability

2. **Account Setup:**
   - **Owner Account Creation:**
     - Corporate identifies franchise owners for pilot program
     - Mason creates owner accounts during pilot setup (Week 7)
     - Each owner assigned to their shops via `shop_assignments` table
     - Owner can view aggregate data across all their shops (regardless of franchise brand)
   - **Manager Account Creation:**
     - Create manager accounts (one per shop manager)
     - Each manager assigned to ONE shop only via `shop_assignments` table
     - Manager can only view/manage their specific shop's data
   - **Account Management Post-Pilot:**
     - Admin interface for corporate to manage owner accounts (post-MVP enhancement)
     - During pilot: Mason handles account creation/modification
   - **Testing:**
     - Verify manager sees only their shop
     - Verify owner sees all their shops
     - Test dynamic branding works per franchise
   - Configure shop-specific settings (branding assets, initial rewards programs)

3. **Branding Assets Collection:**
   - Franchise owner provides branding assets during pilot setup:
     - **Logos:** SVG or PNG format (transparent background preferred)
     - **Colors:** Primary and secondary brand colors (hex codes)
     - **Example:** `#E31837` (Speedee red), `#FFD100` (Grease Monkey yellow)
   - **If assets not available:** Generic placeholder branding used initially, can be updated later
   - **Required per franchise:** Logo (header), logo (icon), primary color, secondary color

4. **Manager Training (1 Hour Per Location):**
   - **30 minutes:** Product walkthrough, send test Flash Sale
     - **Key concept:** "You can only send flash sales to YOUR shop's customers"
     - **Key concept:** "You can only see customers who signed up at YOUR shop"
   - **15 minutes:** Customer lookup, redemption, add points
   - **10 minutes:** Manager vs Owner dashboard (show difference)
   - **5 minutes:** Q&A, troubleshooting common scenarios

5. **Marketing Materials:**
   - Print QR code counter cards: "Join our Rewards Program!"
   - Design window cling: "Download our app for exclusive deals"
   - Create initial customer incentive: "Sign up today, get $10 in rewards points"

---

### Week 8: Soft Launch & Monitoring
**Timeline:** Week 8 (Days 36-40)
**Goal:** Pilot locations go live, monitor early adoption

#### Soft Launch Checklist:
- ✅ All manager accounts active and tested
- ✅ QR codes and signage displayed at pilot locations
- ✅ Monitoring dashboards configured (Sentry, UptimeRobot)
- ✅ Support email and phone number communicated to managers
- ✅ Daily check-in schedule established (first week only)

#### Week 8 Activities:
- **Day 1:** Pilot locations announce app to customers, QR codes go up
- **Day 2-3:** Monitor signup rate, troubleshoot any issues
- **Day 4:** First Flash Sales sent by managers
- **Day 5:** Weekly sync call with all pilot managers

**Success Metrics (Week 8):**
- Target: 20-50 signups per location
- Target: 2-3 Flash Sales sent per location
- Target: 10-15% redemption rate on Flash Sales

---

## Pilot Phase (Weeks 9-20): 90-Day Measurement Period

### Monitoring & Optimization

**Weekly Activities:**
- **Every Monday:** Email report to corporate stakeholders
  - New signups this week
  - Flash Sales sent
  - Redemptions and redemption rate
  - Revenue impact estimate

- **Every Friday:** Check-in call with pilot managers (optional)
  - Address any issues
  - Share best practices across locations
  - Gather feature requests

**Monthly Activities:**
- **End of Month 1 (Jan 15):** Detailed report and stakeholder meeting
- **End of Month 2 (Feb 15):** Mid-pilot checkpoint, adjust strategy if needed
- **End of Month 3 (Mar 15):** Final pilot results presentation

### Data Collection & KPI Tracking Methodology

**CEO Question:** *"How do we measure success? We need clear, measurable KPIs with a methodology for tracking them."*

---

### Primary KPIs (Tracked Automatically by Platform)

**1. Flash Sale Attribution**

**Metric:** Number of customers who arrived specifically because of a Flash Sale notification

**Tracking Methodology:**
- App generates unique barcode for each Flash Sale event
- Customer redeems barcode at POS (manager scans it)
- App logs redemption with timestamp, location, customer ID
- Dashboard shows: "Flash Sale: 50% off oil change (2pm-4pm) → 12 redemptions → $600 revenue"

**Baseline Comparison:** None needed. This is NEW revenue that wouldn't exist without the Flash Sale feature.

---

**2. Customer Signup Rate**

**Metric:** % of in-shop customers who sign up for the app

**Tracking Methodology:**
- Baseline: Average daily car count per location (from POS data)
- Example: Location averages 40 cars/day
- App logs: 8 new signups on Tuesday
- Signup rate: 8 / 40 = 20% of customers signed up that day

**Weekly Report:** "Week 1: 47 signups / 240 customers = 19.6% signup rate"

---

**3. Reward Redemption Rate**

**Metric:** % of customers who earn AND redeem a reward

**Tracking Methodology:**
- App tracks customer progress: "3 of 4 oil changes completed"
- When customer redeems 4th free oil change, app generates reward barcode
- Manager scans reward barcode at POS
- App logs redemption

**Dashboard shows:** "125 customers reached 4 oil changes → 87 redeemed free service = 69.6% redemption rate"

---

**4. Repeat Visit Lift**

**Metric:** % of customers who return within 90 days (with vs. without app)

**Tracking Methodology:**
- **Control group:** Historical data from POS (before app existed)
  - Example: "30% of customers return within 90 days" (baseline)
- **App group:** Customers who signed up for app
  - App tracks: Customer #1234 visited on 10/1, then again on 11/15 (45 days later)
  - **Repeat rate:** 42% of app users returned within 90 days

**Comparison:** 42% (app users) vs. 30% (historical baseline) = **40% lift in repeat visits**

---

### Secondary KPIs (Manual Tracking Required)

**5. Daily Car Count Increase**

**Metric:** Change in daily car count at pilot locations

**Tracking Methodology:**
- **Baseline (Months 1-3 before pilot):** Average daily car count per location from POS data
  - Example: Location averages 38 cars/day (September-November 2025)
- **Pilot Period (Months 1-3 during pilot):** Track daily car count from POS
  - Example: Location averages 43 cars/day (December 2025-February 2026)
- **Increase:** 43 - 38 = +5 cars/day = 13.2% increase

**Control for seasonality:** Compare to same period last year
  - Last year (Dec-Feb 2024): 39 cars/day average
  - This year (Dec-Feb 2026): 43 cars/day average
  - Net increase after seasonal adjustment: 10.3%

---

**6. Revenue Per Flash Sale Event**

**Metric:** Average revenue generated per Flash Sale

**Tracking Methodology:**
- Manager creates Flash Sale: "30% off transmission flush - next 3 hours"
- App logs: 8 customers redeemed this Flash Sale
- Average service value: $150
- **Total revenue from this event:** 8 × $150 = $1,200
- **Net revenue (after discount):** $1,200 × 70% = $840

**Weekly aggregate:** "Sent 4 Flash Sales this week → 31 redemptions → $2,640 net revenue"

---

### Automated Weekly Report Format

**Every Monday, corporate receives:**

```
Shop Rewards Pilot - Week 4 Report (Jan 22-28, 2026)

=== Overall Performance ===
- Total signups this week: 47 (19.2% signup rate)
- Flash Sales sent: 12
- Flash Sale redemptions: 68 (redemption rate: 22.7%)
- Estimated revenue impact: $3,680
- Repeat customers: 14 (customers making 2nd+ visit)

=== Location Breakdown ===
Speedee Main St:
  - Signups: 12 | Flash Sale redemptions: 15 | Revenue: $780

Speedee Downtown:
  - Signups: 9 | Flash Sale redemptions: 11 | Revenue: $620

[... 4 more locations ...]

=== Cumulative (Weeks 1-4) ===
- Total customers: 184
- Total Flash Sale revenue: $12,940
- Platform cost (4 weeks): $1,190
- Net gain (4 weeks): $11,750
- Annualized ROI: 1,482%
```

**Action Items Flagged:**
- ⚠️ Grease Monkey West: Low signup rate (8%) - consider QR code placement
- ✅ Speedee Main St: 28% signup rate - share best practices with other managers

---

**Qualitative Metrics:**
- Manager satisfaction surveys (ease of use, time savings)
- Customer feedback (app reviews, support tickets)
- Staff adoption (are managers actually using it?)

### Optimization Opportunities

**Based on pilot data, may optimize:**
- Flash Sale timing (what time of day gets best response?)
- Discount percentages (is 50% necessary, or does 30% work?)
- Reward thresholds (are 3 oil changes too many? Should it be 2?)
- Notification copy (what messaging gets best open rates?)

---

## Decision Point: Week 22 (5 Months from Contract Approval)

### Pilot Success Criteria

**CFO Question:** *"What if only 3 of the 6 shops succeed? What's the threshold?"*

**Location-Based Success Threshold:**

The pilot will be considered successful if **at least 4 of 6 locations (67%)** meet minimum performance criteria. This accounts for:
- Manager adoption variability (some managers more tech-savvy than others)
- Location differences (traffic patterns, customer demographics)
- Brand performance differences (Speedee vs. Grease Monkey)

**Go/No-Go Decision Framework:**

---

### Scenario A: PROCEED TO ROLLOUT ✅

**Threshold:** 4-6 locations meet success criteria (67-100%)

**Minimum Per-Location Success Criteria:**
- ✅ 10% increase in daily car count at that location
- ✅ 15%+ Flash Sale redemption rate
- ✅ 100+ customers signed up
- ✅ Positive manager feedback (4/5 stars)
- ✅ Platform fills at least 0.5 bays/day (50% of target)

**Decision:** Proceed to enterprise rollout, focusing on high-performing locations first

**Action Plan:**
- Interview successful managers: What did they do differently?
- Identify underperforming location issues: Training? Signage? Customer demographics?
- Roll out to 10-15 additional locations, prioritizing similar profiles to successful shops

---

### Scenario B: OPTIMIZE & EXTEND PILOT ⚠️

**Threshold:** 2-3 locations meet success criteria (33-50%)

**Decision:** Platform shows promise but needs optimization before rollout

**Action Plan:**
- Extend pilot by 30 days to gather more data
- Implement optimization strategies:
  - Adjust Flash Sale timing based on successful location data
  - Revise notification messaging
  - Increase QR code visibility (larger signs, counter placement)
  - Additional manager training sessions
- Reevaluate after extended period

---

### Scenario C: PIVOT OR CANCEL ❌

**Threshold:** 0-1 locations meet success criteria (<17%)

**Decision:** Fundamental issues with platform or market fit

**Failure Indicators:**
- ❌ <5% increase in daily car count across all locations
- ❌ <10% Flash Sale redemption rate
- ❌ <50 signups per location
- ❌ Manager complaints about usability or complexity
- ❌ Technical issues causing significant downtime
- ❌ Customer complaints about spam or privacy concerns

**Action Plan:**
- Corporate retains source code license (asset value: $16,000)
- Conduct post-mortem analysis: Why did it fail?
- Options:
  - Pivot to simpler SMS-only system (no app)
  - Sell/license platform to non-competing automotive franchise
  - Pause and revisit in 12 months with adjusted strategy

---

### Success Probability Analysis

**Based on conservative assumptions:**
- **High likelihood (70%):** 4-6 locations succeed → PROCEED
- **Moderate likelihood (20%):** 2-3 locations succeed → OPTIMIZE
- **Low likelihood (10%):** 0-1 locations succeed → CANCEL

**Why 67% threshold makes sense:**
- Industry standard for pilot programs: 60-70% success rate indicates viability
- Accounts for expected variability in franchise operations
- Provides statistically significant sample while acknowledging real-world constraints
- Even if 2 locations fail, the 4 successful locations cover the Year 1 investment

**Financial Impact by Scenario:**
- **4 locations succeed:** $12,000/month revenue = $10,810/month net = 909% ROI
- **5 locations succeed:** $15,000/month revenue = $13,810/month net = 1,161% ROI
- **6 locations succeed:** $18,000/month revenue = $16,810/month net = 1,413% ROI

### Enterprise Rollout Plan (If Successful)

**Phase 1: Controlled Expansion (Months 4-6)**
- Add 10-15 locations
- Refine processes based on pilot learnings
- Hire additional support staff if needed

**Phase 2: Rapid Rollout (Months 7-12)**
- Add remaining Speedee locations
- Begin Grease Monkey integration
- Implement per-location SaaS pricing

**Phase 3: Optimization & Scale (Year 2+)**
- Advanced features (appointment booking, AI chatbot)
- Cross-franchise analytics and benchmarking
- Explore licensing to other automotive franchises

---

## Communication Plan

### Stakeholder Updates

**Weekly (During Development):**
- **To:** Primary franchise owner contact
- **Format:** Email with progress update and screenshots
- **Content:** What shipped this week, what's next, any blockers

**Bi-Weekly (During Pilot):**
- **To:** Corporate stakeholders
- **Format:** Email report with metrics dashboard
- **Content:** Signups, redemptions, revenue impact, manager feedback

**Monthly (During Pilot):**
- **To:** All stakeholders + pilot managers
- **Format:** Video call (30-45 minutes)
- **Content:** Deep dive on data, share best practices, Q&A

**Quarterly (Post-Pilot):**
- **To:** Executive team
- **Format:** In-person presentation
- **Content:** Strategic roadmap, ROI analysis, expansion recommendations

---

## Risk Management During Implementation

### Technical Risks

**Risk: API Downtime (NHTSA or OneSignal)**
- **Mitigation:** SMS notifications (if push fails), barcode works offline
- **Monitoring:** Uptime checks every 5 minutes
- **Response:** Alert developer within 15 minutes of outage

**Risk: Heroku Platform Issues**
- **Mitigation:** Daily backups, staging environment for testing
- **Monitoring:** Heroku status dashboard, error tracking
- **Response:** Rollback to previous version if deployment causes issues

**Risk: Data Loss or Corruption**
- **Mitigation:** Automated daily backups, point-in-time recovery
- **Testing:** Monthly restore test to verify backup integrity
- **Response:** Restore from backup (<30 minutes recovery time)

### Business Risks

**Risk: Low Customer Adoption**
- **Mitigation:** In-store signage, initial incentive ($10 in rewards points)
- **Monitoring:** Track signup rate daily
- **Response:** Increase incentive, test different messaging

**Risk: Manager Non-Adoption**
- **Mitigation:** Simple UI, thorough training, quick reference guide
- **Monitoring:** Track Flash Sales sent per location
- **Response:** Additional 1-on-1 training, identify pain points

**Risk: TCPA Complaint**
- **Mitigation:** Explicit opt-in, clear opt-out, consent logging
- **Monitoring:** Track opt-out rate, customer complaints
- **Response:** Immediate opt-out processing, legal consultation if needed

---

## Success Factors

**What Makes This Project Likely to Succeed:**

1. **Clear Problem Definition:** Idle bays = lost revenue (measurable)
2. **Simple Solution:** One button to fill bays (low complexity)
3. **Strong Stakeholder Buy-In:** Corporate already interested
4. **Realistic Timeline:** 9 weeks to MVP (achievable)
5. **Measurable ROI:** Car count and revenue are hard metrics
6. **Experienced Developer:** Mason has Rails expertise and AI assistance
7. **Proven Technology:** No experimental tools, battle-tested stack
8. **Flexibility:** Can adjust based on pilot feedback

---

## Post-Launch Support Commitment

**Months 1-3 (Pilot Phase):**
- **Availability:** Mon-Fri, 9 AM - 5 PM (email), emergency phone for critical issues
- **Response Time:** 24 hours for non-critical, 4 hours for critical
- **Included:** Bug fixes, minor tweaks, weekly reports, monthly calls

**Months 4-6 (Post-Pilot):**
- **Availability:** Same as pilot phase
- **Included:** Feature enhancements (within 20-hour monthly retainer), ongoing optimization

**Months 7-12 (Mature Product):**
- **Availability:** Transition to ticketing system if >20 locations
- **Included:** Proactive monitoring, quarterly roadmap planning

---

## Conclusion: Realistic, Achievable, Low-Risk

**This timeline is aggressive but achievable:**
- 9 weeks to MVP (45 business days)
- 13 weeks total to pilot results
- 24 weeks to rollout decision

**Every phase has clear deliverables and checkpoints.**
**Every risk has a mitigation strategy.**
**Every stakeholder has a communication touchpoint.**

**The MVP demonstration is a surgical strike against empty bays and budget weary customers.**

---

**Next Section:** Risk Analysis & Mitigation (comprehensive risk assessment)
