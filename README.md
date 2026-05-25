# TurnKey Item Library — Excel Add-in

Search and insert capital works line items directly into your Summary Page for Building Data sheet, without leaving Excel.

---

## Setup (one-time, ~10 minutes)

### Step 1 — Create a free GitHub account
Go to https://github.com and sign up if you don't already have one.

### Step 2 — Create a new repository
1. Click the **+** icon (top right) → **New repository**
2. Name it exactly: `turnkey-addin`
3. Set it to **Public**
4. Click **Create repository**

### Step 3 — Upload the files
1. On your new repository page, click **uploading an existing file**
2. Drag ALL files from this folder into the upload area:
   - `manifest.xml`
   - `taskpane.html`
   - `commands.html`
   - `icon-16.png`
   - `icon-32.png`
   - `icon-80.png`
3. Click **Commit changes**

### Step 4 — Enable GitHub Pages
1. In your repository, click **Settings** (top tabs)
2. Scroll to **Pages** in the left sidebar
3. Under **Branch**, select `main` and click **Save**
4. Wait ~60 seconds, then your add-in is live at:
   `https://YOUR-GITHUB-USERNAME.github.io/turnkey-addin/`

### Step 5 — Update the manifest with your URL
1. Open `manifest.xml` in a text editor (Notepad is fine)
2. Find every occurrence of `REPLACE-WITH-YOUR-GITHUB-USERNAME`
3. Replace them all with your actual GitHub username
4. Save the file
5. Upload the updated `manifest.xml` back to GitHub
   (go to the file in GitHub, click the pencil/edit icon, paste the new content, save)

### Step 6 — Sideload the add-in into Excel

**On Windows (Microsoft 365 / Excel 2019+):**
1. Open Excel
2. Go to **Insert** tab → **Add-ins** → **My Add-ins**
3. Click **Upload My Add-in** (or "Manage My Add-ins" → Upload)
4. Browse to and select your `manifest.xml` file
5. Click **Upload**

The add-in will appear as **"Item Library"** button in the **Home** tab ribbon.

**On Mac (Microsoft 365):**
1. Open Excel
2. Go to **Insert** → **Add-ins**
3. Click **Upload My Add-in**
4. Select `manifest.xml`

---

## Using the Add-in

1. Open your Capital Works template (the `.xlsm` file)
2. Click **Item Library** in the Home ribbon → the panel opens on the right
3. **Search or browse** by category to find items
4. **Tick checkboxes** to select items — they move to the Selected tab
5. Adjust **qty, unit, rate, next due, total life** if needed for this job
6. Click **↓ Insert into Summary Page**
7. Items are inserted into the correct sheet with formulas — then run your VBA as normal

### Saving job templates
- After selecting items, go to the **Saved Jobs** tab
- Type a job name (e.g. "732 Military Rd Mosman") and click **Save**
- Load any past job in one click to reuse its items

### Adding custom items
- Use the **+ Add** tab to add your own items to the library permanently

---

## Updating the add-in
To update the app (e.g. after changes are made), simply upload the new `taskpane.html` to your GitHub repository. Changes go live within a minute. You don't need to re-sideload the manifest.

---

## Troubleshooting

**"Sheet not found" error:**
The add-in looks for a sheet whose name contains "Summary Page" or "Building Data".
Make sure your sheet is named exactly `Summary Page for Building Data`.

**Add-in doesn't appear in ribbon:**
In Excel, go to Insert → Add-ins → My Add-ins and check it's listed and enabled.

**Items inserted in wrong place:**
The add-in finds the last row of data in column B and inserts above the Subtotal row.
If your sheet structure differs, manually select where you want the rows and paste instead.
