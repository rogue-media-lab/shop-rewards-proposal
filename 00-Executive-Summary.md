# Executive Summary

**Prepared for:** Speedee Oil Change & Auto Service Corporate
**Prepared by:** Mason Roberts, Rogue Media Lab
**Date:** November 2025
**Project:** Shop Rewards - Customer Loyalty & Bay Filling Platform
**Architecture:** Multi brand platform designed for your franchise portfolio

---

## The Problem

Speedee and Grease Monkey franchise locations are facing **substantial annual revenue loss** across the franchise. This concern is not targeted to one store or even the franchise but is a nationwide trend. It evolves from many factors. Some factors are difficult to control but I think I have identified one loss that can be effectively addressed. This loss is not due to poor service quality or inadequate pricing, rather it stems from a critical failure in customer acquisition and retention in an increasingly competitive market.

**The Competitive Reality:**

Even car washes have apps now. Coffee shops have apps. Fast food chains have apps. These apps aren't just digital business cards, they're revenue generating tools designed to drive customer behavior, build loyalty, and fill slow periods. The companies that get it right treat their apps as critical strategic assets, constantly improving them and reaping measurable returns.

**Meanwhile, some franchise locations have no or limited apps. No direct line to customers. No way to generate traffic on demand.**

**Core Issues:**
- **No Direct Customer Connection:** Without an app, you have no way to reach customers when you need them most
- **Low Customer Flow:** Shop overhead skyrockets when idle bays remain empty
- **Price War Environment:** Intense local competition with no effective differentiation strategy
- **Commodity Perception:** Automotive service has become a price-driven transaction rather than a relationship
- **Outdated Marketing Tools:** Current methods (POS reminders, discount cards, online coupons) fail to generate on-demand traffic

**Three critical questions:**
1. What is the condition of your app?
2. Have you seen these proposed features in any other apps in this industry?
3. Is this worth even trying?

**Every hour a bay sits empty, the store is actively losing money. Your competitors who have figured out mobile engagement are filling their bays while yours sit idle.**

---

## The Solution

**Shop Rewards** is a Progressive Web App (PWA) purpose built for automotive service franchises to solve two specific problems:

1. **Acquisition:** Fill idle bays on demand with time sensitive "Flash Sale" alerts sent directly to customers' phones
2. **Retention:** Convert price shoppers into loyal, returning customers through a gamified rewards program

**Multi-Brand Architecture for Your Portfolio:**
This platform is designed to support your entire franchise portfolio, both Speedee and Grease Monkey, with complete flexibility as you grow. Each brand operates independently with:
- Brand specific customization (logo, colors, terminology)
- Private customer database (zero data sharing between brands)
- Franchise-safe architecture (no POS integration required)

**What makes this different from generic loyalty software:**
This is purpose built for automotive service shops with one unique feature that doesn't exist in the market: **the ability for managers to push a button and fill their schedule within hours using on-demand flash sales.**

---

## How It Works

### For Shop Managers (The "Bay Filler")
When bays are empty at 2pm on a slow Tuesday:
1. Manager logs into admin dashboard
2. Clicks "Send Flash Sale" button
3. Creates offer: "50% off oil change - next 2 hours only"
4. Push notification sent instantly to all opted in customers
5. Customers arrive, bay fills, crew stays productive

### For Customers (The "Lure")
1. Sign up in 30 seconds with email (scan QR code at shop counter for instant signup)
2. Select your preferred shop location OR QR code auto-selects
3. Receive instant alerts on time-sensitive deals from YOUR shop
4. Earn "Points" on every dollar spent at YOUR shop
5. Track progress: "3 of 4 oil changes - one more for free!"
6. Redeem rewards for free or discounted services

### Unique Features
- **Location-Based Multi-Tenancy:** Customers choose their preferred shop location. Flash sales and rewards are shop-specific, creating dedicated customer bases per location while supporting multiple franchise brands
- **QR Code Instant Signup:** Each shop gets unique QR codes. Customer scans → Account created → Linked to that shop. Highest conversion rate for in store acquisition
- **Zero POS Integration:** Completely separate from franchise systems. No corporate agreement violations
- **Progressive Web App (PWA):** Installs like a native app with home screen icon and push notifications, but accessible from any device without App Store approval. This is NOT a website update, it's a dedicated app experience that enables the instant notification capability the flash sale feature requires
- **Three-Tier Admin Access:** Managers see one shop, Owners see multiple shops they own, Corporate sees all pilot locations

---

## MVP Feature Breakdown

### What You're Getting (Detailed)

#### Customer-Facing Features (The Mobile App)

**1. Quick Signup & Authentication**
- Email based signup (30 seconds or less)
- Verification code for security
- Shop selection during signup (enter zip code → see nearby shops)
- QR code option: Scan at shop counter → Auto-selects that shop → Skip to profile
- Optional profile information (name, phone, email, zip, birth month)
- **Status:** Solid ✅ (Standard authentication pattern with location selection)

**2. Home View (About)**
- Franchise brand prominent
- Store banner image becomes Flash Sale when active
- Points slider to quickly view points
- Store information, address, phone number, store hours
- Map of location

**3. Digital Coupon Wallet**
- View active coupons/flash sales from YOUR shop only
- See expiration times and terms
- "Redeem" button generates unique code for staff to verify
- Coupon history (used/expired)
- **Status:** Solid ✅ (Core feature, shop-scoped)

**4. Rewards Points Dashboard**
- Visual progress tracker ("3 of 4 oil changes completed at YOUR shop")
- Current point balance at YOUR shop
- Rewards catalog (what you can redeem for)
- Redemption history
- **Status:** Solid ✅ (Shop-scoped loyalty program)

**5. Push Notification System**
- Receive flash sale alerts from YOUR shop only (not all locations)
- **SMART CONTROLS** to prevent abuse:
  - **"Quiet Hours"**: Customer sets no-alert times (e.g., 10pm-8am)
  - **"Max Alerts Per Day"**: Default limit of 2 flash sales/day (prevents spam)
  - **"Urgent Only" Mode**: Only alerts for 40%+ discounts
  - **Full Opt-Out**: Available but requires confirmation ("You'll miss all deals")
- In-app notification history (never miss a deal)
- **Status:** Functional with optimization needed ⚙️ (Shop-scoped notifications)

**6. Profile & Settings**
- Update contact info
- Notification preferences (see #5 above)
- Privacy policy and terms access
- Delete account option (GDPR compliance)
- **Status:** Solid ✅ (Standard user management)

**7. Services Display (Valvoline-Style)**
* Owner creates master service list (CRUD interface)
* Manager selects which services their shop offers
* Customer sees service cards: icon, name, time estimate (no pricing)
* Examples: "Full-Service Oil Change ~ 15 mins", "Air Conditioning ~ 30-60 mins"
* Helps customers understand offerings before arrival
* **Status:** Solid ✅ (Inspired by Valvoline app design)

**8. Perks System (Service-Count Rewards)**
* Separate from points: Tracks service milestones ("3 of 4 oil changes")
* Two perk types: Service-count ("4th oil change free") + Points-threshold ("500 pts = $50 off brakes")
* Automatic progress tracking based on PO entries
* Visual progress bars show customer how close they are
* Manager awards perk at checkout (with PIN confirmation)
* **Status:** Solid ✅ (Dual loyalty system unique to automotive)

**9. Barcode Generation (POS Bridge)**
* Code 128 barcodes for all coupons, points redemptions, and perks
* Manager scans barcode at POS (discount applied automatically)
* Franchise-safe: No API integration required
* Dynamic amount barcodes for points ("AMT20" = $20 off)
* Customer shows barcode, manager scans, transaction complete
* **Status:** Functional ⚙️ (Requires POS configuration to recognize codes)

**10. Manager PIN Confirmation**
* 4-digit PIN security for all redemptions
* Prevents customer self-redemption fraud
* Audit trail: Logs which manager confirmed redemption
* PIN entry required before points/perks deducted
* Fast workflow: Scan barcode → Enter PIN → Complete
* **Status:** Solid ✅ (Security + accountability)


---

#### Manager/Admin Features (The Control Panel)

**1. Admin Dashboard (Shop Manager = ONE Shop)**
- Active customer count at THIS shop
- Flash sales sent today from THIS shop
- Redemption statistics for THIS shop
- Quick-action buttons for common tasks
- **Status:** Solid ✅ (Shop-scoped interface)

**2. Flash Sale "Bay-Filler" Tool (with Check-In)**
- One-click "Send Flash Sale" button
- Quick-create form:
  - Discount amount (%, $ off, or custom)
  - Service type (oil change, inspection, etc.)
  - Expiration time (1-4 hours)
  - Optional: Target specific customer segments
- Send to customers of THIS shop only (not all locations)
- **Check-In Feature:** If customer arrives during active flash alert, manager clicks "Check In" to reserve discount even if line is long. Checked-in customers can return later same day (doesn't extend to next day)
- **BUILT-IN SAFEGUARDS:**
  - Warning if >2 flash sales sent in one day
  - Cannot send between 9pm-7am (respects customer quiet hours)
  - Cannot combine with standing coupons or points
  - Preview: "This will reach ~250 customers at Speedee Main Street"
- **Status:** Functional with optimization needed ⚙️ (Shop-scoped feature)

**3. Customer Lookup & Management**
- Search by phone number, name, or email (only shows THIS shop's customers)
- Customer profile view (visits, points at THIS shop)
- View customer's notification preferences
- Quick redemption: "Use reward" button with PIN confirmation
- **Status:** Solid ✅ (Shop-scoped CRM functionality)

**3A. PO Transaction Workflow (Pain-Free Points Entry)**
- Manager searches customer (5 seconds)
- Selects service type from dropdown (Oil Change, Tire Rotation, etc.)
- Enters PO number + amount paid (minus tax)
- System auto-calculates points (10 pts per dollar)
- Preview shows: "Points to award: 100 pts ($100 × 10)"
- Shows perk progress: "Oil Changes: 2 → 3 of 4 ✅ (One more for free!)"
- Manager clicks "Add Points & Update Perks"
- Total time: ~30 seconds
- **Status:** Solid ✅ (Replaces manual point entry, tracks perks automatically)

**4. Standing Coupons (Owner-Created, Not Flash Sales)**
- **Owner creates** standing coupons (ongoing promos, not time-sensitive)
- Examples: "$7 off conventional oil", "10% military/senior discount", "$50/axle brake special"
- Available to all customers at that shop automatically
- Birthday coupons auto-generated when customer fills in birth month (optional field)
- Set start/end dates, track usage statistics
- **Manager cannot create** - only Owner/Corporate level
- **Status:** Solid ✅ (Distinct from flash alerts)

**5. Rewards Program Configuration (Owner/Corporate Only)**
- Define reward tiers ("3 oil changes = 1 free")
- Set point values ("$1 spent = 10 point")
- Create reward catalog
- **Status:** Solid ✅ (One-time setup, rarely changed)

---

#### Owner/Corporate Features (Multi-Shop Management)

**1. Owner Dashboard (Owner = MULTIPLE Shops)**
- View aggregate metrics across all owned shops
- Compare performance between shops (Speedee vs. Grease Monkey)
- Shop selector: View one shop or all shops
- Cannot send flash sales (delegates to managers)
- **Status:** Solid ✅ (Multi-shop analytics)

**2. Manager Account Creation**
- Create manager accounts for shops
- QR Code for sign up generated when shop is created
- Assign managers to specific shops
- Disable/revoke access as needed
- **Status:** Solid ✅ (Shop assignment system)

**3. Corporate Analytics (Pilot Program)**
- View ALL pilot shops across ALL owners
- Read-only access for pilot evaluation
- Used for pilot analytics and stakeholder reporting
- **Status:** Solid ✅ (Cross-franchise visibility)

---

### Features Excluded from MVP (Available Post-Pilot)

These features are deliberately excluded from the pilot to maintain focus on the core revenue recovery problem:

- ❌ **Cross-shop rewards** (earn points at one Speedee location, redeem at another)
  - Post-MVP enhancement: 2-week development effort
  - Architecture already supports this feature
- ❌ **VIN Scanner** (No need for Garage feature for MVP)
- ❌ **Appointment scheduling** (use existing systems)
- ❌ **Service history from POS** (manual entry only for next phase)
- ❌ **Payment processing** (pay in-store as usual)
- ❌ **AI Chatbot assistance** (Post-pilot feature)
- ❌ **Automated maintenance reminders** (Post-pilot feature)
- ❌ **In-app messaging** between customer and shop
- ❌ **Online estimate requests**
- ❌ **Service Advisor Assistant** (quickly and easily help non English speaking customers)

**Why This Approach?**
The MVP laser-focuses on solving ONE problem: filling idle bays with location-specific flash sales. It should put the value of car maintenance in the customers hand. Feature creep kills pilots. We prove the core hypothesis first (revenue recovery through on-demand traffic generation), then expand based on what we learn from the pilot.

---

## Business Impact (ROI)

### Conservative 90-Day Pilot Scenario (6 Locations)

**Pilot Composition:**
- **6 shops:** 3 Speedee + 3 Grease Monkey locations
- Purpose: Validate that platform works effectively for both franchise brands
- This validates the multi-franchise architecture and proves cross-brand scalability

**Assumptions:**
- Each shop fills **1 idle bay per day** using Flash Sales
- Average service value: **$100** (oil change, inspection, small repairs)
- 30 days per month

**Monthly Revenue Recovery:**
- 6 locations × 1 bay/day × 30 days × $100 = **$18,000/month**

**Monthly Program Cost:**
- Platform operational costs: $390 (includes E&O insurance)
- Maintenance & support: $800
- **Total: $1,190/month**

**Net Monthly Gain:** $16,810
**ROI:** 1,413% (monthly return)
**Break-Even:** 2.0 days
**Year 1 Net Gain:** $185,720 (after $30,280 total investment)

**This pays for itself in the first week.**

---

## Investment Summary

### Developer Availability

**Mason Roberts is available to begin development immediately upon contract approval.** Full-time focus will be dedicated to this project during the 9-week MVP development phase with no competing client commitments. Mason will pause automotive technician work to ensure timely delivery and provide dedicated availability for stakeholder communication and support during the critical development period.

**Developer Background:** Mason is a self-taught Rails developer with 5 years of experience building Progressive Web Apps. He currently works as an automotive technician at Speedee locations, providing direct insight into the operational challenges this platform addresses. Portfolio includes Rails 8 PWAs with authentication systems, multi-tenant applications, and AWS S3 integration. Detailed portfolio, code samples, and prototype offer available in Conclusion section (Q2).

---

### MVP Development (One-Time Payment)

**Cost: $16,000**

This covers:
- Complete app build (customer PWA + admin dashboard + owner dashboard)
- All features: Flash Sales, Rewards Program, Services Display, Perks System, Barcode Generation, Customer Lookup
- Deployment to production servers
- Initial training and documentation
- You own the license to use this across Speedee and Grease Monkey franchises

**Payment Structure (Milestone-Based):**
- Milestone 1: 25% upon contract signing: $4,000
- Milestone 2: 25% at Week 3 checkpoint (Phases 1-3 complete): $4,000
- Milestone 3: 50% upon MVP delivery (end of Week 9): $8,000

**Optional Add-On:**
- **Branding Asset Preparation: $400** (if franchise does not have digital logo files or brand color codes ready)
  - Extract logos from existing print materials or websites
  - Convert raster formats (JPG/PNG) to vector (SVG) if needed
  - Contract graphic designer for asset recreation if necessary (contractor fees included)
  - Deliver franchise-ready logo files and color palette

---

### 90-Day Pilot Program

**Additional Cost: $3,570** (3 months of service)

This covers:

**Hosting & Operations ($390/month):**
- Heroku production + staging servers
- PostgreSQL database
- Push notification service (OneSignal)
- SMS authentication (Twilio)
- Domain, SSL, automated backups
- **E&O Professional Liability Insurance**

**Maintenance & Support ($800/month = 20 hours during pilot):**
- Bug fixes and emergency support (Response: 4 hrs critical, 24 hrs non-critical)
- Feature tweaks based on pilot feedback
- Weekly check-ins during pilot
- Performance monitoring and security updates
- Tech support for managers and customers

**Total 90-Day Pilot Investment: $19,570**
- Development: $16,000
- Pilot operations: $3,570 (3 months × $1,190/month)

---

### After the Pilot (If Successful)

**Monthly Subscription: $1,190/month**
- Same hosting and support services continue (13 hours/month support)
- No additional development fees
- Month-to-month or annual contract available

**Total Year 1 (if continuing full year):**
- Development: $16,000 (one-time)
- Pilot (3 months): $3,570
- Months 4-12 (9 months): $10,710
- **Year 1 Total: $30,280**

**Year 2+ Annual Cost:** $14,280/year ($1,190/month × 12)

---

### Decision Point at Day 90

**Option A: Continue**
- Keep paying $1,190/month
- App stays live and supported
- Optimize based on lessons learned from pilot

**Option B: Pause**
- Stop monthly payments
- App goes offline
- Total investment: $19,570
- Can reactivate later at $1,190/month + $500 reactivation

**Option C: Enterprise Rollout**
- Negotiate per-location pricing for full deployment
- Typical: $50-100/location/month for 10+ locations
- Dedicated support and custom feature development

---

### What You Get
- Fully functional mobile PWA with customer and admin interfaces
- Flash Sale system with push notifications
- Rewards/points program with redemption tracking
- Store information at a glance
- Coupons at a glance, easily used with app
- Services at a glance, easily know what the shop can do
- Customer lookup and point assignment tools
- TCPA-compliant legal framework
- 90-day pilot support with dedicated developer access
- Full flexibility to evaluate and decide at the 90-day mark

---

## Competitive Position

| Solution | Build Cost | Monthly Cost | On-Demand Bay Filling | Multi-Franchise |
|---|---|---|---|---|
| Generic SaaS (Kangaroo, etc.) | $0-1,000 | $299/location | ❌ No | ❌ No |
| Car Wash Apps (Rinsed, etc.) | $0 | $29-99/location | ❌ General promos only | ✅ Yes |
| Custom Agency Build | $150,000-500,000 | $15,000+ | ❌ Not included | ⚠️ Requires rebuild |
| SMS Marketing Only | $0 | $100-300 | ❌ No app | ❌ No |
| **Shop Rewards** | **$16,000** | **$1,190 total** | ✅ **UNIQUE FEATURE** | ✅ **Built-in** |

**What Makes This Unique:**

Research shows NO other automotive service platform offers this combination:
- **Flash Sale Bay Filler:** Real-time, manager-controlled flash sales to fill idle bays on demand (not generic promotions)
- **Services Display:** Valvoline-style service cards showing what you offer (time estimates, no pricing pressure)
- **Dual Loyalty System:** Points (dollar-based) + Perks (service-count rewards) working together
- **Barcode Bridge:** Franchise-safe POS integration via scannable coupons (no API required). Uses current barcode functionality
- **Multi-Brand Architecture:** One platform serves both Speedee and Grease Monkey

**You're getting a purpose-built automotive service platform that doesn't exist in the market.**

**Plus:** The multi-brand architecture means you can deploy this across both Speedee and Grease Monkey locations, and scale to additional locations as your portfolio grows, all without rebuilding.

---

## Multi-Brand Architecture & Scalability

**Platform Design Philosophy:**

Shop Rewards is built with a **multi-brand architecture** from the ground up. This isn't generic software we're adapting, this is purpose built for automotive service franchise portfolios like yours, with the technical flexibility to handle multiple brands efficiently.

**How It Works:**

**For Your Portfolio (Speedee & Grease Monkey):**
- Deploy to both brands simultaneously or separately
- Each brand operates **completely independently**
- Brand specific customization: logo, colors, terminology, messaging
- **Zero data sharing** between brands, complete data firewall
- Same powerful features, different brand identity

**Technical Implementation:**
- **Brand Isolation:** Database level separation ensures Speedee customers never see Grease Monkey data (and vice versa)
- **Brand Customization:** Dynamic theming allows each brand to maintain its unique identity
- **Centralized Management:** Optional corporate dashboard for cross brand analytics
- **Cost Efficiency:** Shared infrastructure = lower per location costs than building separate apps

**Strategic Benefits:**

1. **Lower Per Location Cost:** Platform costs spread across all your locations
2. **Faster Deployment:** Build once, deploy to both brands
3. **Future-Proof:** Add new locations or expand into new markets without rebuilding
4. **Proprietary Advantage:** A custom tool built specifically for your franchise portfolio

**Cost Comparison:**

| Approach                | Build Cost | Monthly Cost | Add Locations/Brands |
| ----------------------- | ---------- | ------------ | -------------------- |
| Separate apps per brand | $20,000+   | $2,200+      | Rebuild from scratch |
| Multi-brand platform    | $16,000    | $1,190       | Deploy in days       |

**Franchise Compliance:**
- Brand firewall option: Use neutral branding ("Auto Rewards powered by [Your Brand]")
- Zero POS integration: Complete independence from franchise corporate systems
- Data sovereignty: Each brand owns and controls its customer data

---

## Why This Works

1. **Unique Feature Combination:** Flash sale bay filling  + Coupons + Services display + Dual loyalty system + Barcode bridge
2. **Proven Hypothesis:** Customers respond to time sensitive, high value offers (50% off creates urgency)
3. **Behavioral Psychology:** Gamification (collecting points + perks) drives repeat visits
4. **Franchise Safe:** Barcode bridge eliminates POS integration risk, no corporate compliance concerns
5. **Speed to Market:** 9 weeks to launch vs. 10+ months for agency builds
6. **Scalable Architecture:** Multi brand design supports your entire portfolio and future growth
7. **Flexible & Adaptive:** Direct developer access means features adapt to real world usage
8. **Access:** Built on the web. Access from anywhere on any device

*If customers are looking for value. If customers are shopping. If customers are asking for some relief. Then why not put all the options in the palm of their hands. Make it harder for them to keep shopping.*

---

## Pilot Timeline

- **Week 0:** Proposal approval, contract signed
- **Weeks 1-9:** MVP development (Admin + Customer features)
- **Week 10:** Deployment to 6 pilot locations (3 Speedee, 3 Grease Monkey)
- **Week 11:** Pilot launch with manager training and customer onboarding
- **Weeks 11-23:** 90 day pilot program with weekly metrics reporting
- **Week 24:** Results review, decision on enterprise rollout

**MVP Delivery:** End of Week 9 (stakeholder demonstration upon completion)

*This timeline will vary. Consider that most customers that opt-in will do so at the store, upon getting an oil change. It will be another 3 to 6 months before they need the next. The app should evaluate this before pushing the flash sale.*

---

## Success Metrics (90-Day Pilot)

**Primary KPIs (Key Performance Indicator):**
- Daily car count increase per location
- Flash Sale redemption rate (target: 15-25%)
- Customer sign-up rate (target: 100+ users/location)
- Average revenue per Flash Sale event

**Secondary KPIs:**
- Customer return rate (loyalty indicator)
- Rewards redemption rate
- Manager usage frequency (adoption indicator)
- Customer satisfaction (post visit surveys)

**Decision Criteria for Enterprise Rollout:**
- Minimum 10% increase in daily car count across pilot locations
- Positive ROI (Return on Investment) within 30 days
- Manager satisfaction score >4/5
- Customer sign-up rate >20% of total customers served

---

## Risk Mitigation

### Franchise Compliance Risk
**Concern:** Will using this app violate Speedee or Grease Monkey franchise agreements?

**Mitigation:**
- Zero POS integration: completely independent system
- Optional brand firewall: Use neutral branding ("Auto Rewards" or similar)
- Proprietary customer database separate from franchise systems
- No corporate data access or reporting required

### Multi-Brand Data Risk
**Concern:** Will customer data be shared between Speedee and Grease Monkey locations?

**Mitigation:**
- **Brand Isolation:** Database level separation ensures zero data crossover
- **Brand Firewalls:** Each brand operates as completely separate entity
- **Audit Trail:** All data access logged and auditable
- **Privacy Compliance:** Exceeds GDPR and franchise agreement requirements

### Legal/TCPA Compliance
**Concern:** Are we legally allowed to send marketing text messages?

**Mitigation:**
- Explicit opt-in checkbox at signup (TCPA requirement)
- Clear privacy policy and terms of service
- Smart notification controls (not full opt-out by default):
  - Quiet hours (customer defined)
  - Frequency limits (max 2 flash sales/day default)
  - Discount threshold filter ("only alert me for 40%+ off")
- SMS opt-out mechanism: "Reply STOP to end" (required by law)
- All marketing messages include unsubscribe instructions

**Addressing the Paradox:**
If everyone turns off notifications, the flash sale feature doesn't work. The solution:
- **Default state:** All notifications ON with smart limits (not overwhelming)
- **Full opt-out requires confirmation:** "You'll miss all flash sale deals. Are you sure?"
- **Incentive to stay opted-in:** "Flash sale members saved an average of $240 last quarter"
- **Re-engagement campaigns:** Monthly "You're missing out" message to opted-out users (with re-opt-in link)

The goal is to make notifications valuable enough that customers WANT them, not turn them off.

### Technical Risk
**Concern:** What if the platform crashes or loses data?

**Mitigation:**
- Proven technology stack (Rails 8, PostgreSQL, Heroku)
- 99.9% uptime guarantee
- Automated daily backups with 30-day retention
- Error monitoring with 24-hour response time
- Staging environment for testing before production updates

### Adoption Risk
**Concern:** Will managers actually use this, or will it sit unused?

**Mitigation:**
- In-person manager training at each pilot location
- Simple 3-click workflow for Flash Sales ("stupid simple by design")
- Customer onboarding incentive ("Sign up today, get $10 in Points")
- Weekly check-ins during pilot to address friction points
- Success stories shared across locations to build momentum

---

## Next Steps

1. **Review Proposal:** Corporate stakeholders review full technical and financial documentation
2. **Q&A Session:** Address questions on features, costs, timeline, and risks
3. **Pilot Agreement:** Finalize contract for 6 location pilot program (3 Speedee + 3 Grease Monkey)
4. **Development Start:** Begin 9-week MVP build immediately upon approval (Day 0)
5. **MVP Delivery:** Stakeholder demonstration at end of Week 9

---

## Honest Answers to Skeptical Questions

### "Don't we already have websites? Why not just update speedeeoil.com and greasemonkeyauto.com instead of building a separate app?"

**Short answer:** Push notifications. That's the difference that matters.

**The core problem:**
Your existing websites can't send **instant push notifications** to customers' phones. Without that capability, the flash sale "bay-filler" feature doesn't work. A customer visiting a website once a month won't see your "50% off for the next 2 hours" deal in time.

**What websites CAN do:**
- Display coupons (but customers have to remember to check)
- Email signup (emails go to spam or get ignored)
- SMS signup (requires separate Twilio service = same cost as this app)
- Show loyalty program info (but customers won't visit daily to check)

**What a PWA app DOES differently:**

1. **Push Notifications to Lock Screen**
   - Manager sends flash sale at 2pm → Notification appears on customer's phone immediately
   - Same experience as getting a text message, but within your app
   - This is the ONLY way to generate on-demand traffic within hours

2. **Home Screen Presence**
   - App icon sits between Facebook and Instagram
   - One tap to open (not "remember URL, open browser, type address")
   - Visible reminder: "I have rewards points at Speedee"

3. **Dedicated Experience**
   - Opens fullscreen (no browser UI)
   - Feels like a native app (not a website)
   - User can't accidentally navigate away or close a tab

4. **User Commitment Signal**
   - Installing an app = higher engagement intent than bookmarking a website
   - 10x higher return visit rate for PWAs vs. mobile websites

**Could you add push notifications to your existing websites?**

Technically yes, but:
- Requires complete website rebuild as PWA (same development cost)
- Browser-based push notifications have lower opt-in rates (users ignore "allow notifications" popups)
- Users don't "install" a website, it stays in the browser, not on home screen
- Corporate franchise websites are often controlled/hosted by corporate, not you (can't modify freely)

**The bottom line:**
If you want customers to respond to a flash sale within 2 hours, you need push notifications sent directly to their phone. A website bookmark doesn't accomplish that. This PWA functions like a native app while being accessible from the web, best of both worlds.

---

### "Won't customers just turn off notifications and make this useless?"

**Short answer:** Not if we design it right.

**The strategy:**
1. **Make notifications valuable, not annoying.** Limit to 2/day max by default. Only send genuinely good deals (30%+ off).
2. **Smart controls, not kill switches.** Give customers "Quiet Hours" and "Discount Threshold" filters instead of binary on/off.
3. **Social proof.** Show opted-in customers they saved $X this quarter. FOMO keeps people subscribed.
4. **Behavioral nudges.** Full opt-out requires confirmation and shows what they're missing.

**The pilot will test this.** If opt-out rates are too high, we adjust incentives and UX. This is why the 90-day pilot includes weekly check-ins, we can iterate based on real behavior.

---

### "What if managers abuse the flash sale button and spam customers?"

**Short answer:** We build guardrails into the system.

**Built-in safeguards:**
1. **Frequency limits:** Admin dashboard warns if >2 flash sales sent in one day
2. **Time restrictions:** Cannot send flash sales between 9pm-7am (respects customer sleep)
3. **Preview before send:** Shows "This will reach 250 customers" so managers think twice
4. **Usage analytics:** Corporate dashboard shows which locations are overusing (if we build that)

**Manager training during pilot week will emphasize:** "Less is more. One well timed 50% off deal fills bays. Five mediocre deals annoy customers."

---

### "What if this cannibalizes full-price customers?"

**Short answer:** That's not how idle bays work.

**The logic:**
- Flash sales only go out when bays are EMPTY
- Empty bay = $0 revenue. Flash sale customer at 50% off = $50 revenue.
- Full-price customers weren't coming in anyway (that's why the bay is empty)
- Over time, flash sale customers become regular customers (rewards program hooks them)

**The risk:** A customer who was about to come in at full price sees the flash sale and delays. **The mitigation:** Flash sales are time-limited (2 hours) and require immediate action. If they're delaying, they weren't coming in today anyway.

---

### "What if we invest $19,570 and it doesn't work?"

**Short answer:** The pilot is designed to answer that question in 90 days.

**Decision criteria at Day 90:**
- Did daily car count increase by 10%+ at pilot locations? (Yes/No)
- Did we achieve positive ROI within 30 days? (Yes/No)
- Do managers use it regularly (not just once)? (Yes/No)
- Did at least 20% of customers sign up? (Yes/No)

**If the answer to any of these is "No," you stop paying the $1,190/month and walk away.** Total investment: $19,570. That's 3.3 weeks of the revenue you're currently losing to idle bays.

---

## The Bottom Line

**For a $19,570 pilot investment (or $30,280 for a full year), you can potentially recover $18,000+/month in lost revenue.**

Mobile apps have become essential infrastructure for service businesses. They're not marketing gimmicks, they're revenue-generating assets. The companies that have figured this out are prosperous while others struggle.

**This platform gives you something that doesn't exist in the market: the ability to push a button and fill your schedule within hours.** Research shows no existing automotive service app offers true on-demand flash sale bay-filling functionality.

This is not a marketing experiment, it's a surgical tool designed to solve the idle bay problem and build customer loyalty in a commodity market.

**Multi-Brand Strategic Advantage:**
You're not just getting an app for Speedee or Grease Monkey. You're getting a platform built to support your entire franchise portfolio. As you add locations or expand into new markets, this platform scales with you. No rebuild required.

**The math is simple:**
- Pilot breaks even in 3.3 days
- Year 1 net gain: $185,720 (after all costs)
- Every idle bay hour you fill is pure profit recovery

**The question isn't whether this will work. The question is: How soon can we start?**

---

**Contact:**
Mason Roberts
Rogue Media Lab
email: rogue.media.lab@gmail.com
mobile: (803) 524-8988

---

*Full technical specifications, feature documentation, cost breakdowns, and implementation plans are included in the following sections of this proposal.*
