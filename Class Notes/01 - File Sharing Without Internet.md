# 🌐 File Sharing Without Internet

## ❓ Question

I don't have any of your contact details (phone number or email), but I need to share a file with you. Internet, Bluetooth, AirDrop, and email are not allowed.

**Hint:** Both devices are connected to the same local network.

**How can the file be shared?**

---

# 🚀 Method 1 - Hosting a Simple HTTP Server

## 🎯 Objective

Share files present in a folder with other devices connected to the same local network using Python's built-in HTTP server.

---

## 📋 Requirements

* Python installed
* Both devices connected to the same Wi-Fi / Local Network
* No Internet required
* Firewall should allow Python (if prompted)

---

## 1️⃣ Step 1 - Navigate to the Folder

Open **Command Prompt** inside the folder to be shared.

Example:

```powershell
cd C:\Users\Edlyn Jessica\OneDrive\Desktop
```

---

## 2️⃣ Step 2 - Start the HTTP Server

Run the following command:

```powershell
python -m http.server 8000
```

Output:

```text
Serving HTTP on :: port 8000 (http://[::]:8000/) ...
```

This starts a simple web server on **port 8000** and serves all files from the current directory.

---

## 3️⃣ Step 3 - Find the System's IP Address

Run:

```powershell
ipconfig
```

Relevant output:

```text
Wireless LAN adapter Wi-Fi

IPv4 Address : 10.1.35.82
Subnet Mask  : 255.255.255.0
Gateway      : 10.1.35.1
```

---

## 🌐 Which IP Should Be Used?

`ipconfig` may display multiple IP addresses.

### ✅ Correct IP

**10.1.35.82**

**Reason:**

* Belongs to the active Wi-Fi adapter.
* Reachable by other devices connected to the same network.

---

## 4️⃣ Step 4 - Access the Server

On another device connected to the same Wi-Fi, open any web browser and enter:

```text
http://10.1.35.82:8000
```

The browser displays all files present inside the shared folder, allowing them to be downloaded.

---

# ⚙️ Working Principle

```text
        HTTP Request
Client ----------------------> Python HTTP Server

Browser <--------------------- Requested File
        HTTP Response
```

The computer running the command acts as a **web server**.

* A client (browser) sends an HTTP request.
* The Python HTTP server receives the request.
* The requested file is sent back as an HTTP response.
* Since both devices are on the same local network, no Internet connection is required.

---

# ✅ Advantages

* No Internet required
* No additional software required
* Cross-platform (Windows, Linux, macOS)
* Quick and easy to set up
* Accessible from any web browser

---

# ⚠️ Limitations

* Supports file download only
* No authentication by default
* Suitable only for trusted local networks
* Server stops when the terminal is closed

---

# 💻 Commands Learned

Start a simple HTTP server:

```powershell
python -m http.server 8000
```

View network configuration:

```powershell
ipconfig
```

---

# 📝 Conclusion

Successfully hosted a simple HTTP server using Python and shared files over the local network using the Wi-Fi IPv4 address **10.1.35.82**.

This method requires:

* Python
* Devices connected to the same local network
* A web browser on the client device

No Bluetooth, Email, AirDrop, or Internet connection is required.
