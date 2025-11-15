# CIA BlackWatch (Discord Bot) - Scaffold
# CIA BlackWatch (Discord Bot) - Scaffold

Base scaffold for **CIA BlackWatch**, an advanced Discord security bot (Discord.js v14). This repo contains a working skeleton implementing handlers, SQLite storage, basic detectors and a Lockdown/Normality flow with a test command.

Quick start

1. Install dependencies:

```bash
npm install
```

2. Configure the bot token as an environment variable named `DISCORD_TOKEN` (do NOT paste tokens into source files):

```bash
export DISCORD_TOKEN="your_bot_token_here"
npm start
```

Files of interest

- `src/index.js` - bot entrypoint
- `src/handlers` - command & event loaders
- `src/commands` - slash commands (Test_AutoLockdown, normality, embed, safe_roles, safe_bots)
- `src/events` - event listeners
- `src/actions/lockdown.js` - Lockdown / Normality logic
- `src/data/db.js` - SQLite wrapper (data/file.db)

Command deployment
 - Use `deploy-commands.js` to register commands via the REST API. Set these env vars before running:
	 - `DISCORD_TOKEN` — your bot token
	 - `CLIENT_ID` — your application ID
	 - `GUILD_ID` — optional; if set, commands are registered to that guild. If not set, commands are registered globally.

	Example (guild deploy):
	```bash
	export DISCORD_TOKEN="..."
	export CLIENT_ID="123456789012345678"
	export GUILD_ID="987654321098765432"
	node deploy-commands.js
	```

	Example (global deploy):
	```bash
	export DISCORD_TOKEN="..."
	export CLIENT_ID="123456789012345678"
	unset GUILD_ID
	node deploy-commands.js
	```

Notes

- This is a scaffold and demonstration of the requested features. For production use you must review permissions, intents, and run the bot with a dedicated service account with correct privileges. Some actions (modifying roles above the bot, owner protections) may fail due to Discord permission hierarchies.
- IMPORTANT: Never paste your bot token in code or public channels. The token provided in the conversation should be considered compromised and must be revoked immediately. Use `DISCORD_TOKEN` or a secrets manager.

# CIA-DISCORD-BOT
THIS IS NOT CENTRAL INTELLIGENCE AGENCY. This is just a similar project name.
