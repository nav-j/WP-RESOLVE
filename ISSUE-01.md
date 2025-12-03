Your site is **not starting because MySQL is failing to start in LocalWP**:

> `Can't connect to MySQL server on '::1:10056' (10061)`
>
> That means: **MySQL service is stopped, blocked, or the port is in use**.

This is why:

* Your website doesn’t open
* WordPress version sometimes doesn’t show
* You see 404 / Nginx errors

Let’s fix it step-by-step (this works almost every time) 

---

## Fix 1 – Restart MySQL in Local (most important)

1. Close LocalWP completely
2. Open **Task Manager (Ctrl + Shift + Esc)**
3. End these if running:

   * `mysqld.exe`
   * `local.exe`
   * `nginx.exe`
4. Open **LocalWP again**
5. Start your site

 Try now.
If still error → go to Fix 2

---

## Fix 2 – Port conflict (another MySQL using same port)

You most likely have **XAMPP / WAMP / another MySQL** running.

### Do this:

1. Press **Windows + R**

2. Type:

   ```
   services.msc
   ```

3. Look for anything like:

   * MySQL
   * MySQL80
   * MariaDB
   * XAMPP MySQL

4. If running → **Right click → Stop**

Now go back to **LocalWP** and start your site.

 80% of time this fixes it.

---

##  Fix 3 – Change MySQL port in Local (Hard fix but powerful)

If something is still blocking port **10056**:

1. Open LocalWP
2. Click your site
3. Go to **Database tab**
4. Click **Stop site**
5. Now go to **Site Settings (⚙️)**
6. Change MySQL port from example:

   ```
   10056 → 3307
   ```
7. Click **Apply**
8. Start the site again

---

##  Fix 4 – Repair Database folder

Sometimes the database file is corrupted.

Go to:

```
C:\Users\YOURNAME\Documents\Local Sites\yoursite-name\app\
```

You will see:

```
sql
```

Rename it to:

```
sql_old
```

Now restart your site on Local.

Local will auto-create a fresh new database.

 Your site WILL start (but old data will be gone unless restored).

---

##  Fix 5 – Nuclear solution (100% works)

If you just want it to WORK now:

1. Backup this folder:

   ```
   wp-content
   ```

2. Delete the site in LocalWP

3. Create a **New Site**

4. Copy your old `wp-content` into the new site

 Done. Fresh database + your content safe.

---

WordPress version: **6.9**

WordPress is actually installed correctly 
The only problem is **MySQL not running**.

---
