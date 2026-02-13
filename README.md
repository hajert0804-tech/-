<!doctype html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>رسالة عشوائية</title>
  <style>
    body { font-family: system-ui, -apple-system, "Segoe UI", Tahoma, Arial; background:#0b1220; color:#e9eefc; margin:0; }
    .wrap { min-height:100vh; display:flex; align-items:center; justify-content:center; padding:24px; }
    .card { width:min(720px, 100%); background:#121b31; border:1px solid #223055; border-radius:16px; padding:22px; }
    .tag { display:inline-block; font-size:12px; opacity:.8; margin-bottom:12px; }
    .msg { font-size:22px; line-height:1.7; white-space:pre-wrap; }
    .meta { margin-top:16px; font-size:12px; opacity:.7; display:flex; gap:12px; flex-wrap:wrap; }
    button { cursor:pointer; margin-top:18px; background:#2f6bff; border:none; color:white; padding:10px 14px; border-radius:10px; font-size:14px; }
    button:active { transform: translateY(1px); }
  </style>
</head>
<body>
  <div class="wrap">
    <div class="card">
      <div class="tag">رسالة اليوم</div>
      <div id="message" class="msg"></div>
      <div class="meta">
        <span id="count"></span>
        <span id="seed"></span>
      </div>
      <button id="newBtn" type="button">اعرض رسالة ثانية</button>
    </div>
  </div>

  <script>
    // عدّلي الرسائل هنا:
    const messages = [
      "الله يفتح لك أبواب الخير.",
      "ابتسمي، كل شي بيعدّي.",
      "انتي أقوى مما تتخيلين.",
      "خذي نفس… وكمّلي.",
      "رزقك جايك بالطريق."
    ];

    // اختيار عشوائي عند كل فتح
    function pickRandom(arr) {
      return arr[Math.floor(Math.random() * arr.length)];
    }

    function renderRandom() {
      const msg = pickRandom(messages);
      document.getElementById("message").textContent = msg;
      document.getElementById("count").textContent = `عدد الرسائل: ${messages.length}`;
      document.getElementById("seed").textContent = `وقت العرض: ${new Date().toLocaleString("ar-BH")}`;
    }

    document.getElementById("newBtn").addEventListener("click", renderRandom);
    renderRandom();
  </script>
</body>
</html>
