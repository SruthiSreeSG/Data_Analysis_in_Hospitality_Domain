# 🏨 Power BI Project: Hospitality Data Analytics Dashboard

An interactive Power BI dashboard built to analyze key metrics in the hospitality industry — including revenue, occupancy, cancellations, and platform-wise performance.

---

## 🧩 Problem

Hospitality businesses generate vast amounts of data across platforms (like Booking.com, Goibibo, etc.), cities, and property types. However, most struggle to:

- Monitor key performance indicators (KPIs) like Occupancy, Revenue, and RevPAR
- Understand cancellation/no-show trends across platforms
- Optimize pricing and inventory decisions

This project aims to **visualize and track KPIs** through a dynamic Power BI dashboard for better decision-making.

---

## 🔎 Exploration

### 📁 Dataset Summary

The dataset included:
- **Booking details**: revenue, platform, cancellation flag, no-show flag
- **Property metadata**: city, type, status
- **Timeline**: Monthly occupancy and revenue patterns

**KPIs focused on:**
- 💵 Revenue  
- 🛏️ Occupancy  
- 🧾 RevPAR (Revenue per Available Room)  
- 🟡 Realisation %  
- ❌ Cancellation & No-show rates

---

## 📊 Analysis & Dashboard Features

✅ Created interactive visuals to track:

| KPI                   | Description                                                  |
|------------------------|--------------------------------------------------------------|
| **Revenue (₹1.71B)**    | Total revenue across all properties                          |
| **Occupancy (0.58)**    | Rooms occupied / Rooms available                             |
| **RevPAR (₹7.35K)**     | Revenue per available room                                   |
| **Realisation % (70.15%)** | % of realized bookings out of total booked                |
| **Cancellation rate** | % of bookings cancelled per platform                          |
| **No-show rate**       | % of guests who did not arrive after booking                 |

---

## 🧠 DAX Measures Used

```DAX
-- Average Daily Rate (ADR)
ADR = SUM(Revenue) / SUM(Rooms_Occupied)

-- Cancellation Rate
Cancellation_Rate = 
    DIVIDE(
        COUNTROWS(FILTER(BookingData, BookingData[Cancelled] = "Yes")),
        COUNTROWS(BookingData)
    )

-- No-show Rate
NoShow_Rate = 
    DIVIDE(
        COUNTROWS(FILTER(BookingData, BookingData[No_Show] = "Yes")),
        COUNTROWS(BookingData)
    )

-- Realisation %
Realisation = 
    DIVIDE(
        COUNTROWS(FILTER(BookingData, BookingData[Status] = "Realised")),
        COUNTROWS(BookingData)
    )
```
---

## 📈 Dashboard Features
- 🎯 Slicers for platform, city, and property type
- 🕹️ Tooltips for KPI hover interactions
- 📊 Bar and line charts for monthly trends
- 📉 Drill-down filters for platform-wise revenue
- 🔄 Auto-refresh and dynamic filtering setup
---

## 🧾 Conclusion
- 🔍 Platform-wise insights revealed Booking.com generated the most revenue
- ❌ Goibibo had highest cancellation rates
- 📍 Properties in metro cities showed high RevPAR and realization %
- 📉 Adjusting pricing based on RevPAR & platform behavior can reduce loss
---

## 💻 Tools Used
✅ Power BI

✅ DAX

✅ Excel for preprocessing

