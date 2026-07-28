# DAX Measures Documentation

| Measure | Category | Business Purpose | Used In |
|---------|----------|------------------|---------|
| Total Bookings | Operational KPI | Tracks the total number of hotel bookings. | Operational Dashboard |
| Average ADR | Operational KPI | Measures the average booking value per day (Average Daily Rate). | Operational Dashboard |
| Average Nights Stayed | Operational KPI | Calculates the average duration of guest stays. | Operational Dashboard |
| Cancelled Bookings | Operational KPI | Counts the total number of cancelled bookings. | Both Dashboards |
| Cancellation Rate | Operational KPI | Measures the percentage of bookings that were cancelled. | Both Dashboards |
| Estimated Booking Revenue | Commercial KPI | Estimates the total potential revenue generated from all bookings. | Commercial Dashboard |
| Revenue at Risk | Commercial KPI | Quantifies the estimated revenue associated with cancelled bookings. | Commercial Dashboard |
| Revenue at Risk (%) | Commercial KPI | Measures the proportion of total revenue exposed to cancellations. | Commercial Dashboard |
| Average Revenue per Booking | Commercial KPI | Calculates the estimated average revenue generated per booking. | Commercial Dashboard |

## Operational KPIs

### Total Bookings

**Purpose**

Counts the total number of hotel bookings.

```DAX
Total Bookings = COUNTROWS('Hotel Bookings')
```

---

### Average ADR

**Purpose**

Calculates the average daily rate across all bookings.

```DAX
Average ADR = AVERAGE('Hotel Bookings'[adr])
```

---

### Average Nights Stayed

**Purpose**

Calculates the average duration of guest stays.

```DAX
Average Nights Stayed =
AVERAGE('Hotel Bookings'[Total Nights])
```

---

### Cancelled Bookings

**Purpose**

Counts the total number of cancelled bookings.

```DAX
Cancelled Bookings =
CALCULATE(
    COUNTROWS('Hotel Bookings'),
    'Hotel Bookings'[is_canceled] = 1
)
```

---

### Cancellation Rate

**Purpose**

Measures the percentage of bookings that were cancelled.

```DAX
Cancellation Rate =
DIVIDE(
    [Cancelled Bookings],
    [Total Bookings]
)
```

---

## Commercial KPIs

### Estimated Booking Revenue

**Purpose**

Estimates the potential revenue generated from all bookings.

```DAX
Estimated Booking Revenue =
SUMX(
    'Hotel Bookings',
    'Hotel Bookings'[adr] * 'Hotel Bookings'[Total Nights]
)
```

---

### Revenue at Risk

**Purpose**

Calculates the estimated revenue associated with cancelled bookings.

```DAX
Revenue at Risk =
CALCULATE(
    [Estimated Booking Revenue],
    'Hotel Bookings'[is_canceled] = 1
)
```

---

### Revenue at Risk %

**Purpose**

Measures the proportion of total booking revenue associated with cancelled bookings.

```DAX
Revenue at Risk % =
DIVIDE(
    [Revenue at Risk],
    [Estimated Booking Revenue]
)
```

---

### Average Revenue per Booking

**Purpose**

Calculates the estimated average revenue generated per booking.

```DAX
Average Revenue per Booking =
DIVIDE(
    [Estimated Booking Revenue],
    [Total Bookings]
)
```

---

# Business Value

These measures enabled the development of executive KPIs that answered operational questions while also quantifying the commercial impact of booking cancellations.

The Commercial Impact Dashboard demonstrated that approximately **$16.73 million** in estimated booking revenue was associated with cancelled reservations, providing management with a measurable indicator of potential revenue leakage and supporting data-driven recommendations for improving revenue protection and customer retention.
