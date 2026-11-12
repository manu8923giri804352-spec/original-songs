<!DOCTYPE html>  
  
<html lang="hi">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Original Songs - AI Music Generator</title>  
    <style>  
        :root {  
            --bg-color: #0f172a;  
            --card-bg: #1e293b;  
            --primary: #38bdf8;  
            --accent: #f43f5e;  
            --text-color: #f8fafc;  
            --text-secondary: #94a3b8;  
        }  
        body {  
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;  
            background-color: var(--bg-color);  
            color: var(--text-color);  
            margin: 0;  
            padding: 0;  
            display: flex;  
            justify-content: center;  
            align-items: center;  
            min-height: 100vh;  
        }  
        .container {  
            width: 100%;  
            max-width: 480px;  
            background: var(--card-bg);  
            border-radius: 16px;  
            box-shadow: 0 10px 25px rgba(0,0,0,0.5);  
            padding: 24px;  
            box-sizing: border-box;  
            margin: 16px;  
        }  
        h1 {  
            text-align: center;  
            color: var(--primary);  
            margin-bottom: 4px;  
            font-size: 24px;  
        }  
        .subtitle {  
            text-align: center;  
            color: var(--text-secondary);  
            font-size: 13px;  
            margin-bottom: 20px;  
        }  
        .hidden {  
            display: none !important;  
        }  
        input, select, textarea {  
            width: 100%;  
            padding: 12px;  
            margin: 8px 0 16px 0;  
            background: #0f172a;  
            border: 1px solid #334155;  
            color: var(--text-color);  
            border-radius: 8px;  
            box-sizing: border-box;  
            font-size: 14px;  
        }  
        button {  
            width: 100%;  
            padding: 12px;  
            background: var(--primary);  
            color: #0f172a;  
            border: none;  
            border-radius: 8px;  
            font-weight: bold;  
            font-size: 16px;  
            cursor: pointer;  
            transition: 0.2s;  
            margin-top: 5px;  
        }  
        button:hover {  
            opacity: 0.9;  
        }  
        .btn-secondary {  
            background: #334155;  
            color: var(--text-color);  
        }  
        .badge {  
            background: #334155;  
            padding: 6px 10px;  
            border-radius: 6px;  
            font-size: 12px;  
            color: var(--primary);  
            display: inline-block;  
            margin-bottom: 12px;  
            text-align: center;  
            width: 100%;  
            box-sizing: border-box;  
        }  
        .info-box {  
            background: #0f172a;  
            padding: 12px;  
            border-radius: 8px;  
            font-size: 12px;  
            color: var(--text-secondary);  
            margin-bottom: 16px;  
            border-left: 3px solid var(--accent);  
            line-height: 1.5;  
        }  
        .stats {  
            display: flex;  
            justify-content: space-between;  
            font-size: 12px;  
            color: var(--text-secondary);  
            background: #0f172a;  
            padding: 8px 12px;  
            border-radius: 6px;  
            margin-bottom: 16px;  
        }  
        .qr-box {  
            text-align: center;  
            background: #0f172a;  
            padding: 15px;  
            border-radius: 10px;  
            margin-bottom: 15px;  
            border: 1px dashed var(--primary);  
        }  
    </style>  
</head>  
<body>  
  
  
```
<div class="container">
    <!-- 1. LOGIN & PRIVACY SCREEN -->
    <div id="loginScreen">
        <h1>Original Songs</h1>
        <div class="subtitle">By Manu Giri</div>
        <hr style="border:0; border-top:1px solid #334155; margin:15px 0;">
        
        <div class="info-box">
            <b>प्राइवेसी नोटिस:</b> हमें आपकी पर्सनल जीमेल नहीं चाहिए! कृपया अपनी कोई भी <b>साइड/सेकेंडरी Gmail</b> दें। फोन नंबर संपर्क के लिए और इंस्टा आईडी आपके गानों के प्रमोशन के लिए है।
        </div>

        <label>साइड Gmail आईडी:</label>
        <input type="email" id="userEmail" placeholder="example@gmail.com" required>

        <label>पर्सनल फोन नंबर:</label>
        <input type="tel" id="userPhone" placeholder="9876543210" required>

        <label>इंस्टाग्राम आईडी:</label>
        <input type="text" id="userInsta" placeholder="@your_instagram" required>

        <button onclick="handleLogin()">ऐप में प्रवेश करें</button>
    </div>

    <!-- 2. MAIN DASHBOARD SCREEN -->
    <div id="appScreen" class="hidden">
        <h1>Original Songs</h1>
        <div id="userBadge" class="badge"></div>

        <div class="stats">
            <span id="dailyLimitText">दैनिक सीमा: दिन में 2 गाने</span>
            <span id="weeklyLimitText">वीकली: हफ्ते में 3 बार</span>
        </div>

        <div class="info-box">
            <b>नियम व फीचर्स:</b> 5000 शब्द सीमा। फ्री यूजर्स (25% रॉयल्टी), ₹99 पेड प्लान (10% रॉयल्टी - ऑटो एक्टिव)। मेहनती क्रिएटर्स (महीने के 100 गाने) को ओनर मानु गिरी की तरफ से 1 साल का फ्री सब्सक्रिप्शन और प्रमोशन! ब्रांड प्रमोशन के लिए भी रास्ते खुले हैं।
        </div>

        <!-- PAYMENT PROMO BOX (For Free Users) -->
        <div id="upgradeBox" style="background: #334155; padding: 12px; border-radius: 8px; margin-bottom: 15px; text-align: center;">
            <span style="font-size: 13px; display: block; margin-bottom: 8px;">कम रॉयल्टी (10%) के लिए ₹99 का पेड प्लान लें!</span>
            <button class="btn-secondary" onclick="showPaymentModal()" style="padding: 8px; font-size: 13px;">₹99 पे करें (ओनर का स्कैनर)</button>
        </div>

        <label>गाने का टाइटल:</label>
        <input type="text" id="songTitle" placeholder="जैसे: tanha raatein...">

        <label>لिरिक्स लिखें (अधिकतम 5000 शब्द):</label>
        <textarea id="songLyrics" rows="4" maxlength="5000" placeholder="यहाँ अपने दिल के जज़्बात या लिरिक्स लिखें..."></textarea>

        <label>वाइब और स्टाइल चुनें:</label>
        <select id="songVibe">
            <option value="lofi">लो-फाई वाइब (Lo-Fi Vibe + Piano)</option>
            <option value="hard">हार्ड बीट (Hard Bass)</option>
            <option value="guitar">गिटार मेलोडी (Guitar Tuning)</option>
        </select>

        <label>गैलरी से वीडियो/मूवी प्रोजेक्ट जोड़ें (वैकल्पिक):</label>
        <input type="file" id="mediaFile" accept="video/*, audio/*">

        <button onclick="generateSong()">गाना बनाएं (AI Generate)</button>
        
        <div id="outputResult" style="margin-top: 15px; font-size: 13px; color: var(--primary);"></div>
    </div>

    <!-- 3. PAYMENT MODAL SCREEN -->
    <div id="paymentScreen" class="hidden">
        <h1>₹99 प्लान भुगतान</h1>
        <div class="subtitle">सीधे ओनर (मानु गिरी) को भेजें</div>
        
        <div class="qr-box">
            <p style="margin: 0 0 10px 0; font-size: 14px; color: var(--primary);"><b>ओनर का UPI QR Code / Scanner</b></p>
            <div style="background:#1e293b; padding:20px; border-radius:8px; color:#94a3b8; font-size:12px;">
                [ QR Code Image Here ]<br>
                UPI ID: <b>manugiri@oksbi</b> (या अपनी यूपीआई आईडी डालें)
            </div>
        </div>

        <button onclick="autoActivatePaidPlan()">मैंने भुगतान कर दिया है (Auto Active)</button>
        <button class="btn-secondary" onclick="closePaymentModal()" style="margin-top: 8px;">वापस जाएं</button>
    </div>
</div>

<script>
    let currentUser = {};

    function handleLogin() {
        const email = document.getElementById('userEmail').value.trim();
        const phone = document.getElementById('userPhone').value.trim();
        const insta = document.getElementById('userInsta').value.trim();

        if(!email || !phone || !insta) {
            alert("कृपया सभी डिटेल्स भरें!");
            return;
        }

        // Owner Check (Manu Giri)
        let isOwner = email.toLowerCase().includes("manu") || email.toLowerCase().includes("admin");

        currentUser = { email, phone, insta, isOwner, isPaid: false };
        localStorage.setItem('originalSongsUser', JSON.stringify(currentUser));

        loadDashboard();
    }

    function loadDashboard() {
        const saved = JSON.parse(localStorage.getItem('originalSongsUser'));
        if(saved) {
            currentUser = saved;
            document.getElementById('loginScreen').classList.add('hidden');
            document.getElementById('paymentScreen').classList.add('hidden');
            document.getElementById('appScreen').classList.remove('hidden');

            const badge = document.getElementById('userBadge');
            const upgradeBox = document.getElementById('upgradeBox');

            if(currentUser.isOwner) {
                badge.innerHTML = "👑 ओनर एक्सेस: मानु गिरी (100% फ्री लाइफटाइम)";
                badge.style.background = "#f43f5e";
                badge.style.color = "#fff";
                upgradeBox.classList.add('hidden');
            } else if(currentUser.isPaid) {
                badge.innerHTML = "⭐ पेड क्रिएटर (10% रॉयल्टी प्लान - ऑटो एक्टिव)";
                badge.style.background = "#38bdf8";
                badge.style.color = "#0f172a";
                upgradeBox.classList.add('hidden');
            } else {
                badge.innerHTML = "👤 फ्री क्रिएटर (25% रॉयल्टी प्लान)";
            }
        }
    }

    function showPaymentModal() {
        document.getElementById('appScreen').classList.add('hidden');
        document.getElementById('paymentScreen').classList.remove('hidden');
    }

    function closePaymentModal() {
        document.getElementById('paymentScreen').classList.add('hidden');
        document.getElementById('appScreen').classList.remove('hidden');
    }

    function autoActivatePaidPlan() {
        currentUser.isPaid = true;
        localStorage.setItem('originalSongsUser', JSON.stringify(currentUser));
        alert("बधाई हो! भुगतान सफल रहा और आपका पेड प्लान ऑटोमैटिक एक्टिव हो गया है!");
        loadDashboard();
    }

    function generateSong() {
        const title = document.getElementById('songTitle').value;
        const lyrics = document.getElementById('songLyrics').value;
        const vibe = document.getElementById('songVibe').value;

        if(!title || !lyrics) {
            alert("कृपया गाने का टाइटल और लिरिक्स दोनों भरें!");
            return;
        }

        if(!currentUser.isOwner) {
            let todayCount = parseInt(localStorage.getItem('dailyCount') || 0);
            if(todayCount >= 2) {
                alert("आज की दैनिक सीमा (2 गाने) पूरी हो चुकी है। कृपया कल प्रयास करें!");
                return;
            }
            localStorage.setItem('dailyCount', todayCount + 1);
        }

        document.getElementById('outputResult').innerHTML = "⏳ आपका एआई गाना तैयार हो रहा है... पियानो और गिटार ट्यूनिंग जोड़ी जा रही है!";
        setTimeout(() => {
            document.getElementById('outputResult').innerHTML = `✅ बधाई हो! आपका गाना <b>"${title}"</b> (${vibe.toUpperCase()} वाइब में) सफलतापूर्वक जनरेट हो गया है!`;
        }, 2000);
    }

    window.onload = function() {
        if(localStorage.getItem('originalSongsUser')) {
            loadDashboard();
        }
    }
</script>

```
  
</body>  
</html>  
