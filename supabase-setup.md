# Supabase Setup Guide — Step by Step

Supabase is a free online database. Follow these steps carefully — no coding needed!

---

## Step 1: Create a Supabase account

1. Go to **supabase.com**
2. Click **"Start your project"**
3. Sign up with your GitHub or Google account (free)

---

## Step 2: Create a new project

1. Click **"New project"**
2. Fill in:
   - **Name:** `open-house-quest`
   - **Database Password:** Choose a strong password (save it somewhere!)
   - **Region:** Pick one closest to you (e.g. Southeast Asia)
3. Click **"Create new project"**
4. Wait 1–2 minutes while it sets up

---

## Step 3: Create the RSVP table

1. In your project, click **"SQL Editor"** in the left menu
2. Click **"New query"**
3. Copy and paste this entire block into the box:

```sql
CREATE TABLE rsvp (
  id uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  created_at timestamptz DEFAULT now(),
  guest_name text,
  gender text,
  has_hijab boolean DEFAULT false,
  attire_colour text,
  time_slot text,
  total_pax integer,
  adult_male integer DEFAULT 0,
  adult_female integer DEFAULT 0,
  toddler_male integer DEFAULT 0,
  toddler_female integer DEFAULT 0
);

-- Allow anyone to insert RSVP data (public access)
ALTER TABLE rsvp ENABLE ROW LEVEL SECURITY;

CREATE POLICY "Allow public insert"
  ON rsvp FOR INSERT
  TO anon
  WITH CHECK (true);

CREATE POLICY "Allow owner to read"
  ON rsvp FOR SELECT
  TO authenticated
  USING (true);
```

4. Click **"Run"** (the green button)
5. You should see "Success" — the table is created! ✅

---

## Step 4: Get your API credentials

1. In the left menu, click **"Project Settings"** (gear icon)
2. Click **"API"**
3. You'll see two things to copy:
   - **Project URL** — looks like `https://abcxyz.supabase.co`
   - **anon / public key** — a long string starting with `eyJ...`

---

## Step 5: Add credentials to the game

1. Open `index.html` in any text editor (Notepad, TextEdit, etc.)
2. Press **Ctrl+F** (Windows) or **Cmd+F** (Mac) to search
3. Search for: `YOUR_SUPABASE_URL`
4. Replace it with your **Project URL**
5. Search for: `YOUR_SUPABASE_ANON_KEY`
6. Replace it with your **anon / public key**
7. Save the file

---

## Step 6: Test it

1. Open `index.html` in your browser (double-click the file)
2. Play through the game until Screen 7 (Quest Complete)
3. Go back to Supabase → **Table Editor** → **rsvp**
4. You should see a new row with your test RSVP! ✅

---

## Viewing responses after the event

1. Go to **supabase.com** → log in → your project
2. Click **Table Editor** → **rsvp**
3. All your guests' RSVPs will be listed there
4. You can also click **"Export"** to download as Excel/CSV

---

That's it! You're ready to go. 🎉
