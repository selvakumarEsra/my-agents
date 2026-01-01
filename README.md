# ActiveSG Booking Agent (Comet Browser)

## Overview

**ActiveSG Booking Agent** is a structured, instruction-driven browser agent designed to operate inside **Comet Browser** to assist with:

- Extracting existing ActiveSG bookings
- Discovering badminton courts near a given postal code
- Checking availability for a specific time slot (e.g. 9:00 PM)
- Presenting results in structured table format

The agent is written to behave deterministically and follows a strict execution order.

> ⚠️ Important:  
> Due to security, payment, and Singpass constraints, **Comet Browser can safely support discovery and verification**, but **cannot reliably complete final booking/payment steps automatically**.  
> The agent will **check feasibility and guide booking**, not silently perform irreversible actions.

---

## Agent Capabilities in Comet

### ✅ What the agent CAN do
- Navigate ActiveSG menus
- Read and extract existing bookings
- Search venues by postal code
- Extract available courts and time slots
- Check whether a specific time (e.g. 9 PM) is available
- Display results as structured tables

### ❌ What the agent CANNOT reliably do (Comet limitation)
- Persist authenticated sessions across runs
- Bypass Singpass / OTP / CAPTCHA
- Complete payments (“Pay using ActiveSG$”)
- Perform irreversible bookings unattended

For **actual booking automation**, use:
- n8n + Playwright
- Human-in-the-loop confirmation

---

## Files in This Setup

---

## Prerequisites

- Comet Browser (latest version)
- ActiveSG account
- Singpass access enabled
- Stable internet connection

---

## How to Run the Agent in Comet Browser

### Step 1: Open Comet Browser
Launch **Comet Browser** on your system.

---

### Step 2: Login to ActiveSG
1. Navigate to:  
   https://activesg.gov.sg/
2. Click **Login**
3. Complete login using **Singpass**
4. Ensure you land on the ActiveSG homepage while logged in

> ⚠️ Do not refresh or open a new tab after login

---

### Step 3: Open Comet Assistant
1. In the **top-right corner**, click **Assistant**
2. This opens the Comet AI panel

---

### Step 4: Paste Agent Instructions
1. Open `ActiveSG_Booking_Agent.md`
2. Copy **all contents**
3. Paste into the **Assistant input area**

---

### Step 5: Set Agent Arguments
Before executing, replace the argument values:

```json
{
  "instant_booking_time": "9:00 PM",
  "postal_code": "XXXXXX"
}


## Example
{
  "instant_booking_time": "9:00 PM",
  "postal_code": "520111"
}
