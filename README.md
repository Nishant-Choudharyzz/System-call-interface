# User-Friendly System Call Interface for Enhanced Security

A fully browser-based, offline-capable Operating System simulation designed to teach the concepts of **System Calls**, **Authentication**, **Authorization**, and **Auditing**.

## 🚀 How to Run
1. simply open `index.html` in any modern web browser.
2. No server, installation, or internet connection required

## 🔐 Credentials
- **Username**: `admin`
- **Password**: `admin123`
- **Username**: `user`
- **Password**: `user123`

---

## 📚 Educational Concepts

### 1. System Calls (The Interface)
In a real Operating System, applications run in **User Mode** and cannot directly access hardware or critical data. modifying files, creating processes, or accessing memory requires help from the Kernel.
Apps request this help via **System Calls** (e.g., `open`, `read`, `write`, `fork`).
> This project simulates this boundary. The `Kernel` class in JavaScript acts as the privileged core, and the UI acts as a user-mode application making requests to it.

### 2. Authentication (Who are you?)
Before the OS accepts commands, it often needs to know who is making them.
- We simulate this with a login screen.
- The kernel stores a session (`currentUser`) which is checked before every system call.

### 3. Authorization (Are you allowed?)
Even if you are logged in, you might not have permission to do everything.
- **Root/Admin**: Has full access.
- **Regular User**: Restricted from system directories like `/etc` or prohibited from killing system processes.
> Try accessing restricted files (simulated in `sys_read`) to see `access_denied` errors.

### 4. Auditing (The Trail)
Security isn't just about prevention; it's about detection.
- Every system call (success or failure) is logged.
- In this project, logs are saved to the browser's `localStorage`, simulating a persistent audit trail.
- Administrators review these logs to detect security breaches (e.g., repeated failed login attempts or unauthorized file access).

---

## 🛠 Project Structure
- `index.html`: The Single Page Application (SPA) structure.
- `style.css`: Premium, dark-themed styling.
- `script.js`: Contains the entire simulated mock OS (FileSystem, Process Manager, Kernel, Logging).

## ⚠️ Note
This is a **simulation**. No real files on your computer are touched. The "File System" is a JavaScript object in memory and will reset when you refresh the page (Audit Logs persist).

## Changes:
1. Made a different section for system calls.
2. Added one more user.
3. Changed name of user to standard user.
4. changed name of admin to Superuser(root).
