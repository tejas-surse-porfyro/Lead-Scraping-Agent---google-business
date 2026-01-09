# 🧲 AI Lead Scraper Agent (Google Maps – n8n)

This repository contains an **AI Lead Scraper Agent** built using **n8n**, **Apify (Google Maps scraper)**, and **Google Sheets**.

The workflow automates **local business lead collection** from Google Maps based on business type and location and stores the results in a Google Sheet.

---

## 📌 Overview

The **Lead Scraper Agent** allows you to collect business leads without manually searching Google Maps.

You enter:
- Business type
- Location
- Number of results

The automation:
- Scrapes matching businesses from Google Maps using Apify
- Extracts structured lead data
- Saves it directly into Google Sheets

---

## ▶️ How the Workflow Is Triggered

- Triggered using **n8n Form Trigger**
- Runs automatically on every form submission

---

## ⚙️ What It Does (Exact)

- Accepts input from a form:
  - Business Type (required)
  - Location (required)
  - Max Results (optional)
- Sends data to Apify Google Maps scraper API
- Receives business lead data
- Appends leads into Google Sheets
- Avoids duplicates using business name matching

---

## 🛠 Nodes Used in Workflow

Only the following nodes are used:

1. **Form Trigger**
   - Collects:
     - Business Type
     - Location
     - Max Results

2. **HTTP Request**
   - Sends POST request to Apify:
     ```
     google-map-business-scraper
     ```
   - Parameters sent:
     - businessType
     - location
     - maxResults

3. **Google Sheets – Append row**
   - Stores lead data into Sheet1
   - Maps fields:
     - Name
     - Category
     - Rating
     - Address
     - Website
   - Deduplication based on Name

---

## 📊 Data Collected Per Lead

Each lead stored in Google Sheets includes:
- Business Name
- Category
- Google Rating
- Full Address
- Website (if available)

---

## 🧠 How This Agent Can Be Used (Real Scenarios)

### 1️⃣ Freelancers & Agencies (Lead Generation)

- Scrape leads like:
  - Cafes in Pune
  - Salons in Mumbai
  - Clinics in Bangalore
- Export Google Sheet
- Use it for:
  - Cold email
  - WhatsApp outreach
  - Sales calls

---

### 2️⃣ Local Service Businesses

- Find competitors or potential partners
- Build a local business directory
- Identify businesses without websites for upselling

Example:
- Business Type: Gym  
- Location: Hyderabad  

---

### 3️⃣ SaaS or Tool Promotion

- Scrape businesses relevant to your SaaS
- Example:
  - Business Type: Real Estate Agency
  - Location: Delhi
- Use output sheet for demo outreach or onboarding

---

### 4️⃣ Marketing Campaign Preparation

- Generate targeted lead lists before campaigns
- Segment by:
  - Location
  - Business category
  - Rating
- Use the same Google Sheet for email tools

---

### 5️⃣ Internal Research & Data Collection

- Market research
- Competitor analysis
- Business density analysis by location

---

## 📁 Google Sheets Usage

The Google Sheet acts as:
- Lead database
- Deduplicated list
- Ready-to-use outreach source

Columns updated:
- Name
- Category
- Rating
- Address
- Website

---

## 🧱 Tech Stack Used

- **n8n**
- **Apify API (Google Maps Business Scraper)**
- **Google Sheets API**
- **HTTP Request Node**
- **Form Trigger Node**



