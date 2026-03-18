# ADV
A secure web-based payment system that generates and emails unique IntaSend checkout links to customers, processes payments via M-Pesa or card, and tracks transaction status in real time .





# 💳 Secure Email-Based Payment System (IntaSend + Google Apps Script)

---

## 🧾 1. OVERVIEW

This application enables users to:

- Enter an email and amount on the frontend  
- Receive a payment link via email  
- Complete payment through IntaSend  
- Automatically update payment status via webhook  
- View real-time payment status on the frontend  

---

## ⚙️ 2. SYSTEM ARCHITECTURE

The system follows a simple client-server-payment flow:

- Frontend (HTML/JavaScript) collects user input  
- Backend (Google Apps Script) processes requests  
- IntaSend API generates payment links  
- Webhook updates transaction status  
- Google Sheets stores transaction records  

Flow:

Frontend → Backend → IntaSend → Webhook → Backend → Google Sheets → Frontend  

---

## 🧩 3. COMPONENTS

### 🔹 Frontend
- User interface for entering email and amount  
- Sends payment requests to backend  
- Displays payment link  
- Checks and displays payment status  

### 🔹 Backend (Google Apps Script)
- Handles incoming requests  
- Generates payment links via IntaSend  
- Stores transactions in Google Sheets  
- Sends payment emails  
- Processes webhook updates  

### 🔹 Payment Gateway
- IntaSend processes all payments securely  

### 🔹 Database
- Google Sheets used as storage (`PAYMENTS` sheet)  

---

## 📊 4. GOOGLE SHEETS STRUCTURE

Sheet Name: `PAYMENTS`

- Column A: OrderID (Unique identifier)  
- Column B: Email (Customer email)  
- Column C: Amount (KES)  
- Column D: PaymentLink  
- Column E: Status (PENDING / COMPLETE)  
- Column F: TxnID (Transaction ID)  
- Column G: CreatedAt (Timestamp)  

---

## 🔐 5. CONFIGURATION

Set the following in Google Apps Script → Project Settings → Script Properties:

- INTASEND_PUBLIC_KEY = pk_live_xxxxx  
- INTASEND_SECRET_KEY = sk_live_xxxxx  

**Important:**
- These keys must remain in the backend only  
- Never expose them in frontend code  

---

## 🌐 6. DEPLOYMENT

To deploy the backend:

1. Open Google Apps Script  
2. Click Deploy → New Deployment  
3. Choose Web App  
4. Set:
   - Execute as: Me  
   - Access: Anyone  
5. Deploy and copy the Web App URL  

---

## 🔗 7. WEBHOOK SETUP

In IntaSend dashboard:

1. Go to Developers → Webhooks  
2. Set webhook URL:

   https://script.google.com/macros/s/YOUR_DEPLOYMENT_ID/exec  

3. Save configuration  

---

## 🔄 8. SYSTEM FLOW

### Step 1: User Request
User enters email and amount.  
Frontend sends request to backend.

### Step 2: Backend Processing
Backend:
- Generates Order ID  
- Requests payment link from IntaSend  
- Saves transaction in Google Sheets  
- Sends email with payment link  

### Step 3: Payment
User clicks link and completes payment via IntaSend.

### Step 4: Webhook Update
IntaSend sends payment confirmation to backend.  
Backend updates status in Google Sheets to COMPLETE.

### Step 5: Status Check
Frontend queries backend using OrderID.  
Backend returns current status (PENDING or COMPLETE).  

---

## 🧪 9. TESTING

To test the system:

1. Enter a valid email and amount  
2. Click "Pay Now"  
3. Open generated payment link  
4. Complete payment  
5. Verify:
   - Google Sheet updates to COMPLETE  
   - Frontend displays success  

---

## 🔍 10. TROUBLESHOOTING

If payment status remains PENDING:

- Ensure webhook URL is correct  
- Confirm deployment access is set to "Anyone"  
- Check Apps Script execution logs  
- Verify payment completed in IntaSend dashboard  

---

## 🔐 11. SECURITY

### Implemented

- Backend-only storage of API keys  
- No secrets in frontend  
- Input validation  

### Recommended Improvements

- Webhook verification  
- Rate limiting  
- Domain restrictions  
- Activity logging  

---

## 🚨 12. LIMITATIONS

- Uses polling instead of real-time updates  
- No authentication system  
- No admin dashboard  
- No refund handling  

---

## 🚀 13. FUTURE IMPROVEMENTS

- M-Pesa STK Push integration  
- Admin dashboard  
- SMS notifications  
- PDF receipts  
- Real-time updates (WebSockets)  

---

## 🏷️ 14. DESCRIPTION

A secure web-based payment system that enables users to generate payment links via email and complete transactions through IntaSend, with automated backend processing and Google Sheets tracking.

---

## 🎯 15. STATUS

- Fully functional  
- Secure architecture  
- Live payment ready  
- Scalable for production use  

---

## 📞 16. CONTACT

For support or inquiries:

- <i class="fas fa-user"></i> **Name:** Your Name  
- <i class="fas fa-envelope"></i> **Email:** <a href="mailto:your@email.com" target="_blank">your@email.com</a>  
- <i class="fas fa-phone"></i> **Phone:** <a href="tel:+254XXXXXXXXX" target="_blank">+254 XXX XXX XXX</a>  
- <i class="fas fa-globe"></i> **Website:** <a href="https://yourwebsite.com" target="_blank">https://yourwebsite.com</a>  

---

> 💡 *Ensure Font Awesome is included if rendering icons in HTML.*
---