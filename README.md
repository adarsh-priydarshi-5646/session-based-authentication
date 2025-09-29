# 🔐 Session-Based Authentication Challenge

Welcome to your mini-project challenge! 🚀  
In this exercise, you’ll implement **basic session-based authentication** in Express.js and test it using **Mocha, Chai, and Supertest**.

---

## 📌 What You Need to DoYou only need to **implement the following routes** inside `server.js`:

1. **`POST /login`**
   - Accepts `{ username, password }`
   - If `username = admin` and `password = secret`
     - ✅ Save the user in the session
     - ✅ Respond with **200 → { message: "Login successful" }**
   - Else
     - ❌ Respond with **401 → { message: "Invalid credentials" }**

2. **`GET /profile`**
   - If user is logged in (session exists)
     - ✅ Respond with **200 → { message: "Welcome, <username>" }**
   - Else
     - ❌ Respond with **401 → { message: "Unauthorized" }**

3. **`GET /logout`**
   - Destroy the session
   - ✅ Respond with **200 → { message: "Logout successful" }**

---

## 🛠️ Setup Instructions

1️⃣ **Install Dependencies**
```bash
npm install
```

2️⃣ **To start the server**
```bash
npm run dev
```

3️⃣ **To test code**
```bash
npm test
```


## ⚡ Express-session syntax :

1️⃣ **Creating Session**
```js
req.session.user = { username };
```

2️⃣ **Destroying Session**
```js
req.session.destroy(err => {
    if (err) {
      return res.status(500).json({ message: "Logout failed" });
    }
    res.clearCookie("connect.sid");
})
```