#  AutoMessager – Smart Scheduled Messaging Hub

AutoMessager is a lightweight, client-side web application that lets you **schedule and automate messages** with real-time delivery simulation. Perfect for reminders, follow-ups, or testing message automation workflows — all running directly in your browser with persistent storage.

<img width="1886" height="1104" alt="image" src="https://github.com/user-attachments/assets/3f6721e6-2a71-43ee-83b5-1df44639c9c5" />

## Features

- ** Schedule Messages** – Set exact date & time for any message delivery.
- ** Recurring Messages** – Choose hourly, daily, or weekly repeats (automatically reschedules).
- ** Auto-Delivery Simulation** – Background checker sends messages when scheduled time arrives.
- ** Persistent Queue** – All schedules saved to `localStorage` (survives page refresh).
- ** Manage Messages** – Delete individual items or clear entire queue.
- ** Responsive Design** – Works on desktop, tablet, and mobile devices.
- ** Real-Time Status** – Visual indicators for pending, sent, or failed messages.
- ** Live Badge** – Shows that the auto-sender is actively monitoring.


### Quick Start
1. Enter recipient name/ID, message content, and scheduled time.
2. Choose repeat option (optional).
3. Click "Schedule Auto-Message".
4. The system automatically sends messages when time arrives (checks every 15 seconds).

##  Tech Stack

- **HTML5** – Semantic structure
- **CSS3** – Modern gradients, glassmorphism effects, responsive grid
- **JavaScript (ES6)** – Core logic, scheduling, localStorage persistence
- **No dependencies** – Pure vanilla implementation

##  Project Structure

```
automessager/
├── index.html          # Main application (single file)
└── README.md           # Documentation
```

> **Note:** This is a single-file application – just open `index.html` in any modern browser.

##  Installation & Usage

### Local Setup
```bash
# Clone the repository
git clone https://github.com/yourusername/automessager.git

# Navigate to project folder
cd automessager

# Open index.html (double-click or use live server)
open index.html
```

### Using with Live Server (recommended for development)
```bash
npx live-server
```

##  How It Works

1. **Scheduling** – User fills form → new message object added to `schedules` array with target timestamp.
2. **Persistence** – Every change saved to `localStorage` for data retention.
3. **Background Checker** – Interval function runs every 15 seconds, compares current time with scheduled timestamps.
4. **Auto-Send** – When `Date.now() >= scheduledTimestamp`, message status updates to "sent" and is logged to console.
5. **Recurrence** – If repeat rule exists, a new schedule is automatically created with next occurrence timestamp.
6. **UI Update** – Real-time rendering with color-coded status badges.

##  Use Cases

-  **Meeting Reminders** – Schedule Slack/email reminders (integrate with webhooks).
-  **SMS Follow-ups** – Connect to Twilio API (extend the `processSend` function).
-  **Testing Automation** – Simulate message queues without external services.
-  **Daily Motivation** – Auto-send inspirational quotes.
-  **Recurring Tasks** – Hourly/daily team check-ins.

## 🔌 Extending to Real APIs

The current version simulates delivery (console log + status update). To connect with real messaging services:

```javascript
// Modify processSend() function in index.html
async function processSend(schedule) {
  // Example: Send via WhatsApp Business API
  await fetch('https://your-api.com/send', {
    method: 'POST',
    body: JSON.stringify({
      to: schedule.recipient,
      message: schedule.message
    })
  });
  // Update status accordingly
}
```

Integration ideas:
- **Twilio** (SMS/WhatsApp)
- **Telegram Bot API**
- **Slack Webhooks**
- **Email (SMTP)**

## Future Improvements

- [ ] Custom repeat intervals (every X hours/days)
- [ ] Edit scheduled messages
- [ ] Export/import schedules (JSON)
- [ ] Dark mode toggle
- [ ] Push notifications when message is sent
- [ ] Timezone support
- [ ] Webhook triggers on send

## Contributing

Contributions are welcome! Follow these steps:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please ensure your code follows the existing style and includes appropriate comments.

## License

Distributed under the MIT License. See `LICENSE` file for more information.

## Acknowledgments

- Icons and design inspiration from modern SaaS dashboards
- Glassmorphism UI trends
- LocalStorage API for seamless client-side persistence

##  Contact

Your Name – [@yourtwitter](https://twitter.com/yourtwitter) – email@example.com

Project Link: [https://github.com/yourusername/automessager](https://github.com/yourusername/automessager)

---

**⭐ Star this repository if you find it useful!**  
Report issues or suggest features via [GitHub Issues](https://github.com/yourusername/automessager/issues).
```
