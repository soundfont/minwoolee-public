# minwoolee Discord Bot

**minwoolee** is a private Discord bot designed for **server moderation**, **utility tasks**, and **interactive features**. It provides commands for managing messages, moderating members, viewing detailed moderation history, and displaying server statistics — all with a clean, consistent embed format that includes the server icon.

> This bot is still a work in progress as new features and commands are actively being developed by the collaborators.

---

## Features

-   **Command Prefix:** `.`
-   **Moderation Tools:**
    -   Kick, ban, unban, timeout (with flexible duration), untimeout members.
    -   Purge messages.
    -   Comprehensive moderation history tracking (`.history` for actions against a member, `.moderationhistory` for actions by a staff member).
    -   View list of banned users (`.bans`).
-   **Utility Tools:**
    -   Display counts of humans, bots, and total members (`.membercount`).
    -   Check bot latency (`.ping`).
    -   Set AFK status (`.afk`).
    -   Help command linking to documentation (`.help`).
-   **Interactive Features:**
    -   Automatic message reactions for "y/n" and "v/s" phrases (from `reactor.py`).
-   **Clean Embeds:** All embed messages display the server icon (if available) as a thumbnail for consistent branding, facilitated by a central `Utils` cog.
-   **Database Integration:** Uses PostgreSQL for persistent storage of moderation logs.

---

## Command Reference

**Command**: `<name>`
**Alias**: `<alias if applicable>`
**Description**: `<what the command does>`
**Usage**: `<syntax>`
**Permissions**: `<required Discord permissions>`

---

### `.ping`

-   **Description:** Shows the bot's latency in milliseconds.
-   **Usage:** `.ping`
-   **Permissions:** None

---

### `.purge <amount>`

-   **Description:** Deletes a specified number of messages (1–100).
-   **Usage:** `.purge 25`
-   **Permissions:** Manage Messages

---

### `.kick <@user> [reason]`

-   **Description:** Kicks a member from the server.
-   **Usage:** `.kick @User Spamming`
-   **Permissions:** Kick Members

---

### `.ban <@user> [reason]`

-   **Description:** Bans a member from the server.
-   **Usage:** `.ban @User Inappropriate behavior`
-   **Permissions:** Ban Members

---

### `.unban <user_id_or_mention> [reason]`

-   **Description:** Unbans a member from the server.
-   **Usage:** `.unban @User Mistake` or `.unban 123456789012345678 Appealed`
-   **Permissions:** Ban Members

---

### `.bans`

-   **Description:** Displays a paginated list of all banned users in the server.
-   **Usage:** `.bans`
-   **Permissions:** Ban Members

---

### `.timeout <@user> <duration_string> [reason]`

-   **Alias:** `.to`
-   **Description:** Temporarily times out a member. Duration can be specified with units (w, d, h, m, s). Maximum 28 days.
-   **Usage:** `.timeout @User 2h30m Being disruptive` or `.timeout @User "1w 2d" Spam` or `.timeout @User 45m`
-   **Permissions:** Moderate Members

---

### `.untimeout <@user> [reason]`

-   **Alias:** `.uto`
-   **Description:** Removes a timeout from a member.
-   **Usage:** `.untimeout @User Cooled down`
-   **Permissions:** Moderate Members

---

### `.membercount`

-   **Alias:** `.mc`
-   **Description:** Displays the number of human members, bots, and total users in an embed.
-   **Usage:** `.membercount`
-   **Permissions:** None

---

### `.history <@member>`

-   **Description:** Views all recorded moderation actions *against* a specific member. Paginated.
-   **Usage:** `.history @User`
-   **Permissions:** Manage Messages

---

### `.history removeall <@member>`

-   **Description:** Removes *all* history entries for a specific member.
-   **Usage:** `.history removeall @User`
-   **Permissions:** Administrator

---

### `.history remove <@member> <case_id>`

-   **Description:** Removes a *specific* punishment by its Case ID for a member.
-   **Usage:** `.history remove @User 123`
-   **Permissions:** Manage Messages (or higher, e.g., Administrator, depending on desired strictness)

---

### `.history view <case_id>`

-   **Description:** Views details for a specific moderation Case ID from the server's logs.
-   **Usage:** `.history view 123`
-   **Permissions:** Manage Messages

---

### `.moderationhistory <@staff_member>`

-   **Alias:** `.mh`
-   **Description:** Views all moderation actions *performed by* a specific staff member. Paginated.
-   **Usage:** `.moderationhistory @Moderator`
-   **Permissions:** Manage Messages

---

### `.afk [reason | "off"]`

-   **Description:** Sets your status to AFK (Away From Keyboard). Reason is optional. Typing `.afk off` or sending any other message removes AFK. If a user who is AFK is mentioned, the bot will state their AFK status and reason.
-   **Usage:** `.afk Going for lunch` or `.afk` or `.afk off`
-   **Permissions:** None

---

### `.help`

-   **Description:** Provides a link to this documentation.
-   **Usage:** `.help`
-   **Permissions:** None

---

## Automatic Features

### Message Reactions

-   The bot automatically reacts to messages containing specific phrases:
    -   "y/n": Reacts with ⬆️ and ⬇️ (if other text is present and it's the last trigger).
    -   "v/s": Reacts with ⬅️ and ➡️ (if other text is present and it's the last trigger).

---

## Upcoming Commands

Stay tuned! More moderation and utility commands are in development. This README will be updated accordingly.

---

## Authors

Developed and maintained by:

-   [**soundfont**](https://github.com/soundfont)
-   [**Rafan Ahmed**](https://github.com/RafanAhmed)
