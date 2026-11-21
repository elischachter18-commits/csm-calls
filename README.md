# CSM Calls

A home-screen app for your phone that shows which clients you haven't reached and logs a call in two taps. It's set up the same way as 200 Lean and Money Tracker: one page hosted on GitHub Pages.

## Where your data lives

Clients and calls are saved **only on your phone**, in the app's own storage. Nothing is sent to GitHub, Firebase or anywhere else. The GitHub page holds only the app's code, which contains no client names or phone numbers.

That means:
- **Each device keeps its own data.** Your laptop won't see what's on your phone.
- **Back up regularly:** ⋯ (Settings) › **Back up everything**. Save the file somewhere safe, such as iCloud Drive or Google Drive. If your phone is reset or the app is deleted, restore that file with **Restore from backup**.

## Files

| File | What it is |
|---|---|
| `index.html` | The app |
| `manifest.webmanifest`, `icon-*.png`, `apple-touch-icon.png` | Home-screen name and icon |
| `sw.js` | Lets the app open with no signal |

## Setup

### 1. GitHub Pages
1. Sign in at github.com (the same account as your other apps).
2. Create a new repository named `csm-calls`. It must be **Public**, because GitHub Pages on a free account needs that. Only the app's code goes in it.
3. Choose **Add file › Upload files**, drag in every file from this folder, and commit.
4. Go to **Settings › Pages**: set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
5. After a minute or two, the app is live at `https://<your-username>.github.io/csm-calls/`.

### 2. On your phone
1. Open that address in **Safari** (iPhone) or **Chrome** (Android).
2. iPhone: **Share › Add to Home Screen**. Android: **⋮ › Add to Home screen**.
3. Always open the app from the home-screen icon. Its data is kept separately from the browser tab.

### 3. Bring your clients over (once)
1. In Google Sheets, open "Eli CSM calls" and choose **File › Download › Comma-separated values (.csv)**. On a phone, you can download it from the Sheets website, or export it on your laptop and send the file to yourself.
2. In the app, tap **⋯ › Import clients from CSV** and pick the file.
3. Choose the layout: **One client per row** (pick which column holds the name, phone and so on), or **Client names across one row**. In the second layout, any Loom link under a client's name is saved to that client.
4. Check the preview, untick anyone you don't want, and tap **Import**. Clients you already have are never duplicated: an existing client only gets phone, email, Loom or notes filled in where theirs are blank.

## How calling works
1. Tap a client, then tap **Call**. Your phone's dialer opens with their number.
2. When you come back to the app, it asks **Did they pick up?** Tap **Yes** or **No** to log the call with the current date and time. Tap **I didn't call** if you backed out.
3. Called from somewhere else? On the client's page, tap **Log a call manually**.
4. To fix a mistake, tap any call in the client's **Call history** to change it or delete it.

## Service agreements
- Each client's page has a **Service agreement** line. Tap **Update** to mark it **Not sent**, **Sent** (with the date) or **Signed** (with the date).
- The **Agreements** tab at the top of the home screen groups everyone into **Waiting to sign** (longest wait first, amber after 7 days), **Not sent yet** and **Signed**. Tap any client there to update them right away.
- **Export clients (CSV)** includes each client's agreement status and dates.

## Updating
Upload the changed files to the same repository. The app picks up the new version the next time you open it.
