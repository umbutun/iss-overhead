# 🛰️ ISS Overhead Notifier

A Python script that tracks the International Space Station and sends an email alert when it's passing overhead at night — combining multiple APIs with automated notifications.

---

## Features

- **ISS Tracking:** Real-time position from Open Notify API
- **Sunrise/Sunset Data:** Determines if it's dark using Sunrise-Sunset API
- **Location Awareness:** Checks if ISS is within ±5° of your coordinates
- **Email Alerts:** Sends notification when conditions are met
- **Scheduled Checks:** Runs continuously, checking every 60 seconds

---

## How It Works

```
┌─────────────────────────────────────────────────┐
│                                                 │
│   1. Fetch ISS position (lat/long)              │
│                  ↓                              │
│   2. Compare to your location (±5° range)       │
│                  ↓                              │
│   3. Check if it's currently nighttime          │
│                  ↓                              │
│   4. If both true → Send email alert            │
│                  ↓                              │
│   5. Wait 60 seconds, repeat                    │
│                                                 │
└─────────────────────────────────────────────────┘
```

---

## APIs Used

| API | Purpose |
|-----|---------|
| [Open Notify](http://open-notify.org/Open-Notify-API/ISS-Location-Now/) | ISS current latitude/longitude |
| [Sunrise-Sunset](https://sunrise-sunset.org/api) | Dawn/dusk times for your location |

---

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/umbutun/iss-overhead.git
   cd iss-overhead
   ```

2. Update `main.py` with your details:
   ```python
   MY_LAT = 41.0082   # Your latitude
   MY_LONG = 28.9784  # Your longitude
   MY_EMAIL = "your_email@gmail.com"
   MY_PASSWORD = "your_app_password"
   ```

3. Run the script:
   ```bash
   python main.py
   ```

---

## Tech Stack

- **Python 3**
- **Requests** — API calls
- **smtplib** — Email sending
- **datetime** — Time comparisons

---

## What I Learned

- Working with multiple APIs in a single project
- Parsing JSON responses and extracting data
- Sending emails programmatically with SMTP
- Building a continuously running script with scheduled checks
- Combining conditions from different data sources

---

## Part Of

🐍 [100 Days of Code — Python Projects](https://github.com/umbutun/python-100-days-of-code)

---

## License

[MIT License](LICENSE)
