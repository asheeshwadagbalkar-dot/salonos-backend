# 🌟 SalonOS — Multi-Tenant Beauty Parlour & Salon SaaS Management Platform

A modern, production-grade Multi-Tenant SaaS platform tailored for beauty parlours, luxury salons, spas, and grooming studios.

---

## 🏗️ Multi-Tenant Architecture

Each salon tenant gets an isolated environment:
- **Subdomain Routing**: `luxeglow.salonos.com`, `glamourcuts.salonos.com`
- **Header & API Routing**: Handled via `x-tenant-slug` and `x-tenant-id` HTTP headers
- **Data Isolation**: All database models, services, inventory, and staff rosters are strictly scoped by `tenant_id`
- **Multi-Branch Support**: Seamless support for flagship and multiple branch outlets under each tenant
- **Super Admin Platform HQ**: Unified platform governance, Monthly Recurring Revenue (MRR) tracking, and SaaS subscription tier management

---

## 💻 Tech Stack

- **Frontend**: React.js (Vite) + Tailwind CSS + Lucide Icons + Google Fonts (Poppins & Inter)
- **Backend**: Node.js + Express.js REST API
- **Database**: MongoDB (Mongoose) with automatic high-speed embedded zero-config fallback
- **Integrations**: 
  - WhatsApp Business API Automation Engine & Conversational Chatbot
  - Razorpay Online Payment Gateway Integration
  - 80mm Thermal Receipt POS Printing Engine
  - SMS Notification Gateway Simulation

---

## 📦 Delivered Modules & Features

### 1. 🔐 Authentication & Onboarding
- Multi-role Role-Based Access Control (RBAC): `superadmin`, `owner`, `manager`, `receptionist`, `staff`, `customer`
- 1-Click interactive **Demo Persona Switcher** in the top navigation bar for testing each role
- Salon Owner Onboarding with auto-generated subdomains, logo/banner setup, and business hours

### 2. ✂️ Service & Combo Management
- Pre-configured service categories: *Hair Services*, *Skin & Facials*, *Nail Art*, *Bridal & Make-Up*, *Spa & Massage*, *Waxing & Threading*, *Men's Grooming*
- Full duration picker (15m, 30m, 45m, 60m, 90m, 120m, 180m), MRP vs Offer pricing, and gender applicability
- Home/Doorstep service toggles with custom travel charges
- Combo Packages bundling multiple services with savings calculations

### 3. 📅 Smart Appointment Booking & Calendar
- Day, Week, and Month scheduling views
- Real-time slot calculation algorithm preventing double bookings and enforcing salon buffer times
- Status progression: `pending` ➔ `confirmed` ➔ `in_progress` ➔ `completed` ➔ `cancelled`
- Quick Walk-In booking modal with live slot computation

### 4. 💳 Point of Sale (POS) & Quick Billing
- Fast touch-friendly service and retail product catalog
- Dynamic item cart with quantity steppers and customer lookup
- Real-time coupon discount code validation (`FESTIVE25`, `WELCOME100`, `BDAY2026`)
- Automated GST calculation (CGST 9% + SGST 9%)
- Split payments tender support: Cash, Card, UPI, Customer Prepaid Wallet, and Razorpay
- Instant **80mm Thermal Tax Receipt** printable modal with QR code

### 5. 💬 WhatsApp Business Automation Engine & Chatbot
- **Trigger-Based Workflow Engine**:
  1. *New Booking Created* ➔ Immediate WhatsApp + SMS confirmation
  2. *24 Hours Before Appointment* ➔ Gentle reminder
  3. *2 Hours Before Appointment* ➔ Final call with Google Maps directions
  4. *Appointment Completed* ➔ Post-service review and Google rating request
  5. *Customer Birthday* ➔ 30% OFF celebration voucher code
  6. *60 Days Inactive* ➔ Automated comeback re-engagement message
- **Interactive Phone Chatbot Simulator**:
  - Test real-time bot replies for commands: `BOOK`, `SERVICES`, `OFFERS`, `HOURS`, `LOCATION`, `BALANCE`
- Transmission log feed tracking delivery status (`sent`, `delivered`, `read`)

### 6. 👥 Customer CRM & Loyalty Engine
- Client segmentation tabs: *VIP High Spenders*, *Regulars*, *First Timers*, *Inactive (60+ days)*, *Birthdays This Month*
- Customer 360 profile view with visit history and itemized invoices
- Prepaid Wallet with promotional recharge bonuses (e.g., recharge ₹1000, get ₹1100)
- Loyalty points balance management (redeemable at billing)

### 7. 📦 Inventory & Consumables Management
- Retail and back-bar product tracking with SKU, barcode, cost price, and selling price
- Visual Low-Stock warning indicators
- Stock-In (Purchase) and Stock-Out (Usage/Wastage) adjustment logging

### 8. 🌐 Standalone Public Booking Widget & Mini Website
- Customer-facing booking portal at `salonname.salonos.com/book`
- 7-Step booking wizard:
  - Step 1: Select Treatment(s)
  - Step 2: Choose Stylist (or "Any Available")
  - Step 3: Pick Date & Live Available Slot
  - Step 4: Contact Details & Doorstep Address input
  - Step 5: Apply Promo Coupon
  - Step 6: Select Payment (Pay at Salon or Razorpay Online)
  - Step 7: Booking Confirmation with WhatsApp alert preview

### 9. 🛡️ Super Admin Control Center
- Platform-wide KPIs: Total registered salons, total bookings, Monthly Recurring Revenue (MRR)
- Salon tenant governance (1-click Suspend / Activate)
- SaaS Subscription tier manager: *Free (₹0)*, *Starter (₹999)*, *Professional (₹2,499)*, *Enterprise (₹4,999)*

---

## 🚀 Quick Start Guide

### 1. Prerequisites
- Node.js (v18+)
- (Optional) MongoDB running on `mongodb://127.0.0.1:27017/salon_saas` — If MongoDB is not running, the platform seamlessly boots with its built-in embedded data engine.

### 2. Run Backend Server
```bash
node server/src/server.js
```
The server will run on `http://localhost:5000`.

### 3. Run Frontend Application
```bash
cd client
npm run dev
```
Open `http://localhost:3000` in your browser.

---

## 🔑 Pre-Seeded Demo Accounts

| Role | Name | Identifier | Password |
|---|---|---|---|
| **Super Admin** | Platform Owner | `admin@salonos.com` | `admin123` |
| **Salon Owner** | Priya Sharma (Luxe Glow) | `priya@luxeglow.com` | `admin123` |
| **Manager** | Rahul Verma | `rahul@luxeglow.com` | `admin123` |
| **Stylist** | Sameer Khan | `sameer@luxeglow.com` | `admin123` |
| **Receptionist** | Ananya Deshmukh | `ananya@luxeglow.com` | `admin123` |
| **Customer** | Kavita Reddy | `+91 98450 12345` | OTP: `123456` |

*(Note: You can also instantly switch personas at any time using the Role Switcher pill in the top navbar!)*
