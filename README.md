# ClearDM - Discord Message Cleaner

License: MIT
Discord: Official API v9

A lightweight and elegant script to automate the deletion of your own messages in Discord DMs (Direct Messages). Features a minimalist interface, channel queuing support, and persistent settings via IndexedDB.

---

## Interface

### Home Panel
![Home Cleaner](https://cdn.traumas.cc/uploads/image222222-12ff622625cbb16366ccf2588138d882.png)

### Configuration Panel
![Config Cleaner](https://cdn.traumas.cc/uploads/image2213-f798ad3d6302da9e545579f453b9daa4.png)

---

## Features

* Target Selection: Choose any DM chat directly from a dropdown menu with user avatars.
* Processing Queue: Add multiple channels to the queue, and the script will process them sequentially.
* Quantity Control: Set a message limit or leave it empty to delete your entire history.
* Delay Persistence: The wait time between deletions (Delay) is saved in your browser's database (IndexedDB), keeping your preference even after closing Discord.
* Clean Interface: Dark design inspired by Discord's aesthetic, featuring smooth animations and a progress bar.
* Safety: Automatically handles Discord Rate Limits (429 errors).

---

## How to Run (Quick Installation)

To run the script right now, follow these steps:

1. Open Discord in your browser (Chrome, Edge, or Brave).
2. Press **F12** (or `Ctrl + Shift + I`) and click on the **Console** tab.
3. Copy and paste the following code and press **Enter**:

```javascript
(async function() {
    const url = "[https://raw.githubusercontent.com/q6r/ClearDm/main/clear.js](https://raw.githubusercontent.com/q6r/ClearDm/main/clear.js)";
    const res = await fetch(`${url}?t=${Date.now()}`);
    const code = await res.text();
    
    const blob = new Blob([code], { type: 'application/javascript' });
    const objUrl = URL.createObjectURL(blob);
    
    const script = document.createElement("script");
    script.src = objUrl;
    
    document.head.appendChild(script);
})();
```

---

## Settings

### Delay (Wait Time)
The default delay is 1100ms.
* Why? This helps prevent spam detection and potential bans for bot-like behavior.
* How to change? Click the gear icon at the top of the panel.
* Saving: The value you enter will be permanently saved via IndexedDB in your browser's user profile.

---

## Disclaimer

Using self-bots or automation scripts that interact with the Discord API may violate Discord's Terms of Service. Use this script sparingly and at your own risk. The developer is not responsible for any account suspensions.

---

## Technologies
* JavaScript (ES6+)
* Discord API (v9)
* IndexedDB (Local storage)
* CSS Keyframe Animations

---

### Contributions
Feel free to open an Issue or submit a Pull Request for UI improvements or new features!
