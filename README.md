# ADV
A secure web-based payment system that generates and emails unique IntaSend checkout links to customers, processes payments via M-Pesa or card, and tracks transaction status in real time .





# 💳 Secure Email-Based Payment System  
### *(IntaSend + Serverless backend)*

---

## ✨ Overview

A modern, secure, and scalable payment system that allows users to:

- 📧 Enter an email and amount  
- 🔗 Receive a payment link instantly  
- 💸 Complete payment via IntaSend  
- 🔄 Automatically update payment status via webhook  
- 📊 Track payment status in real-time  

---

## 🧠 System Architecture

---

## 🧩 Core Components

### 🎨 Frontend
- Clean UI for user input  
- Sends payment requests  
- Displays generated payment link  
- Auto-checks payment status  

---

### ⚙️ Backend (
- Generates secure payment links  
- Stores transactions in Sheets  
- Sends payment emails  
- Handles webhook updates  

---

### 💳 Payment Gateway
- Powered by **IntaSend**  
- Secure and reliable transaction handling  

---

### 🗄️ Database
- Sheets (`PAYMENTS`)  
- Lightweight and easy to manage  

---

## 📊 Database Structure

| Column | Field         | Description                  |
|--------|--------------|------------------------------|
| A      | OrderID       | Unique order identifier      |
| B      | Email         | Customer email               |
| C      | Amount        | Payment amount (KES)         |
| D      | PaymentLink   | Generated payment link       |
| E      | Status        | PENDING / COMPLETE           |
| F      | TxnID         | Transaction ID               |
| G      | CreatedAt     | Timestamp                    |

---

## 🔐 Configuration

Set these in ** → Project Settings → Script Properties**



⚠️ **Security Rule:**  
Never expose these keys in your frontend.

---

## 🚀 Deployment Guide

1. Open Script  
2. Click **Deploy → New Deployment**  
3. Select **Web App**  
4. Configure:
   - Execute as: **Me**
   - Access: **Anyone**
5. Deploy and copy the URL  

---

## 🔗 Webhook Setup

Configure webhook in IntaSend dashboard:




---

## 🔄 How It Works

### 1️⃣ User Action
User enters email and amount → clicks **Pay Now**

---

### 2️⃣ Backend Processing
- Generates Order ID  
- Requests payment link  
- Saves data  
- Sends email  

---

### 3️⃣ Payment
User clicks link and pays via IntaSend  

---

### 4️⃣ Webhook Update
- IntaSend notifies backend  
- Status updated → `COMPLETE`  

---

### 5️⃣ Frontend Status
- Frontend polls backend  
- Displays:
  - ⏳ Pending  
  - ✅ Success  

---

## 🧪 Testing

✔ Enter email & amount  
✔ Generate payment link  
✔ Complete payment  
✔ Confirm:

- Sheet updates  
- UI shows success  

---

## 🔍 Troubleshooting

If stuck on **PENDING**:

- ❌ Wrong webhook URL  
- ❌ Deployment not public  
- ❌ Payment not completed  

✔ Fix by checking:
- Script logs  
- IntaSend dashboard  

---

## 🔐 Security

### ✅ Implemented
- Backend-only secrets  
- Input validation  
- Secure API calls  

### 🔒 Recommended
- Webhook signature verification  
- Rate limiting  
- Domain restrictions  

---

## ⚠️ Limitations

- Uses polling (not real-time push)  
- No authentication system  
- No admin dashboard  

---

## 🚀 Future Enhancements

- 📲 Auto M-Pesa STK Push  
- 📊 Admin Dashboard  
- 📩 SMS Notifications  
- 🧾 PDF Receipts  
- ⚡ Real-time updates  

---

## 🏷️ Description

A secure, lightweight, and scalable payment system that enables email-based payment link generation and seamless transaction processing using IntaSend and Google Apps Script.

---

## 🎯 Status

✅ Production Ready  
✅ Secure  
✅ Scalable  
✅ Fully Functional  

---

## 📞 Contact & Support

<div align="left">

### 💼 Get in Touch

<i class="fas fa-user"></i> **McOwino**  

<a href="mailto:22techiq@gmail.com" target="_blank">22techiq@gmail.com</a>  
<a href="tel:+254751828300" target="_blank">+254 751828300</a>  
<a href="https://a-finder.vercel.app" target="_blank">Visit Website</a>  

</div>

---

## 🎨 WEWE NDIYE KUSEMA !

Wanna integrate a payment system on your website ? Get in touch and I'll handle the task for you.