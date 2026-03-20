# AI Powered Parametric Insurance for Food Delivery Workers
AI-powered micro-insurance platform for gig workers with dynamic risk assessment and secure digital payments.

## Inspiration

We started with a simple observation. Delivery partners working on platforms like Swiggy and Zomato are highly dependent on daily earnings, but they have no protection when external conditions like heavy rain, floods, or extreme heat affect their work.

Initially, the idea was just to build an insurance system. But after analyzing the problem deeper, especially the fraud scenario involving GPS spoofing, we realized that the real challenge is not just payouts, but building a system that is both fair and secure.

This project is currently in the planning and design phase, where we are focusing on structuring a realistic and implementable solution.
What it does
This is a parametric insurance system designed for food delivery workers that:

- Predicts environmental disruptions

- Estimates possible income loss

- Helps optimize earnings during moderate conditions

- Automatically triggers payouts during severe disruptions

The key idea is that workers should not have to manually claim insurance. The system calculates everything based on real-world signals.

## Core Concept

The system works in three layers:

**1. Earnings Optimization**

During manageable disruptions, workers are guided to:

- better working hours
- safer zones
- higher demand areas

**2. Risk Compensation**

Workers receive additional incentives during difficult conditions such as heavy rain or heat.

**3. Insurance Protection**

During severe disruptions like floods, the system activates a disaster mode where:

- work is paused
- income is replaced through automated payouts

## System Workflow

1. **Collect Environmental Data**
   - Weather conditions  
   - Real-time alerts  

2. **Track Worker Activity**
   - Job activity  
   - Earnings data  

3. **Classify Situation**
   - Normal  
   - Moderate disruption  
   - Severe disruption  

4. **Apply Decision Logic**
   - Route optimization  
   - Incentive allocation  
   - Insurance payout calculation  

5. **Trigger Smart Actions**
   - Automatic payout if income loss exceeds threshold

**AI Risk Assessment and Fraud Detection**

This is a critical part of the system, especially considering the spoofing scenario.

**Goal**

To prevent fake claims while ensuring genuine workers are not affected.

## Adversarial Defense & Anti-Spoofing Strategy

To prevent GPS spoofing and coordinated fraud, our system does not rely on location alone. Instead, we look at overall user behavior, activity patterns, and regional consistency to understand whether a claim is genuine or manipulated.

### 1. The Differentiation

We differentiate between a real worker and a spoofed user by analyzing how they behave over time, not just where they appear to be.

A genuine worker usually:

- has consistent delivery activity before the disruption
- shows a gradual drop in earnings as conditions worsen
- follows realistic movement and app usage patterns
- behaves similarly to other workers in the same area

A fraudulent user usually:

- suddenly appears in a high-risk zone
- has little or no recent delivery activity
- shows unrealistic or static movement
- behaves very differently from nearby workers

The idea is simple: if the behavior doesn’t match real-world conditions, it gets flagged.

### 2. The Data

**How We Detect Fraud**

Instead of relying only on GPS, we use multiple data signals:

- historical earnings patterns
- delivery activity logs
- time spent online
- location consistency over time
- comparison with nearby workers
- regional demand patterns

### 3. AI Approach

We plan to use:

- anomaly detection models to identify unusual behavior
- clustering to compare workers in the same region
- rule-based validation for environmental triggers

### 4. The UX Balance

We don’t want genuine workers to suffer because of strict fraud checks.

**Handling Edge Cases**

1. We avoid directly rejecting claims.
2. If a claim is suspicious
   - mark as under review
   - allow partial payout
   - re-evaluate using additional data
     
This ensures fairness.

   This is important because:

   - network issues are common during bad weather
   - GPS can be inaccurate
   - real users can also behave irregularly during disruptions
     
We follow a verify-first approach before taking any rejection decision.

## Technical Architecture

**Frontend**
- React Native for mobile application
- Simple interface for workers to view earnings, risk, and payouts

**Backend**
- Node.js with NestJS for structured API development
- Handles business logic, risk evaluation, and payouts

**Database**
- PostgreSQL for structured data storage
- Stores user data, earnings history, policies, and transactions

**Real-Time Processing**
- Redis for caching and handling real-time event updates

**AI and Data Processing**
- Python for machine learning models
- Libraries such as scikit-learn, pandas, NumPy

**External APIs**
- Weather data using OpenWeather API
- Location services using Google Maps API


## Payment System Design

**How Payments Work** 
1. Workers pay a weekly premium
2. System maintains an insurance pool
3. Payouts are triggered automatically based on conditions

**Payment Security**
- We plan to integrate secure payment gateways such as
   - Razorpay
   - Stripe

**Security measures** 
- tokenized transactions
- encrypted communication
- no storage of sensitive card details

**Data Storage** 
- Payment records stored in PostgreSQL
- Sensitive data handled by payment gateway
- Only transaction references stored in our system

**Payout Handling** 
- Payouts triggered automatically
- Sent via UPI or bank transfer APIs
- Logged for audit and transparency

### Data Strategy

Since real platform data is not available, we use simulated datasets.

Data Includes:

- worker ID
- city
- expected income
- actual income
- working hours
- environmental conditions

Usage

- simulate disruptions
- test payout logic
- validate fraud detection

### Challenges Identified

- making the system realistic without relying on external jobs
- handling extreme cases like floods
- preventing fraud without penalizing genuine users
- balancing automation and fairness

### Future Scope

- integrate real delivery platform data
- improve AI models
- build real-time fraud detection pipelines
- deploy and test in real environments
