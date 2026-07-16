# Merchant Churn Risk Dashboard

## Project Overview

This project implements a simple dashboard that identifies merchants at risk of churning and provides actionable retention recommendations. Built as part of the CX AI-Proficiency Build Round, the solution demonstrates end-to-end thinking from problem definition to functional prototype using only HTML, CSS, and JavaScript.

## What Was Built

### 1. Specification Document (`v1-spec.md`)
- Defined the merchant record schema with fields like ID, name, dates, transaction volumes, engagement metrics, and support data
- Established clear churn risk signals based on observable merchant behaviors
- Created a risk scoring system that translates multiple factors into actionable risk levels
- Designed appropriate next-step recommendations tailored to different risk profiles and primary risk factors

### 2. Interactive Dashboard (`index.html`)
A single-page application featuring:

**Data Generation**
- Realistic mock merchant data simulating various business types and risk profiles
- Correlated metrics (e.g., higher transaction volumes tend to correlate with more customers)
- Varied plan tiers (Basic, Pro, Enterprise) based on transaction volume

**Risk Assessment Engine**
- Calculates risk scores (0-100) based on four key signals:
  * Transaction volume decline (>20% drop)
  * Platform inactivity (>14 days without login)
  * Low engagement (<2 logins/week AND <15 customers)
  * High support load (>3 tickets in 30 days)
- Categorizes risk into Low (0-25), Medium (26-50), and High (51+) tiers
- Identifies the primary contributing risk factor for each merchant

**User Interface**
- Clean, professional design with visual hierarchy and responsive layout
- Interactive controls for filtering by risk level and plan tier
- Multiple sorting options (risk score, name, last activity, transaction volume)
- Statistics dashboard showing key metrics at a glance
- Color-coded risk badges and plan indicators for quick visual assessment
- Tooltips providing full action recommendations on hover
- Smooth animations and loading states for enhanced user experience

**Key Features**
- Merchant table displaying all relevant metrics with proper formatting
- Real-time filtering and sorting without page reloads
- Visual stats cards showing total merchants and risk distribution
- Actionable recommendations specific to each merchant's risk profile
- Mobile-responsive design that adapts to different screen sizes
- Zero dependencies - pure HTML/CSS/JS that runs in any modern browser

## Technical Approach

### Frontend Implementation
- Semantic HTML5 structure for accessibility and SEO
- Modern CSS3 with CSS variables for consistent theming
- Flexbox and Grid layouts for responsive design
- Vanilla JavaScript ES6+ for DOM manipulation and logic
- Event-driven architecture for interactive components
- CSS animations and transitions for polished user experience

### Design Decisions
- **No Frameworks**: Chose vanilla technologies to demonstrate core web development skills
- **Client-Side Only**: All logic runs in the browser, making deployment simple
- **Mock Data Approach**: Generated realistic data locally since no dataset was provided
- **Progressive Enhancement**: Basic functionality works without JS, enhanced with JS
- **Accessibility**: Proper color contrast, keyboard navigable elements, semantic markup

### Risk Logic Details
The scoring algorithm weighs different risk factors:
- Volume decline: up to 40 points (weighted by severity)
- Inactivity: up to 30 points (weighted by days inactive)
- Low engagement: up to 20 points (based on login frequency and customer count)
- Support load: up to 10 points (based on ticket volume)

This creates a nuanced risk assessment where merchants with multiple mild issues might score similarly to those with one severe issue.

## How to Use

1. Open `index.html` in any modern web browser
2. The dashboard automatically loads with generated merchant data
3. Use the filter controls to narrow down by risk level or plan tier
4. Change sorting options to view data in different orders
5. Hover over action buttons to see full retention recommendations
6. Click "Refresh Data" to generate a new set of mock merchants

## Customization Points

The dashboard is designed for easy adaptation:
- **Risk Logic**: Modify `calculateRiskScore()` function to adjust weights or thresholds
- **Recommendations**: Update `getRecommendedAction()` for different business contexts
- **Data Generation**: Edit `generateMockMerchants()` to simulate different merchant populations
- **Styling**: Adjust CSS variables in the `:root` section for branding
- **Metrics**: Add or remove fields in the merchant objects and corresponding table columns

## Files in This Repository

- `index.html` - The complete dashboard application
- `v1-spec.md` - Initial specification document detailing the problem approach
- `README.md` - This documentation file

## Built With

- HTML5
- CSS3 (with CSS variables and modern layout techniques)
- JavaScript ES6+ (vanilla, no frameworks)
- Google Fonts (Inter, via system font stack)

## Conclusion

This project demonstrates the ability to take an open-ended requirement, define clear specifications, implement a functional solution, and create a polished user experience—all using foundational web technologies. The dashboard provides tangible value by translating abstract churn risks into concrete, actionable insights for merchant retention teams.