<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yelkencinin Not Defteri</title>
    <style>
        body { font-family: 'Segoe UI', sans-serif; background: #eef2f5; padding: 15px; display: flex; justify-content: center; margin: 0; }
        .app { width: 100%; max-width: 450px; background: white; min-height: 100vh; box-shadow: 0 10px 30px rgba(0,0,0,0.1); border-radius: 15px; overflow: hidden; }
        header { background: #002b5c; color: white; padding: 25px; text-align: center; border-bottom: 5px solid #f1c40f; }
        .content { padding: 20px; }
        
        .btn { 
            display: block; width: 100%; padding: 16px; margin-bottom: 12px; 
            border: 2px solid #002b5c; background: white; color: #002b5c; 
            font-weight: bold; border-radius: 10px; cursor: pointer; 
            font-size: 15px; transition: 0.2s; box-sizing: border-box;
            outline: none; /* Varsayılan mavi çizgiyi kaldırır */
        }

        /* Tıkladığın anda (basılı tutarken veya seçiliyken) mavi olması için */
        .btn:focus { 
            background-color: #004a99; 
            color: white; 
        }

        .btn:hover { background: #002b5c; color: white; }
        
        .page { display: none; }
        .active { display: block; }
        .info-card { background: #f8fafc; padding: 15px; border-left: 5px solid #f1c40f; margin-bottom: 12px; border-radius: 6px; font-size: 14px; line-height: 1.6; }
        .q-text { font-size: 17px; font-weight: bold; text-align: center; margin-bottom: 20px; color: #1a365d; }
        .footer-btn { background: #fff; color: #d9534f; border-color: #d9534f; margin-top: 20px; }
        
        /* Mobildeki o çirkin mavi gölgeyi kaldırır, sadece bizim verdiğimiz renk kalsın */
        * { -webkit-tap-highlight-color: transparent; }
    </style>
</head>
<body>

<div class="app">
    <header>
        <h1 style="margin:0; font-size: 20px;">İSİM DAHA BULAMADIM</h1>
        <p style="margin:5px 0 0; opacity: 0.8; font-size: 13px;">teknik, sözlük, donanım blabla </p>
    </header>

    <div class="content">
        <div id="home" class="page active">
            <button class="btn" onclick="openPage('taktik')">TAKTİKİMSİ</button>
            <button class="btn" onclick="openPage('donanim')">DENİZCİLİK SÖZLÜĞÜ</button>
            <button class="btn" onclick="openQuiz()">TEST ET</button>
        </div>

        <div id="taktik" class="page">
            <h3 style="color:#002b5c; margin-top:0;">Stratejik Notlar</h3>
            <div class="info-card"><strong>Start Hattı:</strong> Rüzgar üstü pozisyonu, rakiplerinize "kirli hava" göndererek onları yavaşlatmanızı sağlar.</div>
            <div class="info-card"><strong>Şamandıra Dönüşü:</strong> "Geniş gir, dar çık" kuralı teknenin momentumunu korur ve bir sonraki seyre daha hızlı başlamanızı sağlar.</div>
            <div class="info-card"><strong>Rüzgar Okuma:</strong> Deniz üzerindeki koyu renkli pırpırlar sağanakları, açık renkli yerler ise rüzgarın azaldığı bölgeleri gösterir.</div>
            <button class="btn footer-btn" onclick="openPage('home')">🏠 ANA MENÜYE DÖN</button>
        </div>

        <div id="donanim" class="page">
            <h3 style="color:#002b5c; margin-top:0;">Teknenin Bölümleri ve Bileşenleri</h3>
            <div class="info-card"><strong>Ana Yelken:</strong>Teknenin ana direğine bağlı olan büyük yelkendir. Rüzgarın kuvvetini tekneye ileterek hareket sağlar.</div>
            <div class="info-card"><strong>Baş:</strong> Teknenin ön tarafındaki bölgeyi ifade eden genel bir yön terimidir.</div>
            <div class="info-card"><strong>Borda:</strong> Teknenin sağ ve sol yan yüzeylerinin genel adıdır.</div>
            <div class="info-card"><strong>Bumba (Boom):</strong> Yelkenli teknelerde ana yelkenun alt kenarının bağlı olduğu yatay hareketli direktir.</div>
            <div class="info-card"><strong>Dümen:</strong> Yol alan bir teknenin yönünü değiştirmedeki en etkili parça.</div>
            <div class="info-card"><strong>İskele:</strong> Teknenin sol tarafıdır.</div>
            <div class="info-card"><strong>Sancak:</strong> Teknenin sağ tarafıdır.</div>
            <button class="btn footer-btn" onclick="openPage('home')">🏠 ANA MENÜYE DÖN</button>
        </div>

        <div id="quiz" class="page">
            <div id="q-content">
                <p id="q-text" class="q-text"></p>
                <div id="q-options"></div>
            </div>
            <button class="btn footer-btn" onclick="openPage('home')">🏠 ANA MENÜYE DÖN</button>
        </div>
    </div>
</div>

<script>
    const questions = [
        { q: "Rüzgara en yakın (45°) seyir hangisidir?", a: ["Orsa", "Pupa", "Geniş Apaz"], c: "Orsa" },
        { q: "Rüzgarı tam arkadan aldığımız seyir?", a: ["Pupa", "Apaz", "Dar Apaz"], c: "Pupa" },
        { q: "Dümeni iterek (orsalayarak) yaptığımız manevranın adı nedir?", a: ["Kavança", "Tramola", "Orsa"], c: "Tramola" }
    ];

    function openPage(id) {
        // Yeni sayfaya geçerken herhangi bir butonda "mavi" seçim kalmasın diye odağı temizle
        if (document.activeElement) {
            document.activeElement.blur();
        }
        document.querySelectorAll('.page').forEach(p => p.style.display = 'none');
        document.getElementById(id).style.display = 'block';
    }

    function openQuiz() {
        openPage('quiz');
        renderQuiz(0);
    }

    function renderQuiz(idx) {
        // Bir sonraki soruya geçerken sayfadaki tüm "mavi seçim" hafızasını siler
        if (document.activeElement) {
            document.activeElement.blur();
        }

        const item = questions[idx];
        const qText = document.getElementById('q-text');
        const box = document.getElementById('q-options');

        qText.innerText = item.q;
        box.innerHTML = '';

        item.a.forEach(opt => {
            const b = document.createElement('button');
            b.className = 'btn';
            b.innerText = opt;
            
            b.onclick = (e) => {
                // Cevaba bakmadan hemen önce alert çıkmadan bu fonksiyonun çalışması gerekebilir
                // ama biz asıl sıfırlamayı renderQuiz'in başında yapıyoruz.

                if(opt === item.c) {
                    alert("Doğru! ⛵");
                } else {
                    alert("Yanlış. Cevap: " + item.c);
                }
                
                if(idx + 1 < questions.length) {
                    renderQuiz(idx + 1);
                } else {
                    alert("Test tamamlandı!");
                    openPage('home');
                }
            };
            box.appendChild(b);
        });
    }
</script>

</body>
</html>
