# Oracle Compute Instance Creation Script

A JavaScript script that continuously attempts to create an Oracle Cloud free tier compute instance when capacity is limited. **Updated for Oracle Cloud 2025 interface.**

## 🚀 Quick Start

### Prerequisites
- Oracle Cloud account (free tier)
- Modern web browser (Chrome, Firefox, Safari, Edge)
- All instance parameters configured

### Step-by-step usage:

1. Follow the steps at https://blogs.oracle.com/developers/post/how-to-set-up-and-run-a-really-powerful-free-minecraft-server-in-the-cloud

2. **Configure Email (Optional)**
   - Open `script.js` and edit the `EMAIL_CONFIG` section:
   ```javascript
   const EMAIL_CONFIG = {
       SENDER_EMAIL: "your-email@gmail.com",
       SENDER_PASSWORD: "your-app-password", // Gmail app password
       RECIPIENT: "your-email@gmail.com",
       SMTP_SERVER: "smtp.gmail.com",
       SMTP_PORT: 587
   };
   ```

2. **Go to Oracle Cloud**
   - Navigate to: https://cloud.oracle.com/compute/instances/create
   - Make sure you're logged in

3. **Fill ALL Required Fields**
   
   Complete all sections in the Oracle Cloud interface:
   - **Basic Information**
   - **Security** 
   - **Networking**
   - **Storage**
   
   - **⚠️ DO NOT CLICK CREATE YET!**

4. **Launch the Script**
   - Press `F12` to open Developer Tools
   - Go to the `Console` tab
   - Copy the entire content of `script.js`
   - Paste it into the console
   - Press `Enter`

5. **Script is Running**
   - You'll see a blue status bar at the top
   - A small popup window will open (**DO NOT CLOSE IT!**)
   - Console will show: "Create button found!"
   - Close the Developer Tools (F12) - optional but recommended

6. **Wait and Monitor**
   - The script clicks "Create" every 30 seconds
   - Blue bar shows countdown: "Clicking in X seconds"
   - Green bar means "Create clicked!"
   - Red bar means "Create button not found!"

## 🎯 What the Script Does

### Automatic Actions
- ✅ **Auto-retry**: Clicks Create button every 30 seconds
- ✅ **Session management**: Keeps your Oracle session active via popup
- ✅ **Error detection**: Recognizes capacity/quota errors
- ✅ **Success detection**: Automatically stops when instance is created
- ✅ **Email notification**: Sends email when successful (if configured)
- ✅ **Visual feedback**: Real-time status bar

### Manual Controls
```javascript
// Change click interval (default: 30 seconds)
INTERVAL_DURATION = 10; // Faster clicking

// Stop the script manually
stopScript(); // Type this in console
```

## 🔧 Troubleshooting

### "Create button not found"
1. Make sure you're on: https://cloud.oracle.com/compute/instances/create
2. Fill ALL required fields completely
3. Scroll down to see the Create button
4. Check that button is blue and clickable

### Script stops working
- **Popup closed**: Script will fail - keep the popup open!
- **Session expired**: Refresh page and restart script
- **Page changed**: Navigate back to create instance page

### Email not working
- Make sure you configured `EMAIL_CONFIG` properly
- Use Gmail app password (not regular password)
- Email will open your email client (mailto link)

## ⚠️ Important Notes

### **DO NOT CLOSE THE POPUP WINDOW!**
The small popup window maintains your Oracle Cloud session. Closing it will cause the script to fail after 15-30 minutes.

### Performance Tips
- **Close dev tools** while script runs (prevents browser crashes)
- **Keep computer awake** - disable sleep mode
- **Filter console logs** with `***` to see script messages only
- **Be patient** - Oracle capacity varies throughout the day

### Success Indicators
- ✅ Green status bar: "Instance created successfully!"
- ✅ Email notification (if configured)
- ✅ Browser notification
- ✅ Redirect to instances page

## 🛑 Stopping the Script

### Automatic Stop
The script automatically stops when:
- Instance is successfully created
- Success message is detected
- Page redirects to instances list

### Manual Stop
```javascript
// In console, type any of these:
stopScript();                    // Recommended method
clearInterval(intervalId);       // Alternative
instanceCreated = true;         // Alternative
```

## ⏱️ Default Settings

- **Click interval**: 30 seconds
- **Popup refresh**: Every 30 seconds  
- **Session maintenance**: Automatic
- **Error detection**: Automatic
- **Success detection**: Automatic

## 📧 Email Configuration

To receive email notifications:

1. **Gmail Setup**:
   - Enable 2-factor authentication
   - Generate app password: https://myaccount.google.com/apppasswords
   - Use app password in `EMAIL_CONFIG.SENDER_PASSWORD`

2. **Update Configuration**:
   ```javascript
   const EMAIL_CONFIG = {
       SENDER_EMAIL: "your-sender@gmail.com",
       SENDER_PASSWORD: "your-16-char-app-password",
       RECIPIENT: "your-recipient@gmail.com",
       SMTP_SERVER: "smtp.gmail.com",
       SMTP_PORT: 587
   };
   ```

---

**Good luck getting your Oracle Cloud instance! 🍀**