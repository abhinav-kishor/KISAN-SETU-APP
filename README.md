# 🌾 KisanSetu

## The Smart Bridge Between Farmers and Better Markets

KisanSetu is a farmer-focused Android application designed to help farmers make more informed market-selection decisions by bringing together government mandi prices, location intelligence, transportation estimates, market comparison, price trends, alerts, and AI-powered assistance in a single platform.

Instead of simply showing the highest mandi price, KisanSetu considers multiple practical factors such as crop quantity, market price, road distance, transportation cost, and other applicable costs to estimate the potential return and help the farmer identify a suitable market.

*IMP: use PHONE NO.: 8791345325
     and otp : 123456
---

## 📌 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Our Solution](#-our-solution)
- [Objectives](#-objectives)
- [Core Features](#-core-features)
- [How KisanSetu Works](#-how-kisansetu-works)
- [Recommendation Engine](#-recommendation-engine)
- [Government Mandi Data](#-government-mandi-data)
- [Transportation Cost Estimation](#-transportation-cost-estimation)
- [Maps and Location Intelligence](#-maps-and-location-intelligence)
- [AI Assistant](#-ai-assistant)
- [Multi-Language Support](#-multi-language-support)
- [Authentication](#-authentication)
- [Mandi / Market Module](#-mandi--market-module)
- [System Architecture](#-system-architecture)
- [Technology Stack](#-technology-stack)
- [Data Flow](#-data-flow)
- [Security and Reliability](#-security-and-reliability)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Building the APK](#-building-the-apk)
- [Testing](#-testing)
- [Limitations](#-limitations)
- [Future Scope](#-future-scope)
- [Project Development Journey](#-project-development-journey)
- [Research and References](#-research-and-references)
- [Disclaimer](#-disclaimer)
- [Team](#-team)
- [License](#-license)

---

# 🌱 Overview

Farmers often have access to market prices, but selecting the right market is not always as simple as choosing the market with the highest price.

A market offering a slightly higher price may be significantly farther away, resulting in higher transportation costs. Similarly, the final return depends on the quantity being sold and other applicable costs.

KisanSetu addresses this decision-making problem by connecting:

**Farmer → Crop → Quantity → Location → Market Data → Distance → Transportation Cost → Estimated Return → Market Recommendation**

The application is designed to act as a digital bridge between farmers and markets.

---

# ❗ Problem Statement

Farmers may face several challenges when deciding where to sell their produce:

- Difficulty comparing multiple mandis.
- Market prices can vary between locations.
- The highest market price does not always mean the highest potential return.
- Transportation costs can significantly affect the final return.
- Market information may be spread across different platforms.
- Farmers may need to check routes and distances separately.
- Language barriers can make digital services difficult to use.
- Raw market data may not directly answer the farmer's practical question: "Where should I sell?"

KisanSetu aims to bring these factors together into a single, simple mobile experience.

---

# 💡 Our Solution

KisanSetu provides a farmer-centric market decision-support system.

The farmer can enter:

- Crop
- Quantity
- Location

The application can then retrieve and process relevant market information and provide:

- Market-wise price comparison
- Government mandi prices
- Road distance
- Estimated transportation cost
- Estimated net return
- Market ranking
- Recommended market
- Route and navigation
- Price trends
- Alerts
- AI-powered assistance

The objective is not to replace the farmer's decision, but to provide transparent information that can support better decision-making.

---

# 🎯 Objectives

1. Simplify market comparison for farmers.
2. Provide access to government mandi price information.
3. Consider transportation costs while comparing markets.
4. Provide location-aware market information.
5. Calculate estimated potential returns transparently.
6. Provide explainable market recommendations.
7. Reduce the need to manually check multiple platforms.
8. Support multiple Indian languages.
9. Provide AI-powered assistance in natural language.
10. Create a scalable foundation for future agricultural services.

---

# 🚀 Core Features

## 1. Find Best Market

Farmers can enter:

- Crop
- Quantity
- Location

KisanSetu compares available markets using market price, distance, transportation cost, and estimated return.

The system then presents the comparison and identifies a suitable market based on the calculated estimated return.

---

## 2. Market Comparison

The application presents multiple markets with information such as:

- Market name
- Crop price
- Distance
- Estimated transportation cost
- Estimated return
- Recommendation status

The recommendation is not based solely on the highest price.

---

## 3. Government Mandi Bhav

KisanSetu integrates government-provided mandi price information through the Government of India's open data platform.

Users can browse:

- State
- District
- Market
- Commodity
- Variety
- Grade
- Minimum price
- Maximum price
- Modal price
- Arrival date

The Mandi Bhav section supports state-level browsing and more specific filtering where data is available.

---

## 4. Google Maps Integration

KisanSetu integrates Google Maps Platform for location-based functionality.

It provides:

- Market locations
- Road routes
- Road distance
- Estimated travel time
- Navigation support

The selected farmer location and market location can be used for route calculations.

---

## 5. Location Autocomplete

KisanSetu uses Google Places functionality to provide real-world location suggestions while the user types.

Instead of requiring farmers to manually enter a complete address, the application can provide relevant location suggestions.

A selected location can provide:

- Formatted address
- Latitude
- Longitude
- Place ID

These coordinates can then be used by the routing and market-location system.

---

## 6. Transportation Cost Estimation

Transportation cost is estimated using road distance and configured vehicle pricing.

The basic calculation is:

**Transportation Cost = Base Fare + (Road Distance × Rate per km) + Loading Charge**

Different vehicle types can have different:

- Capacities
- Base fares
- Per-kilometre rates
- Loading charges

The application filters vehicles according to the quantity of produce.

For example, a vehicle whose capacity is lower than the farmer's required quantity will not be considered suitable.

The current prototype uses configurable/demo vehicle rates. In a production version, these rates can be replaced with verified rates from transport providers or local transportation partners.

---

# 🤖 AI Assistant — Kisan Sahayak

Kisan Sahayak is the AI-powered conversational assistant integrated into KisanSetu.

It is designed to allow farmers to interact with the application using natural language.

Kisan Sahayak can assist with:

- Understanding market information
- Explaining application results
- General agricultural queries
- Hindi/Hinglish interaction
- Conversational assistance

### AI Design Principle

AI is not responsible for the core numerical calculation or market ranking.

The application logic performs deterministic calculations such as:

- Gross value
- Transportation cost
- Estimated return
- Market ranking

Gemini is primarily used for:

- Assistance
- Explanation
- Conversational interaction

This separation reduces dependency on generative AI for deterministic calculations.

---

# 🌐 Multi-Language Support

KisanSetu is designed with multilingual accessibility in mind.

Supported languages include:

- English
- Hindi
- Marathi
- Bengali
- Telugu

The selected language can be persisted across the application.

The purpose of multilingual support is to reduce language barriers and make the application more accessible to farmers from different regions of India.

---

# 🔐 Authentication

KisanSetu uses Firebase Authentication for user account management.

The authentication workflow supports:

- User registration
- Login
- Password-based authentication
- Phone verification
- Optional email
- Email verification when applicable
- Password reset
- Persistent authentication state
- User profile information

For development and prototype testing, Firebase's official test phone-number mechanism can be used for phone authentication without sending real SMS messages.

---

# 🏪 Mandi / Market Module

KisanSetu also provides a market/mandi-side workflow.

Authorized market users can maintain market-related information such as:

- Market/shop details
- Address
- Location
- Crop information
- Price information
- Demand information

The long-term vision is to support a two-sided ecosystem:

**Farmers ↔ Markets/Mandis**

This can create a foundation for future market communication and participation.

---

# 🧮 Recommendation Engine

One of the main concepts behind KisanSetu is that the highest market price does not necessarily mean the highest estimated return.

For example:

**Market A**
- Price: ₹2,500/quintal
- Distance: 10 km

**Market B**
- Price: ₹2,600/quintal
- Distance: 40 km

Although Market B offers a higher price, its additional transportation cost may reduce the potential return.

Therefore, KisanSetu uses a cost-aware market comparison approach.

### Gross Value

```text
Gross Value = Quantity × Market Price
