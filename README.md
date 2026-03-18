# ADV
A secure web-based payment system that generates and emails unique IntaSend checkout links to customers, processes payments via M-Pesa or card, and tracks transaction status in real time .





# 💳 Secure Email-Based Payment System  
### *(IntaSend + Google Apps Script)*

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
- Displays payment link  
- Auto-checks payment status  

---

### ⚙️ Backend (Google Apps Script)
- Generates secure payment links  
- Stores transactions in Google Sheets  
- Sends payment emails  
- Handles webhook updates  

---

### 💳 Payment Gateway
- Powered by **IntaSend**  
- Secure and reliable transaction handling  

---

### 🗄️ Database
- Google Sheets (`PAYMENTS`)  
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

Set these in **Google Apps Script → Project Settings → Script Properties**