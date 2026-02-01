# PROJEKT: THE MIDNIGHT CLUB

## 1. STATUS
Current: **Offline / Single Player Mode**
By default, the application runs in a local simulation. Messages are not sent to the internet.

## 2. HOW TO ENABLE MULTIPLAYER (TESTING WITH FRIENDS)
To let multiple people chat in the same room, you must connect the app to a backend. The code is already pre-wired for **Firebase Realtime Database**.

### Step 1: Get API Keys
1. Go to [Firebase Console](https://console.firebase.google.com/).
2. Create a new project (e.g., "midnight-club-dev").
3. In the sidebar, go to **Build** > **Realtime Database** > **Create Database**.
   - Choose **Start in Test Mode** (this allows anyone with the config to read/write for 30 days).
4. Click the **Project Overview** (gear icon) > **Project settings**.
5. Scroll down to "Your apps", click the **</>** icon (Web).
6. Register the app (name it whatever).
7. Copy the `firebaseConfig` object (it has `apiKey`, `authDomain`, etc.).

### Step 2: Update Code
1. Open `index.html` in a text editor (VS Code, Notepad, etc.).
2. Scroll to **Line 224**:
   ```javascript
   const USE_FIREBASE = false; 
   ```
   Change this to:
   ```javascript
   const USE_FIREBASE = true;
   ```
3. Scroll to **Line 226** and paste your `firebaseConfig` object, replacing the placeholder.

### Step 3: Share
- **Option A (Easiest)**: Send the updated `index.html` file to your friends. If they open it in their browser, and you open it in yours, you will see each other's messages!
- **Option B (Better)**: Drag and drop the file onto a hosting service like Netlify Drop or use Firebase Hosting.

## 3. CLUB RULES
- **HOURS**: 23:00 - 03:00 (Local Time).
- **LOCKOUT**: Outside these hours, the club is closed.
- **WIPE**: At 03:01 AM, the system purges.

## 4. DEV CHEATS
If you need to test the UI during the day:
- **Change Hours**: Search for `const isClubOpen` in the code and force it to `true`.
