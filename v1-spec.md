# v1 Spec Doc: Merchant Churn Dashboard

## Problem Understanding
Build a simple dashboard that flags merchants at risk of churning and recommends a next step for each one.

## Merchant Record Shape
Each merchant record will contain:
- `id`: Unique identifier (string)
- `name`: Merchant business name (string)
- `signupDate`: Date when merchant joined platform (ISO string)
- `lastActivityDate`: Date of last transaction or login (ISO string)
- `monthlyTransactionVolume`: Average monthly transaction count (number)
- `transactionVolumeTrend`: Percentage change in volume over last 3 months (number, can be negative)
- `loginFrequency`: Average logins per week over last month (number)
- `supportTicketCount`: Number of support tickets in last 30 days (number)
- `customerCount`: Number of unique customers served (number)
- `planTier`: Subscription level (string: "basic", "pro", "enterprise")

## Churn Signals Definition
A merchant is flagged as at-risk if they meet ANY of these conditions:
1. **Volume Decline**: transactionVolumeTrend < -30% (significant drop in transactions)
2. **Inactivity**: No login in last 14 days (based on lastActivityDate)
3. **Low Engagement**: loginFrequency < 2 AND customerCount < 10 (minimal platform usage)
4. **High Support Load**: supportTicketCount > 5 (indicates frustration/issues)

## Risk Scoring & Flagging
Each condition contributes to a risk score:
- Volume Decline: 40 points
- Inactivity: 30 points  
- Low Engagement: 20 points
- High Support Load: 10 points

Risk levels:
- **Low Risk**: 0-30 points (monitor)
- **Medium Risk**: 31-60 points (recommend outreach)
- **High Risk**: 61+ points (immediate action required)

## Recommended Next Steps
Based on risk level and primary signal:
- **Low Risk**: "Schedule quarterly check-in"
- **Medium Risk - Volume Decline**: "Offer performance review & optimization consultation"
- **Medium Risk - Inactivity**: "Re-engagement email with new feature highlights"
- **Medium Risk - Low Engagement**: "Provide onboarding refresher & usage tips"
- **Medium Risk - High Support Load**: "Assign dedicated support agent for issue resolution"
- **High Risk**: "Immediate account manager intervention + retention offer"

## Dashboard Features
- Merchant table showing: Name, Risk Level, Primary Risk Factor, Recommended Action
- Filter controls: By risk level, by plan tier
- Sort controls: By risk score, by name, by last activity
- Summary stats: Total merchants, at-risk count, breakdown by risk level
- Color-coded risk indicators (green/yellow/red)

## Technical Approach
- Single-page HTML/CSS/JavaScript application (no framework for simplicity)
- Mock data generated locally (since no dataset provided)
- LocalStorage for persistence (if needed)
- Responsive design for desktop viewing
- Hosted on GitHub Pages for submission

## Success Criteria
- Dashboard loads and displays merchant data correctly
- At-risk merchants are properly flagged based on defined signals
- Recommended next steps are appropriate and actionable
- Interface is clean, readable, and usable
- All requirements from brief are addressed: merchant record shape defined, churn signals identified, next steps recommended