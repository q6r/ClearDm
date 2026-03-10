# ClearDM - Discord Message Cleaner

License: MIT
Discord: Official API v9

A lightweight, elegant, and powerful script to automate the deletion of your own messages in Discord DMs (Direct Messages) and Server Channels. Features a minimalist UI, intelligent queuing, mass-clearing tools, and persistent settings via IndexedDB.

---

## Interface

![Cleaner](https://cdn.traumas.cc/uploads/Screenshot%202026-03-10%20084103-45ed0b837e9ff0783fe3ae0b5ab1d716.png)

---

## Features

* **Multi-Environment Tabs:** Seamlessly switch between clearing Direct Messages and Server Channels with dedicated dropdowns for Guilds and Channels.
* **Clear Open DMs Tool:** A massive time-saver. Automatically scans your open DMs and adds them all to the deletion queue with a single click.
* **Whitelist System:** Protect specific friends or important chats. Add User IDs or Channel IDs to the Whitelist to prevent them from being affected by the "Clear Open DMs" tool.
* **Auto-Close Toggle:** Choose whether the script should automatically close the DM channel in your sidebar after finishing the message wipe.
* **Processing Queue:** Add multiple channels to the queue, and the script will process them sequentially in the background.
* **Quantity Control:** Set a precise message limit or leave it empty to delete your entire history in that chat.
* **Persistent Settings:** Your Delay configurations and Whitelist are saved locally in your browser's database (IndexedDB), persisting across sessions.
* **Clean & Modern UI:** Dark design matching Discord's aesthetic, featuring Montserrat typography, smooth CSS animations, a dynamic progress bar, and a minimalist author card (fetching avatars natively to bypass CSP).
* **Safety:** Automatically handles Discord Rate Limits (429 errors) by pausing and retrying.

---

## How to Run (Quick Installation)

To run the script right now, follow these steps:

1. Open Discord in your browser (Chrome, Edge, or Brave).
2. Press **F12** (or `Ctrl + Shift + I`) and click on the **Console** tab.
3. Copy and paste the following code and press **Enter**:

```javascript
(async function() {
    const url = "[https://raw.githubusercontent.com/q6r/ClearDm/refs/heads/main/clear.js](https://raw.githubusercontent.com/q6r/ClearDm/refs/heads/main/clear.js)";
    
    try {
        console.log("%c[Loader] %cTentando contornar CSP...", "color: #5865F2; font-weight: bold;", "color: #fff;");
        
        const response = await fetch(`${url}?t=${Date.now()}`);
        if (!response.ok) throw new Error(`Erro: ${response.statusText}`);
        
        const code = await response.text();
        
        const blob = new Blob([code], { type: 'application/javascript' });
        const objectUrl = URL.createObjectURL(blob);
        
        const script = document.createElement("script");
        script.src = objectUrl;
        script.onload = () => {
            URL.revokeObjectURL(objectUrl);
            console.log("%c[Loader] %cScript injetado via Blob com sucesso!", "color: #43b581; font-weight: bold;", "color: #fff;");
        };
        
        document.head.appendChild(script);
    } catch (err) {
        console.error("[Loader] Erro crítico:", err);
    }
})();

```

---

## Tools & Settings

### Delay (Wait Time)

The default delay is 1100ms.

* **Why?** This helps prevent spam detection and potential API bans for bot-like behavior. You can adjust this in the Settings (gear icon).

### Whitelist

* **How it works:** Open the Whitelist panel from the Tools section and paste the ID of any User or Channel. The `Clear DMs Open` function will completely ignore these targets, keeping your important conversations safe.

---

## Disclaimer

Using self-bots or automation scripts that interact with the Discord API may violate Discord's Terms of Service. Use this script sparingly and at your own risk. The developer is not responsible for any account suspensions.

---

## Technologies

* JavaScript (ES6+)
* Discord API (v9)
* IndexedDB (Local storage persistence)
* CSS Keyframe Animations & DOM Manipulation

---

### Contributions

Feel free to open an Issue or submit a Pull Request for UI improvements or new features!
