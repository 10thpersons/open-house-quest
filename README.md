# Open House Quest: Final Fantasy Ketupat 🏠🐉

Selamat datang! This is your Raya RSVP game. Follow these steps to get it live.

---

## Step 1: Set up Supabase (free database)

Read the file `supabase-setup.md` for full step-by-step instructions.

After setup, you'll get two things:
- A **Supabase URL** (looks like: `https://abcxyz.supabase.co`)
- A **Supabase Anon Key** (a long string of letters and numbers)

Open `index.html` in a text editor, find these two lines near the top of the `<script>` section:

```
const SB_URL = 'YOUR_SUPABASE_URL';
const SB_KEY = 'YOUR_SUPABASE_ANON_KEY';
```

Replace `YOUR_SUPABASE_URL` and `YOUR_SUPABASE_ANON_KEY` with your actual values.

---

## Step 2: Fix the Waze link (optional)

In `index.html`, find this line:

```
window.open('https://waze.com/ul?ll=3.139,101.687&navigate=yes','_blank');
```

Replace `3.139,101.687` with the actual GPS coordinates of Izham's home.
(You can get coordinates from Google Maps → right-click on the pin → copy the numbers)

---

## Step 3: Host on Netlify (free hosting)

1. Go to **netlify.com** → Sign up for free
2. Click **"Add new site"** → **"Deploy manually"**
3. Drag the `index.html` file into the upload box
4. Netlify gives you a URL like `https://open-house-quest.netlify.app`
5. Share that link on WhatsApp / Instagram — done! 🎉

---

## How to view RSVP responses

1. Go to **supabase.com** → Log in
2. Click your project → **Table Editor** → **rsvp** table
3. You'll see everyone who RSVP'd!

---

## Event Details

| Field | Value |
|-------|-------|
| Date | Saturday, 11 April 2026 |
| Time slots | 1:00pm, 3:00pm, 5:00pm, 8:00pm |
| Host | Izham |
| Maps | https://maps.app.goo.gl/5bc7ZCBizmsbBBY17 |
