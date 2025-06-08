# Bitwarden CLI Cheat Sheet

## Account Management

| Command | Description |
|--------|-------------|
| `bw login <email>` | Log in to a Bitwarden account (prompts for master password) |
| `bw logout` | Log out of the current session |
| `bw unlock` | Unlock the vault (prompts for master password or session key) |
| `bw lock` | Lock the vault |
| `bw status` | Show current login and vault status |

## Session Management

> **Important**: You must export the session key after unlocking to use most commands:

```bash
export BW_SESSION=$(bw unlock --raw)
```

| Command | Description |
|--------|-------------|
| `bw unlock --raw` | Unlock the vault and return session key |
| `export BW_SESSION=$(bw unlock --raw)` | Store session key in environment variable |
| `bw logout` | End session and clear all local data |

## Item Management

| Command | Description |
|--------|-------------|
| `bw list items` | List all items in the vault |
| `bw get item <item_id>` | Get full item data by ID |
| `bw get item <name>` | Get item by name (returns first match) |
| `bw create item <json>` | Create a new item using JSON input |
| `bw edit item <item_id> <json>` | Edit an existing item using JSON input |
| `bw delete item <item_id>` | Delete an item by ID |
| `bw list items --search <term>` | Search for items containing the term |

## Vault Organization

| Command | Description |
|--------|-------------|
| `bw list folders` | List all folders |
| `bw create folder <json>` | Create a folder (JSON format: `{"name": "Folder Name"}`) |
| `bw delete folder <folder_id>` | Delete a folder |
| `bw list collections` | List collections (if using an organization) |
| `bw list organizations` | List available organizations |

## Utilities

| Command | Description |
|--------|-------------|
| `bw sync` | Sync vault data with Bitwarden server |
| `bw config server <url>` | Set the server URL (self-hosted instances) |
| `bw encode <string>` | Base64 encode a string (useful for template input) |
| `bw decode <string>` | Base64 decode a string |
