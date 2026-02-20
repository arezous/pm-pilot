# Environment Keys Setup

Configure API keys for the tools you'll use with your PM Operating System.

## Why You Need This

The PM OS can integrate with various services to supercharge your workflow:

- **OpenAI** — For testing prompts across GPT models
- **Google Gemini** — Alternative LLM for comparison
- **MCP Servers** — Connect to Slack, Google Drive, Reddit, etc.

You don't need all of these. Set up what you'll actually use.

---

## Quick Start

### 1. Create your `.env` file

Copy the template to create your local environment file:

```bash
cp setup/.env.example .env
```

> **Important:** The `.env` file contains secrets. Never commit it to git.

### 2. Add your keys

Open `.env` and fill in the keys for the services you want to use.

---

## API Keys Reference

### OpenAI

| Variable | Description |
|---|---|
| `OPENAI_API_KEY` | Your OpenAI API key |

**How to get it:**
1. Go to [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
2. Click "Create new secret key"
3. Copy the key and paste it into your `.env` file

**Use case:** Compare GPT model outputs against Claude for prompt testing and benchmarking.

---

### Google Gemini

| Variable | Description |
|---|---|
| `GOOGLE_GEMINI_API_KEY` | Your Google AI Studio API key |

**How to get it:**
1. Go to [aistudio.google.com/apikey](https://aistudio.google.com/apikey)
2. Click "Create API Key"
3. Copy the key and paste it into your `.env` file

**Use case:** Alternative LLM for comparison testing and multi-model validation.

---

### MCP Servers

MCP (Model Context Protocol) servers let you connect external tools directly into your workflow.

#### Slack

| Variable | Description |
|---|---|
| `SLACK_BOT_TOKEN` | Bot user OAuth token (`xoxb-...`) |
| `SLACK_TEAM_ID` | Your Slack workspace ID |

**How to get it:**
1. Go to [api.slack.com/apps](https://api.slack.com/apps)
2. Create a new app or select an existing one
3. Navigate to **OAuth & Permissions**
4. Copy the **Bot User OAuth Token**
5. Find your Team ID in your workspace URL or admin settings

#### Google Drive

| Variable | Description |
|---|---|
| `GOOGLE_CLIENT_ID` | OAuth 2.0 client ID |
| `GOOGLE_CLIENT_SECRET` | OAuth 2.0 client secret |

**How to get it:**
1. Go to [console.cloud.google.com](https://console.cloud.google.com)
2. Create or select a project
3. Enable the Google Drive API
4. Create OAuth 2.0 credentials under **APIs & Services > Credentials**

#### Reddit

| Variable | Description |
|---|---|
| `REDDIT_CLIENT_ID` | Reddit app client ID |
| `REDDIT_CLIENT_SECRET` | Reddit app client secret |

**How to get it:**
1. Go to [reddit.com/prefs/apps](https://www.reddit.com/prefs/apps)
2. Click "Create an app" (select "script" type)
3. Copy the client ID and secret

**Use case:** Monitor subreddits for customer sentiment, competitor mentions, and market trends.

---

## Verifying Your Setup

After adding your keys, verify they're loaded:

```bash
# Check that your .env file exists and has content
cat .env | grep -c "="

# Test a specific key is set (without revealing it)
echo ${OPENAI_API_KEY:+OpenAI key is set}
echo ${GOOGLE_GEMINI_API_KEY:+Gemini key is set}
echo ${SLACK_BOT_TOKEN:+Slack key is set}
```

---

## Security Reminders

- Never commit `.env` to version control
- Ensure `.env` is listed in your `.gitignore`
- Rotate keys if you suspect they've been exposed
- Use the minimum required permissions for each service
- Keep keys in `.env` only — do not hardcode them in scripts or documents
