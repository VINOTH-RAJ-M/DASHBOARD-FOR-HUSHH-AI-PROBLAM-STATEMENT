# Campus Ambassador Growth Dashboard - Dataset Documentation

## 📊 Dataset Overview

This comprehensive dataset is designed for building a **Campus Ambassador Growth Dashboard** for hackathons, analytics projects, or data visualization challenges.

**Dataset Created:** March 2024  
**Time Period:** January 2024 - March 2024  
**Total Ambassadors:** 50  
**Total Events:** 77  
**Total Sign-ups Tracked:** 15,000+

---

## 📁 Files Included

### 1. **ambassadors.csv** (Main Dataset)
**50 rows** - Core information about each campus ambassador

**Columns:**
- `ambassador_id` - Unique identifier (AMB001-AMB050)
- `name` - Ambassador's full name
- `email` - Contact email
- `phone` - Contact number
- `college` - College/university name
- `city` - City location
- `state` - State location
- `region` - Geographic region (North/South/East/West/Central)
- `join_date` - Date they joined the program
- `status` - Current status (Active/Inactive)
- `total_signups` - Total sign-ups they've generated
- `total_events` - Total events they've conducted
- `social_media_reach` - Total social media reach
- `engagement_score` - Overall engagement score (0-100)
- `performance_tier` - Performance category (High/Medium/Low)
- `last_active_date` - Last activity date

**Key Insights:**
- 47 Active ambassadors, 3 Inactive
- Performance ranges from 22 (inactive) to 92 (top performer)
- Geographic distribution across all regions
- Mix of IITs, NITs, and other premier institutions

---

### 2. **events.csv**
**77 rows** - Detailed information about events conducted

**Columns:**
- `event_id` - Unique event identifier (EVT001-EVT077)
- `ambassador_id` - Who organized it
- `event_name` - Event title
- `event_type` - Type (Workshop/Seminar/Competition/Demo/Exhibition/etc.)
- `event_date` - When it happened
- `attendees` - Number of attendees
- `signups_generated` - Sign-ups from the event
- `college` - Where it was held
- `city` - City location
- `duration_hours` - Event duration
- `budget_spent` - Budget in rupees
- `event_rating` - Satisfaction rating (out of 5)

**Event Types:**
- Workshop (most common)
- Seminar
- Competition/Hackathon
- Demo/Exhibition
- Meetup/Networking
- Conference/Festival

**Key Metrics:**
- Average attendees: ~75 per event
- Average rating: 4.3/5
- Total budget spent: ₹2.5L+

---

### 3. **daily_signups.csv**
**70 rows** - Daily sign-up data from Jan 15 to Mar 24, 2024

**Columns:**
- `date` - Date
- `total_signups` - Total sign-ups that day
- `organic` - Organic (non-ambassador) sign-ups
- `ambassador_driven` - Sign-ups credited to ambassadors
- `region_north/south/east/west/central` - Regional breakdown

**Key Patterns:**
- Clear upward growth trend
- Ambassador-driven sign-ups account for ~74% of total
- North and South regions lead in performance
- Weekday vs weekend patterns visible

**Use Cases:**
- Time-series growth charts
- Trend analysis
- Regional comparison
- Forecasting models

---

### 4. **social_engagement.csv**
**150 rows** - Social media metrics (3 platforms × 50 ambassadors)

**Columns:**
- `ambassador_id` - Ambassador identifier
- `platform` - Social platform (Instagram/LinkedIn/Twitter)
- `followers` - Follower count
- `posts_this_month` - Posts in current month
- `likes_avg` - Average likes per post
- `comments_avg` - Average comments per post
- `shares_avg` - Average shares per post
- `engagement_rate` - Engagement percentage
- `top_post_reach` - Best-performing post reach

**Platforms Covered:**
- Instagram (highest engagement)
- LinkedIn (professional reach)
- Twitter (fastest updates)

**Key Metrics:**
- Average engagement rate: 7-12%
- Top performers have 15,000+ reach
- Platform-specific performance patterns

---

### 5. **monthly_performance.csv**
**140 rows** - Monthly tracking of ambassador performance

**Columns:**
- `ambassador_id` - Ambassador identifier
- `month` - Month (2024-01, 2024-02, 2024-03)
- `signups` - Sign-ups that month
- `events` - Events conducted
- `active_days` - Days active in the month
- `response_rate` - Response rate percentage
- `satisfaction_score` - Performance rating
- `tasks_completed` - Tasks completed
- `tasks_assigned` - Tasks assigned

**Use Cases:**
- Month-over-month growth
- Ambassador productivity trends
- Identifying declining performance
- Workload analysis

---

### 6. **colleges.csv**
**50 rows** - College/institution summary data

**Columns:**
- `college` - College name
- `city` - City
- `state` - State
- `region` - Geographic region
- `total_ambassadors` - Number of ambassadors
- `active_ambassadors` - Currently active
- `total_signups` - Cumulative sign-ups
- `total_events` - Cumulative events
- `avg_performance_score` - Average score
- `tier` - Institution tier (Premium/Standard)

**Institution Types:**
- 20 Premium tier (IITs, top NITs)
- 30 Standard tier (other colleges)

---

## 🎯 Dashboard Use Cases

### **Key Visualizations You Can Build:**

1. **Overview Dashboard**
   - Total ambassadors (active vs inactive)
   - Total sign-ups with growth trend
   - Events conducted
   - Top performers leaderboard

2. **Growth Analytics**
   - Line chart: Daily sign-ups over time
   - Area chart: Regional growth comparison
   - Bar chart: Month-over-month growth

3. **Geographic Analysis**
   - India map with regional performance
   - State-wise distribution
   - City-wise ambassador density

4. **Performance Metrics**
   - Scatter plot: Events vs Sign-ups
   - Heatmap: Ambassador activity calendar
   - Gauge charts: Engagement scores

5. **Social Media Dashboard**
   - Platform comparison (Instagram vs LinkedIn vs Twitter)
   - Engagement rate trends
   - Top posts/viral content

6. **Event Analytics**
   - Event types distribution (pie chart)
   - Attendees vs Sign-ups correlation
   - ROI analysis (budget vs sign-ups)
   - Rating trends

7. **College/Institution View**
   - Premium vs Standard tier comparison
   - Top-performing colleges
   - Regional strength analysis

8. **Alerts & Warnings**
   - Inactive ambassadors (>14 days)
   - Declining performance
   - Low engagement alerts

---

## 💡 Sample Insights from Data

### **Top Performers:**
1. AMB001 (Rahul Sharma, IIT Delhi) - 245 sign-ups
2. AMB006 (Ananya Singh, IIT Bombay) - 223 sign-ups
3. AMB004 (Sneha Reddy, IIT Madras) - 198 sign-ups

### **Inactive Ambassadors:**
- AMB011, AMB022, AMB029, AMB043 (need re-engagement)

### **Regional Performance:**
1. North: 40% of total sign-ups
2. South: 35%
3. West: 20%
4. East: 5%

### **Event Success:**
- Hackathons generate most sign-ups (~50 per event)
- Workshops have best ratings (4.5+)
- Demos have lowest cost per sign-up

---

## 🚀 Quick Start Guide

### **For React Dashboard:**
```javascript
import Papa from 'papaparse';

// Load ambassadors data
Papa.parse(ambassadorsFile, {
  header: true,
  complete: (results) => {
    const activeAmbassadors = results.data.filter(a => a.status === 'Active');
    // Build your dashboard!
  }
});
```

### **For Python Analysis:**
```python
import pandas as pd

# Load data
ambassadors = pd.read_csv('ambassadors.csv')
events = pd.read_csv('events.csv')
daily = pd.read_csv('daily_signups.csv')

# Quick stats
print(f"Total Active: {len(ambassadors[ambassadors.status=='Active'])}")
print(f"Total Sign-ups: {ambassadors.total_signups.sum()}")
```

### **Sample Queries:**

**Top 5 Performers:**
```sql
SELECT name, college, total_signups 
FROM ambassadors 
WHERE status = 'Active' 
ORDER BY total_signups DESC 
LIMIT 5;
```

**Event ROI:**
```sql
SELECT event_name, signups_generated, budget_spent,
       (signups_generated * 100.0 / budget_spent) as roi
FROM events
ORDER BY roi DESC;
```

---

## 🎨 Recommended Tech Stack

**Frontend:**
- React.js + Tailwind CSS
- Chart.js or Recharts for visualizations
- Material-UI or shadcn/ui for components

**Backend (if needed):**
- Node.js + Express (simple API)
- Python Flask (data processing)

**Deployment:**
- Vercel/Netlify (frontend)
- Mock data (no backend needed for hackathon)

---

## 📈 Data Quality Notes

✅ **Realistic Data:**
- Real Indian colleges and cities
- Believable performance distributions
- Realistic engagement metrics
- Natural growth patterns

✅ **Edge Cases Included:**
- Inactive ambassadors
- Varying performance levels
- Regional imbalances
- Budget variations

✅ **Complete Coverage:**
- All regions of India
- Multiple institution tiers
- Various event types
- 3 months of time-series data

---

## 🏆 Hackathon Tips

1. **Focus on Visual Impact:** Beautiful charts > Complex features
2. **Tell a Story:** Show growth journey, not just numbers
3. **Add Interactivity:** Filters, search, drill-downs
4. **Highlight Problems:** Show inactive ambassadors, declining regions
5. **Unique Feature:** Add AI insights or predictions

**Good Luck! 🚀**

---

## 📞 Support

If you need more data or different formats, feel free to ask!

---

**Dataset Version:** 1.0  
**Last Updated:** March 24, 2024  
**License:** Free to use for educational/hackathon purposes
