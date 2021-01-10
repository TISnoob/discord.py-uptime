# discord-uptime
Discord bot to monitor uptime and ping addresses

Built using discord.py 1.6.x, ping3 and aiohttp

## Installation
**Requires Python 3.6+**

Install dependencies: 

`pip install -r requirements.txt`

Bot setup (Rename config.example.json and edit the default values):
* `token` - Discord bot token
* `prefix` - Discord bot prefix
* `notification_channel` - Channel ID where down/up notifications will be sent
* `role_to_mention` - Role ID which will be tagged in down/up notifications
* `secs_between_ping` - How many seconds between each uptime check
* `http_timeout` - How many seconds before a HTTP request should timeout

No privileged intents are currently needed to run the bot.

## Servers Configuration
Servers should be setup similar to the examples already in `server.json`:
* There are two supported types: `http` and `ping`
```json
[
    {
      "name": "Google",
      "type": "http",
      "address": "google.com"
    },
    {
      "name": "Cloudflare",
      "type": "ping",
      "address": "1.1.1.1"
    }
]
```

## Commands
> Default Prefix: >

* `ping <address> [pings]` - Pings an address once, or for the amount specified via pings and returns the delay in ms
* `http <address>` - Performs a HTTP request to the specified address and returns the response code
* `status` - Displays the status of all servers setup in `servers.json`

## Screenshots
> Status Command

![status](https://i.gyazo.com/6d5e0c4fbdb5ff52619d86eef827e369.png)
> Uptime & Downtime Notifications

![uptime](https://i.gyazo.com/803aebfcb3833ac8de7bd38e18378a29.png)