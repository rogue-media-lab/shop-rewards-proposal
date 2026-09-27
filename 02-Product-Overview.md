# Product Overview

**Document:** Shop Rewards Product Overview & Features
**Project:** Proprietary Customer Loyalty & Bay-Filling Platform
**Date:** November 2025

---

## Product Vision

**Shop Rewards is a mobile first Progressive Web App (PWA) designed to solve two critical problems for automotive service franchises:**

1. **Immediate Traffic Generation:** Enable shop managers to fill idle bays on demand with time sensitive flash sale alerts
2. **Customer Loyalty:** Transform one time price shoppers into repeat customers through gamified rewards

This is not a generic loyalty platform adapted for automotive, it's purpose built from the ground up to address the unique operational challenges of quick service oil change and maintenance franchises.

---

## Core Product Philosophy

### Design Principles

**1. Speed Over Perfection**
- Manager creates and sends a Flash Sale in under 60 seconds
- Customer signs up in under 30 seconds
- No training manual required if it needs explanation, it's too complex

**2. Mobile-First, Always**
- Every feature designed for smartphone use
- Large touch targets, minimal text entry
- Works on 3G connections (many shops have poor cellular signal)

**3. Franchise-Safe Architecture**
- Zero integration with POS systems
- Separate customer database (no corporate data access)
- Brand agnostic design (works for Speedee, Grease Monkey, or future brands)

**4. Privacy & Compliance First**
- TCPA compliant opt in process
- Clear privacy policy and terms of service
- Customer data stays with franchise, not sold to third parties

---

## Product Architecture

### What is a Progressive Web App (PWA)?

A PWA is a website that **looks and feels like a mobile app** without requiring download from the App Store or Google Play.

**Benefits:**
- **No app store approval:** Launch updates instantly, no waiting for Apple/Google review
- **No download friction:** Customer adds to home screen in one tap
- **Lower cost:** Single codebase works on iPhone, Android, and desktop
- **Always up-to-date:** Changes deploy immediately, no "please update your app" messages
- **Smaller file size:** Loads faster than native apps, uses less phone storage

**User Experience:**
1. Customer visits website on phone
2. Browser prompts: "Add Shop Rewards to Home Screen?"
3. Icon appears on phone like a regular app
4. Opens in full screen mode, no browser chrome
5. Works offline for viewing rewards (syncs when connected)

---

## User Roles & Workflows

### Role 1: Customer (The Driver)

**Primary Jobs to Be Done:**
- "I want to know about deals before I need service"
- "I want to earn rewards for being a loyal customer"
- "I don't want to manually type in my car's info"
- "I want to track my service history in one place"

**Customer Journey:**

**Sign-Up (30 seconds):**
1. Visit shop website or scan QR code on counter (QR code auto-selects shop, skip to step 4)
2. Enter phone number, name, and create password
3. Optional: Enter birth month (for birthday rewards)
4. Enter zip code → See nearby shops (e.g., "Speedee Main Street - 2.3 miles")
5. Select preferred shop location
6. Check TCPA opt-in box ("I agree to receive alerts from [Shop Name]")
7. Account created → Branding adapts to shop's franchise → Profile page loads

**View Services Available:**
1. Tap "Services" tab
2. See list of services with icons and time estimates
3. Example: "Full-Service Oil Change ~ 15 mins", "Air Conditioning ~ 30-60 mins"
4. Browse what shop offers before deciding to visit

**Receive Flash Sale:**
1. Push notification appears: "🚨 Flash Sale! 50% off oil change - next 2 hours"
2. Tap notification → App opens to Coupon Wallet
3. See coupon with countdown timer: "1:47:23 remaining"
4. Drive to shop, show coupon to service advisor

**Redeem Coupon (with Barcode & PIN):**
1. Service advisor: "Are you using a coupon today?"
2. Customer taps coupon → Full-screen barcode appears
3. Manager scans barcode at POS (discount applied)
4. Manager enters 4-digit PIN in app to confirm
5. Coupon marked as used, customer gets discounted service

**Earn Points (Manager Entry):**
1. After service, manager searches customer by phone
2. Selects service type from dropdown (e.g., "Oil Change")
3. Enters PO number and amount paid (minus tax)
4. System shows preview: "Points to award: 100 pts ($100 × 10)"
5. Shows perk progress: "Oil Changes: 2 → 3 of 4 ✅"
6. Manager clicks "Add Points & Update Perks"
7. Customer receives notification: "You earned 100 points! 🎉"

**Track Rewards & Perks:**
1. Customer opens app → See points balance: "250 points ($20 cash back value)"
2. See perk progress: "2 of 3 oil changes complete"
3. Visual progress bar shows how close to next reward
4. Third oil change: "Congrats! Free oil change unlocked 🎉"

---

### Role 2: Shop Manager (The Bay-Filler)

**Scope:** Manages ONE shop location

**Primary Jobs to Be Done:**
- "I have empty bays at MY shop and idle techs, I need cars NOW"
- "I want to reward MY loyal customers without manually tracking punch cards"
- "I need to see who's earning points at MY location"

**Manager Portal:** `/manager` (separate login from customer app)

**Access Control:**
- Can only view customers who signed up for their assigned shop
- Can only send flash sales to their shop's customers
- Dashboard shows metrics only for their shop

**Manager Workflows:**

**Send Flash Sale (Under 60 seconds):**
1. Log into `/manager` dashboard (phone or tablet)
2. Click big "Send Flash Sale" button
3. Fill out simple form:
   - Service: "Oil Change"
   - Discount: "50% off"
   - Duration: "2 hours"
   - (Optional) Custom message
4. Click "Send Now"
5. Push notification sent to opted-in customers of THIS shop only
6. Dashboard shows: "Flash Sale sent to 487 customers at Speedee Main Street at 2:15 PM"

**Customer Lookup (Search by phone):**
1. Customer arrives: "I'm here for the 50% off oil change"
2. Manager searches: "555-0123"
3. Customer profile loads:
   - Name: "Sarah Johnson"
   - Vehicle: "2019 Honda CR-V"
   - Rewards Points: 250
   - Active coupons: "50% Oil Change"
4. Tap "Redeem Coupon" → Coupon marked as used

**Add Reward Points (After service):**
1. Invoice total: $125
2. Manager opens customer profile
3. Taps "Add Points"
4. System calculates: $125 × 8% = 10 points (auto-populated)
5. Tap "Confirm" → Customer gets notification

**View Dashboard Stats:**
- Total customers signed up
- Active Flash Sales
- Redemptions today / this week / this month
- Top customers by points earned
- Customer growth chart

---

### Role 3: Franchise Owner (Multi-Shop Manager)

**Scope:** Manages MULTIPLE shop locations they own

**Primary Jobs to Be Done:**
- "I want to see ROI across ALL my locations"
- "I need to compare performance between my shops"
- "I want to create manager accounts for my staff"
- "I need to configure reward programs (e.g., 3 oil changes = 1 free)"

**Owner Portal:** `/owner` (separate login, elevated privileges)

**Access Control:**
- Can view MULTIPLE shops assigned to them
- Can see aggregate metrics across all owned shops
- Can compare performance (Speedee vs. Grease Monkey, or location A vs. location B)
- Cannot send flash sales directly (delegates to shop managers)
- Can create and manage shop manager accounts

**Owner Dashboard Features:**

**Multi-Shop Metrics View:**
```
Your Shops Dashboard

Speedee Locations (2 shops)
├── Total Customers: 247
├── Flash Sales This Week: 8
├── Redemptions: 45
└── Locations:
    ├── Speedee Main St: 125 customers, $12,500 revenue recovery
    └── Speedee Downtown: 122 customers, $11,800 revenue recovery

Grease Monkey Locations (1 shop)
├── Total Customers: 89
├── Flash Sales This Week: 3
├── Redemptions: 12
└── Locations:
    └── Grease Monkey West: 89 customers, $4,200 revenue recovery

Total Portfolio: 336 customers, $28,500 revenue recovery this month
```

**Manager Account Creation:**
- Create new manager accounts for shops
- Assign managers to specific shops via shop_assignments
- Disable/revoke access as needed

**Reward Program Configuration:**
- Set reward program rules for shops
- Download CSV reports for accounting/analysis
- View legal compliance status (TCPA opt-in rates)

---

## Feature Breakdown: MVP (Phase 1)

### Module 1: Customer-Facing Features

| Feature ID | Feature Name | Description | User Benefit |
|---|---|---|---|
| **PWA-101** | Phone-Based Authentication | Sign up with phone number, name, password (email optional) | Fast signup, mobile-first UX |
| **PWA-102** | Shop Selection | Enter zip code → See nearby shops → Select preferred location | Choose your shop, receive location-specific offers |
| **PWA-103** | QR Code Signup | Scan QR code at shop counter → Auto-select that shop → Complete signup | Fastest signup path (bypasses shop selection) |
| **PWA-104** | Services Display | View shop services with icons and time estimates (Valvoline-style) | Understand what shop offers before visit |
| **PWA-105** | Coupon Wallet (Barcode) | View active coupons with scannable Code 128 barcodes | Show barcode at checkout, POS applies discount |
| **PWA-106** | Standing Coupons | View owner-created ongoing promos ($7 off oil, military discount, etc.) | Access standard deals anytime |
| **PWA-107** | Birthday Rewards | Auto-generated coupon on birth month (if provided) | Special birthday discount |
| **PWA-108** | Push Notifications | Receive instant alerts when YOUR shop sends Flash Sale | Real-time awareness of time-sensitive offers |
| **PWA-109** | Rewards Dashboard (Dual Loyalty) | View points balance AND perks progress (e.g., "2 of 3 oil changes") | Two ways to earn rewards |
| **PWA-110** | Points Redemption (with Barcode) | Tap "Redeem Points" → Generate barcode for dollar amount → Manager scans | Convert points to cash-off discount |
| **PWA-111** | Redemption History | See past coupons used and rewards redeemed | Transparency builds trust |
| **PWA-112** | Profile Management | Update name, phone, password, birth month | Customer control over account |

---

### Module 2: Admin (Shop Manager) Features

| Feature ID | Feature Name | Description | Manager Benefit |
|---|---|---|---|
| **ADM-101** | Admin Authentication (with PIN) | Separate login for shop staff + 4-digit PIN for redemptions | Secure, role-separated access with fraud prevention |
| **ADM-102** | "Bay-Filler" Flash Sale Button | Create and send time-sensitive offers in <60 seconds | Fill idle bays on-demand |
| **ADM-103** | Flash Alert Check-In | "Check In" customer who arrives during active flash alert | Reserve discount even if line is long, customer can return same day |
| **ADM-104** | Customer Lookup | Search by phone number or name (shop-scoped only) | Fast access during checkout |
| **ADM-105** | PO Transaction Workflow | Enter PO, service type, amount paid → Auto-calculate points + track perks | Pain-free points entry, ~30 seconds |
| **ADM-106** | Barcode Scanning & PIN Confirmation | Scan customer barcode at POS → Enter PIN to confirm | Secure redemption with audit trail |
| **ADM-107** | Coupon/Perk Redemption | Mark coupons/perks as "used" with barcode + PIN | Track which offers are working |
| **ADM-108** | Dashboard Analytics | See customer count, redemptions, growth metrics | Data-driven decision making |
| **ADM-109** | Active Flash Sales View | See which offers are currently live | Avoid accidentally sending duplicate offers |
| **ADM-110** | Services Assignment | Select which services this shop offers from owner's master list | Customize shop offerings |

---

### Module 3: Owner (Franchise-Level) Features

| Feature ID | Feature Name | Description | Owner Benefit |
|---|---|---|---|
| **OWN-101** | Services Master List (CRUD) | Create/edit services catalog (Oil Change, Tire Rotation, etc.) | One-time setup, managers select from list |
| **OWN-102** | Standing Coupons Creation | Create ongoing promotions ($7 off oil, military discount, brake special) | Standard offers available to all customers |
| **OWN-103** | Reward Program Builder | Define perk rules ("3 oil changes = 1 free") + set points percentage | Customize incentives per location/brand |
| **OWN-104** | Multi-Location Dashboard | Aggregate stats across all shops | Portfolio-level visibility |
| **OWN-105** | User Management | Create/disable shop manager accounts | Control access, onboard new staff |
| **OWN-106** | Export Reports | Download CSV of redemptions, signups, revenue impact | Accounting and analysis |

---

### Module 4: Legal & Compliance

| Feature ID | Feature Name | Description | Compliance Benefit |
|---|---|---|---|
| **LEG-101** | TCPA Opt-In Checkbox | Required checkbox at signup: "I agree to receive marketing texts" | Legal protection under TCPA law |
| **LEG-102** | SMS Opt-Out | Every notification includes "Reply STOP to end" | Required by TCPA, customer goodwill |
| **LEG-103** | Terms of Service | Clear legal terms displayed before signup | Liability protection |
| **LEG-104** | Privacy Policy | Explains data collection, storage, and usage | GDPR/CCPA alignment, transparency |
| **LEG-105** | Consent Timestamp Logging | Store date/time customer agreed to receive messages | Legal defense in case of complaint |

---

## Unique Differentiators

### 1. Barcode POS Bridge (Franchise-Safe Integration)

**How It Works:**
- Customer taps coupon/points redemption → Full-screen Code 128 barcode appears
- Manager scans barcode at POS (same as scanning physical coupon)
- POS recognizes barcode and applies discount automatically
- Manager enters 4-digit PIN in app to confirm
- Transaction logged with audit trail (who, when, amount)

**Why This Matters:**
- **Zero API integration:** No corporate IT approval required
- **Zero POS modification:** Works with existing Sage POS setup
- **Franchise-safe:** Uses same method as paper coupons (scan & apply)
- **Fraud prevention:** PIN confirmation prevents customer self-redemption
- **Audit trail:** Every redemption logged with manager ID

**Competitive Advantage:**
No off-the-shelf loyalty platform offers barcode-based POS integration. This is the bridge between modern app and legacy POS systems.

---

### 2. Dual Loyalty System (Points + Perks)

**How It Works:**
- **Points (Dollar-Based):** Customer earns 10 points per $1 spent (8% cash back value)
- **Perks (Service-Count):** Customer tracks progress toward service milestones ("3 of 4 oil changes")
- Both systems run in parallel, both visible in app
- Manager entry workflow tracks both automatically via PO transaction

**Why This Matters:**
- **Points** appeal to customers who want flexibility ("Use points on anything")
- **Perks** appeal to customers who want predictable rewards ("One more for free!")
- **Gamification:** Two progress bars = twice the engagement
- **Owner control:** Set point percentage + perk thresholds per shop

**Competitive Advantage:**
Most loyalty apps offer points OR punch cards, not both simultaneously. Dual system maximizes motivation across customer types.

---

### 3. Services Display (Valvoline-Inspired Transparency)

**How It Works:**
- Owner creates master service list (CRUD interface)
- Manager selects which services their shop offers
- Customer sees service cards: Icon + Name + Time estimate (no pricing)
- Example: "Full-Service Oil Change ~ 15 mins", "Air Conditioning ~ 30-60 mins"

**Why This Matters:**
- **Reduces friction:** Customer knows you offer service before calling/visiting
- **Sets expectations:** Time estimates help customer plan their day
- **Professional appearance:** Matches Valvoline's modern app UX
- **No pricing pressure:** Time info only, avoids sticker shock

**Competitive Advantage:**
Generic loyalty apps don't have service displays. This automotive-specific feature shows you understand customer needs.

---

### 4. Flash Sale Architecture (Purpose-Built for Bays)

**Unlike generic "send a coupon" features, Shop Rewards is designed for time sensitive bay filling:**

**Time Bound Offers:**
- Coupons auto expire after set duration (2 hours, 4 hours, 8 hours)
- Countdown timer visible to customers
- Creates urgency: "Only 1:23:45 left!"

**Usage Limits:**
- Set max redemptions: "First 10 customers only"
- Dashboard shows: "7 of 10 redeemed"
- Prevents over discounting

**Scheduling:**
- Schedule Flash Sales in advance: "Send Saturday at 10 AM"
- Recurring offers: "Every Tuesday at 2 PM, send 30% off tire rotation"

**A/B Testing:**
- Send different offers to different customer segments
- Track which discounts drive most redemptions
- Optimize over time

---

### 3. Franchise-Safe Data Architecture

**Key Design Decision: NO POS Integration**

**Why this matters:**
- Franchise agreements often prohibit modifications to corporate mandated POS systems
- POS data belongs to franchise corporate, not individual locations
- Integrating with POS creates technical dependency and compliance risk

**How Shop Rewards Solves This:**
- **Separate database:** Customer data stored independently
- **Manual point entry:** Manager adds points after checking POS invoice (5 second task)
- **No automated sync:** Shop Rewards never reads from or writes to Sage
- **Legally defensible:** "This is a marketing tool, not a POS modification"

**Franchise Owner Benefit:**
- Deploy without corporate IT approval
- Zero risk of franchise agreement violation
- Can remove/change platform without POS disruption

---

## User Experience Design

### Mobile-First Design Principles

**Large Touch Targets:**
- All buttons minimum 44×44 pixels (Apple recommendation)
- Easy to tap even with gloves (common in automotive environments)

**Minimal Text Entry:**
- Prioritize drop downs, buttons, and scanners over typing
- Auto complete for common fields (city, state)

**High Contrast:**
- Dark mode optimized for outdoor visibility (customers checking phones in parking lot)
- Large fonts for readability in bright sunlight

**Offline Support:**
- Customer can view their rewards points balance even without internet
- Manager dashboard shows cached data if connection drops
- Syncs when reconnected

---

## Technical Architecture (High-Level)

### Technology Stack

**Backend:**
- **Ruby on Rails 8.x:** Modern, stable framework with 20+ years of production use
- **PostgreSQL:** Industry standard database, scales to millions of records
- **Redis:** Fast caching layer for real-time features

**Frontend:**
- **Hotwire (Turbo + Stimulus):** Modern Rails approach, minimal JavaScript
- **Tailwind CSS:** Utility first CSS for rapid, consistent UI development
- **PWA Manifest + Service Worker:** Enables "Add to Home Screen" and offline support

**Infrastructure:**
- **Heroku Platform:** Managed hosting with 99.99% uptime SLA
- **AWS S3:** File storage for user avatars (if needed in future)
- **OneSignal:** Push notification delivery (free up to 10,000 users)

**Security:**
- **SSL/TLS encryption:** All data transmitted over HTTPS
- **Bcrypt password hashing:** Industry-standard user authentication
- **SQL injection protection:** Built into Rails framework
- **CSRF token protection:** Prevents cross-site request forgery

**Compliance:**
- **GDPR-ready:** Data export and deletion features
- **CCPA-compliant:** California privacy law alignment
- **TCPA-safe:** Explicit opt-in, timestamp logging, easy opt-out

---

## Scalability & Performance

### Built to Scale

**Current Pilot Capacity:**
- 5,000 customers
- 100 Flash Sales per day
- 500 concurrent users

**Enterprise Capacity (With Zero Code Changes):**
- 250,000 customers
- 1,000 Flash Sales per day
- 5,000 concurrent users

**Scaling Path:**
- Pilot: Standard Heroku dyno ($50/mo)
- Growth: Performance dyno ($250/mo)
- Enterprise: Multiple dynos with auto scaling ($500-1,000/mo)

**Database Performance:**
- PostgreSQL handles millions of rows efficiently
- Indexed queries for sub-100ms response times
- Automated daily backups with point-in-time recovery

---

## Future Enhancements (Post-MVP)

These features are intentionally excluded from MVP to keep timeline and cost manageable. If pilot succeeds, they can be added incrementally:

### Phase 2 Features (Months 4-6)
- **Service History Tracking:** Log each visit with mileage, services performed
- **Automated Reminders:** "Your 5,000-mile oil change is coming up"
- **Referral Program:** "Refer a friend, get 50 bonus points"

### Phase 3 Features (Months 7-12)
- **AI Chatbot:** "What services does my car need at 60k miles?"
- **Appointment Booking:** Reserve service time slot in-app
- **Payment Integration:** Pay invoices through app (Stripe)

### Phase 4 Features (Year 2+)
- **Marketplace:** Shop for tires, batteries, accessories
- **Subscription Plans:** Unlimited oil changes for $X/month
- **Fleet Management:** Tools for businesses with multiple vehicles

**Important:** MVP delivers core value (bay-filling + loyalty). Everything else is optional upside.

---

## Success Criteria: What "Working" Means

For the MVP demonstration and 90-day pilot, Shop Rewards is considered successful if:

**Technical Success:**
- ✅ Manager can send Flash Sale in <60 seconds
- ✅ Customer receives push notification within 10 seconds
- ✅ QR code signup completes in <30 seconds average
- ✅ App loads in <2 seconds on 4G connection
- ✅ Zero data loss or security breaches

**Business Success:**
- ✅ 15%+ Flash Sale redemption rate
- ✅ 100+ customers signed up per location
- ✅ Measurable increase in daily car count
- ✅ Positive manager feedback (easy to use)
- ✅ Positive ROI within 30 days

**User Experience Success:**
- ✅ Customer signup takes <30 seconds average
- ✅ App feels fast and responsive
- ✅ Zero complaints about spam or unwanted messages
- ✅ Customers voluntarily show app to friends ("Check out this cool app my shop has")

---

## Conclusion: Product Value Proposition

**Shop Rewards delivers three core values:**

1. **For Customers:** A fast, modern way to save money and get rewarded for loyalty
2. **For Managers:** A simple, powerful tool to fill bays and track customer engagement
3. **For Owners:** A data-driven platform to recover lost revenue and build competitive advantage

**All at 70-90% lower cost than any comparable solution.**

---

**Next Section:** Technical Specifications (detailed architecture and security)
