# Shree Sanitary (Laalwani) — Online Payment & Digital Banking Architecture Guide

This comprehensive guide explains online payment gateway integrations, transaction charges (MDR), regulatory structures, merchant vs customer fee absorption, and real-world implementation strategies for **Shree Sanitary (Laalwani Commercial ERP)**.

---

## 1. Executive Summary & Recommended Strategy

For an Indian sanitaryware, tiles, and plumbing fittings retail & wholesale enterprise in Gujarat:

| Payment Method | Cost to Shop (MDR) | Cost to Customer | Settlement Time | Recommendation |
| :--- | :--- | :--- | :--- | :--- |
| **UPI / Bharat Interface for Money** | **0% (₹0.00)** | **₹0.00** | Instant / T+0 | **Primary Choice (100% Recommended)** |
| **Direct Bank Transfer (NEFT / RTGS / IMPS)** | **₹0.00** | **₹0.00** | Instant to 2 Hours | **For Wholesale & High Value (>₹25,000)** |
| **RuPay Debit Cards** | **0% (₹0.00)** | **₹0.00** | T+1 Business Day | Excellent for counter card swipes |
| **Visa / Mastercard Debit Cards** | **0.40% – 0.90% + GST** | ₹0.00 | T+1 to T+2 Days | Absorb as store operating expense |
| **Visa / Mastercard Credit Cards** | **1.80% – 2.00% + GST** | ₹0.00 (or +2% surcharge) | T+1 to T+2 Days | Surcharge for wholesale; absorb for retail |
| **Net Banking** | **₹10 – ₹15 flat / 1.5%** | ₹0.00 | T+1 Business Day | Use NEFT/RTGS instead for 0 cost |

---

## 2. Who Pays the Transaction Charges? (Shop vs Customer)

### A. Retail Counter Sales (Walk-in Customers)
* **Rule:** **Merchant (Shree Sanitary) absorbs the fee.**
* **Reason:** In modern Indian retail, charging a customer 2% extra for swiping a credit card or using an online gateway creates immediate friction and can lose sales. Because over **80% of counter payments in India now happen over UPI** (which carries **0% fee**), your actual blended transaction processing cost across all sales is typically less than **0.2%** of gross turnover.

### B. Wholesale / Site Contracting Orders (>₹25,000 to ₹5,00,000+)
* **Rule:** **Customer pays via 0% methods (Bank Transfer / UPI) OR pays a 2% convenience surcharge on Credit Cards.**
* **Explanation:** On a bathroom package order of ₹1,00,000, a 2% credit card fee equals **₹2,000 + 18% GST = ₹2,360**. Because wholesale sanitary margins are competitive (10% to 15%), absorbing ₹2,360 directly cuts 20% of your net profit margin!
* **Commercial Best Practice:** Inform the contractor/builder:
  > *"We accept direct NEFT, RTGS, IMPS, Cheque, and UPI at zero additional cost. If you prefer to swipe a commercial or personal rewards credit card, the standard bank gateway fee of 2% will be added to the invoice."*

---

## 3. Top Payment Gateway Providers in India

### Option 1: Razorpay (Market Leader)
* **Pros:** Best developer APIs, rock-solid uptime, instant webhook callbacks, built-in Magic Checkout, generates dynamic payment links via WhatsApp / SMS.
* **Pricing:**
  * UPI & RuPay Debit Cards: **0%**
  * Domestic Visa / Mastercard Credit & Debit: **2.00% + 18% GST**
  * Corporate Credit Cards / Amex: **3.00% + 18% GST**
* **Setup Fee:** ₹0 (No annual maintenance charges).

### Option 2: Cashfree Payments (Low Cost & Instant Settlements)
* **Pros:** Specialized in instant vendor payouts (paying suppliers) and instant customer collections. Often negotiates lower MDR (1.75% + GST) for commercial accounts.
* **Pricing:**
  * UPI: **0%**
  * Standard Cards: **1.75% to 1.90% + GST**
* **Setup Fee:** ₹0.

### Option 3: PhonePe Payment Gateway & PhonePe for Business
* **Pros:** Massive UPI consumer trust, highly aggressive rates, and seamless integration with PhonePe Smart Speaker (voice notification in Gujarati/Hindi/English).
* **Pricing:**
  * UPI: **0%**
  * Debit Cards: **0.4% - 0.85% + GST**
  * Credit Cards: **1.85% + GST**
* **Setup Fee:** ₹0.

### Option 4: Pine Labs / Mosambee / Innoviti Android Smart POS
* **Pros:** Physical countertop all-in-one terminal with touchscreen, built-in thermal printer, chip/swipe card reader, and dynamic screen QR code.
* **Pricing:**
  * One-time or monthly machine rental: ₹300 – ₹500/month.
  * UPI transactions: **0%**.
  * Card MDR: Standard RBI regulated rates.

---

## 4. Hardware Notification: Smart Soundbox (Voice Alerts)

In busy sanitaryware retail counters, staff may not look at the computer screen immediately when a customer scans a QR code. Installing a **Voice Soundbox** at the counter solves this completely:
* **Supported Devices:** PhonePe Smart Speaker, Paytm Soundbox, or HDFC SmartHub Soundbox.
* **Features:**
  * Plays loud voice audio immediately upon bank confirmation:
    > *"શ્રી સેનિટરી પર ₹2,450 સફળતાપૂર્વક મળ્યા"* (Gujarati)
    > *"श्री सेनेटरी पर ₹2,450 प्राप्त हुए"* (Hindi)
  * Eliminates fake screenshot fraud by walk-in buyers.
  * Nominal rental cost: typically ₹100 to ₹125/month, often waived by banks if monthly transactions exceed ₹50,000.

---

## 5. Documents Required to Open a Merchant Gateway Account

To activate Razorpay, Cashfree, or a Bank Merchant Gateway for Shree Sanitary:
1. **GSTIN Registration Certificate** (Form GST REG-06).
2. **Current Bank Account Cancelled Cheque** with firm name printed (`Shree Sanitary`).
3. **Proprietor / Partner PAN Card** and **Aadhaar Card**.
4. **Shop & Establishment License (Gumasta Dhara)** or **Udyam MSME Registration Certificate**.
5. **Bank Statement** for the last 3 to 6 months.

---

## 6. Real-World Integration Roadmap for Laalwani Commercial ERP

When you are ready to activate automated digital collections, the software architecture will support three progressive modes:

### Mode 1: Static UPI QR Code (Already Live in Laalwani ERP)
* **Cost:** **₹0.00**
* **Mechanism:** Customers scan your store's printed UPI QR code (linking directly to your HDFC/SBI Current Account VPA, e.g., `shreesanitary@hdfcbank`).
* **Cashier Flow:** Cashier selects `UPI` in Billing or Orders, enters the 12-digit UTR bank reference number, and saves the bill. The collection automatically updates the Dashboard and accounts ledger.

### Mode 2: Dynamic In-App Bill QR Code
* **Cost:** **₹0.00 (No Gateway API fees)**
* **Mechanism:** Laalwani ERP dynamically generates an on-screen QR code containing:
  `upi://pay?pa=YOUR_STORE_VPA&pn=SHREE_SANITARY&am=1450.00&tr=INV1024&cu=INR`
* **Advantage:** Customer scans the QR code on the desktop monitor, and the exact invoice amount (`₹1,450.00`) is pre-filled on their phone. Customer simply enters their UPI PIN. Zero typing errors!

### Mode 3: Razorpay / Cashfree POS Webhook Auto-Reconciliation
* **Cost:** Standard gateway MDR (0% UPI, ~1.8% Credit Card).
* **Mechanism:** ERP sends an API request to generate a payment request. Once the customer authorizes the transaction, the gateway fires an instant webhook to Laalwani ERP, which auto-marks the invoice as `PAID`, triggers thermal receipt printing, and credits the Counter Cash & Bank balance in real time.

---

*Document prepared for Shree Sanitary (Laalwani Commercial ERP) — Enterprise Commercial Deployment Guide.*

