# Telegram Echo Bot

A Telegram bot built in Go that echoes various types of messages back to users with feedback collection functionality.

## Features

- **Multi-format Echo**: Replies with the same type of content received:
  - 📝 Text messages
  - 🎭 Stickers
  - 📷 Photos
  - 🎤 Voice messages
  - 🎥 Videos and video notes
  - 📄 Documents and audio files
  - 📍 Locations
  - 📊 Polls
  - 👤 Contact sharing

- **Command System**:
  - `/start` - Welcome message
  - `/help` - Show available commands
  - `/about` - Bot information
  - `/feedback <text>` - Submit feedback

- **Feedback Collection**:
  - Saves feedback to a local file (`feedback.txt`)
  - Forwards feedback to specified admin chat
  - File-based storage for simplicity

## Architecture
<pre>
TelegramEchoBot/
├── cmd/
│ └── bot/
│ └── main.go # Application entry point
├── internal/
│ ├── bot/
│ │ ├── bot.go # Bot initialization and main loop
│ │ └── handlers/ # Message handlers
│ │ ├── commands.go # Command processing
│ │ ├── messages.go # Regular message processing
│ │ └── feedback.go # Feedback handling
│ ├── config/
│ │ └── config.go # Configuration loading
│ └── storage/
│ └── feedback.go # Feedback storage
├── .env.example # Environment variables template
├── go.mod # Go module definition
└── go.sum # Dependency checksums
</pre>


## Getting Started

### Prerequisites
- Go 1.16+
- Telegram Bot Token (from [@BotFather](https://t.me/BotFather))

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/fa11astro/TelegramEchoBot.git
   cd TelegramEchoBot
2. **Install dependencies**
   ```bash
   go mod download
3. **Configure environment**
   ```bash
   cp .env.example.env
4. **Edit .env and add your Telegram Bot Token:**
   ```bash
   TELEGRAM_BOT_TOKEN=your_bot_token_here
5. **Run the bot**

## Technical Stack

- **Language**: Go 1.16+
- **Telegram API**: `go-telegram-bot-api` v5
- **Configuration**: `joho/godotenv`

## Development

### Project Structure Principles
- **`cmd/`**: Application entry points
- **`internal/`**: Private application code
- **`config/`**: Configuration management
- **`handlers/`**: Request processing logic
- **`storage/`**: Data persistence layer

## Limitations

- File-based storage (not suitable for production scale)
- No database integration
- Single admin chat for feedback
- Basic error handling

## Future Improvements

- [ ] Database integration for feedback storage
- [ ] Webhook support for production deployment
- [ ] Admin panel for feedback management
- [ ] Rate limiting and spam protection
- [ ] Docker containerization
- [ ] Unit and integration tests

Educational project. Free to use and modify.

Happy echoing! 🎯
