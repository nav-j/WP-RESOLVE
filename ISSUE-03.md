If LocalWP is **not showing the WordPress version**, that usually means **Local can’t detect a valid WordPress install** in your site folder. This is also a big reason you’re getting the **404 nginx error**.

Let’s fix it methodically 👇

---

## 🔍 First: What does it show instead of WordPress Version?

On LocalWP → select your site → **Overview**

Under **WordPress** it usually shows something like:

> WordPress 6.5.2

If instead you see:

* Blank / empty
* “Not detected”
* Or nothing at all

👉 That confirms WordPress is missing or broken.

---

## ✅ Step 1 — Check if WordPress files exist

Go to this folder on your computer:

```
Documents → Local Sites → your-site-name → app → public
```

Inside **public** folder, do you see these?

✅ Must exist:

* wp-config.php
* wp-admin (folder)
* wp-content (folder)
* wp-includes (folder)
* index.php

### If these files/folders are MISSING:

That’s your problem. WordPress is not actually installed.

### Solution:

In LocalWP:

1. Delete this site
2. Click **+ Create New Site**
3. Choose **Preferred** setup
4. Let Local install WordPress automatically

Then your version will appear correctly.

---

## ✅ Step 2 — If files DO exist, repair WordPress

If the WordPress files exist but version is still not showing:

1. Click site in Local
2. Click **Site Shell**
3. Run this command:

```
wp core version
```

If it shows a version → WordPress is OK

If it gives an error → WordPress is corrupted

### To repair:

Run:

```
wp core download --force
```

Then restart site.

---

## ✅ Step 3 — Fix with Apache (important)

In your site → Overview:

1. Change **Web Server** from:

   * Nginx ➝ **Apache**
2. Click **Apply**
3. Restart site

Now check if WordPress version appears.

---

## ✅ Step 4 — Check Site Domain

In Overview → Site Domain must end with:

`.local` or `.test`

Example:

```
mywebsite.local
```

If wrong:

* Edit it
* Click Apply
* Restart site

---

## ✅ Step 5 — Quick 100% working solution (if above fails)

This always fixes version + 404 issues:

1. Backup your **wp-content** folder
2. Delete site in LocalWP
3. Recreate the site
4. After new install, paste back the old **wp-content**

✅ Now WordPress version will show
✅ Site will open correctly

---

## 🚨 Please send me ONE screenshot

Send a screenshot of your LocalWP **Overview tab** for your site.

I’ll tell you exactly why WordPress version is missing in your specific case and fix it for you.
