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
        .btn { display: block; width: 100%; padding: 16px; margin-bottom: 12px; border: 2px solid #002b5c; background: white; color: #002b5c; font-weight: bold; border-radius: 10px; cursor: pointer; font-size: 15px; transition: 0.2s; box-sizing: border-box; outline: none; }
        .btn:hover { background: #002b5c; color: white; }
        .page { display: none; }
        .active { display: block; }
        .info-card { background: #f8fafc; padding: 15px; border-left: 5px solid #f1c40f; margin-bottom: 12px; border-radius: 6px; font-size: 14px; line-height: 1.6; }
        .q-text { font-size: 17px; font-weight: bold; text-align: center; margin-bottom: 20px; color: #1a365d; }
        .footer-btn { background: #fff; color: #d9534f; border-color: #d9534f; margin-top: 20px; }
    
        /* Mavi kalma sorununu çözen kritik kısım */
        .btn:focus, .btn:active { 
            outline: none !important; 
            background-color: #002b5c !important; 
            color: white !important; 
            box-shadow: none !important;
        }
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
            <div class="info-card"><strong>Ana Yelken:</strong>Teknenin ana direğine bağlı olan büyük yelkendir. Rüzgarın kuvvetini tekneye ileterek hareket sağlar. Genellikle yelkenin şekli ve açısı halatlarla kontrol edilir.</div>
            <div class="info-card"><strong>Baş:</strong> Teknenin ön tarafındaki bölgeyi ifade eden genel bir yön terimidir.</div>
            <div class="info-card"><strong>Borda:</strong> Teknenin sağ ve sol yan yüzeylerinin genel adıdır. Teknenin gövdesinin su üstünde kalan yan kısımlarını ifade eder.</div>
            <div class="info-card"><strong>Bumba (Boom):</strong> Yelkenli teknelerde ana yelkenin alt kenarının bağlı olduğu, direğe tutturulmuş, yelkenin açısını ve formunu kontrol etmeye yarayan, genellikle alüminyumdan yapılan yatay hareketli direktir.</div>
            <div class="info-card"><strong>Cunningham (Kaningam) :</strong> Ana yelkenin ön kenarındaki gerginliği ayarlamak için kullanılan kontrol halatıdır. Yelkenin alt ön köşesinden çekilerek yelken kumaşının gerilmesi sağlanır. Kuvvetli rüzgârlarda yelken formunu düzeltmek için kullanılır.</div>
            <div class="info-card"><strong>Direk:</strong>Yelkenlerin bağlandığı dikey ana yapıdır. Teknenin gövdesine sabitlenir ve yelken sistemi bu yapı üzerinde yükselir.</div>
            <div class="info-card"><strong>Dümen:</strong> Yol alan bir teknenin yönünü değiştirmedeki en etkili parça.</div>
            <div class="info-card"><strong>Dümen Palası:</strong> Dümenin suya batan kısmıdır; suyun basıncını alıp teknenin yönünü değiştirir.</div>
            <div class="info-card"><strong>Extension (Yeke Uzatması) :</strong> Yekenin ucuna takılan uzatma çubuğudur. Yelkencinin teknenin farklı yerlerinde otururken dümeni kontrol edebilmesini sağlar.</div>
            <div class="info-card"><strong>Halat:</strong> Teknede yelkenleri kaldırmak, indirmek veya kontrol etmek için kullanılan tüm iplerin genel adıdır.</div>
            <div class="info-card"><strong>İskele:</strong> Teknenin sol tarafıdır. Denizcilikte yön tariflerinde kullanılan temel terimlerden biridir.</div>
            <div class="info-card"><strong>İskota (Sheet):</strong> Yelkenli teknelerde yelkenlerin rüzgâr yönüne göre açısını ayarlamak için kullanılan, yelkenin alt köşelerine bağlı halattır.</div>
            <div class="info-card"><strong>Kafayı Açmak:</strong> Teknenin yönünü rüzgârdan uzaklaştırarak daha geniş bir açıyla seyretmek anlamına gelir. </div>
            <div class="info-card"><strong>Kavança:</strong> Rüzgârı teknenin kıçından alarak yapılan yön değiştirme manevrasıdır.</div>
            <div class="info-card"><strong>Kıç:</strong> Teknenin arka tarafındaki bölgenin genel adıdır.</div>
            <div class="info-card"><strong>Kontra:</strong> Rüzgârın hangi taraftan geldiğini ifade eden terimdir. Rüzgâr sancaktan geliyorsa sancak kontra, iskeleden geliyorsa iskele kontra denir.</div>
            <div class="info-card"><strong>Mandar (Halyard):</strong> Yelkenli teknelerde ana yelken, flok veya balon gibi yelkenleri direğe yukarı basmaya (çıkarmaya) ve indirmeye yarayan, esnemeyen, güçlü halat sistemleridir.</div>
            <div class="info-card"><strong>Omurga:</strong> Teknenin gövdesinin merkez hattını oluşturan ana yapıdır. Tekneye dayanıklılık ve yapısal sağlamlık sağlar.</div>
            <div class="info-card"><strong>Orsa:</strong> Teknenin rüzgâra mümkün olan en yakın açıyla ilerlediği seyir şeklidir.</div>
            <div class="info-card"><strong>Orsalamak:</strong> Teknenin başını rüzgâra doğru çevirmek, yani rüzgâra daha yakın bir açıyla gitmeye başlamak anlamına gelir.</div>
            <div class="info-card"><strong>Palanga:</strong> Halat ve makaralardan oluşan mekanik sistemdir. Daha az kuvvet kullanarak daha büyük bir yükü çekmeyi ve yelkenlide direği bükmeyi sağlar.</div>
            <div class="info-card"><strong>Pruva:</strong> Teknenin en ön noktası veya ileri bakan kısmıdır. Navigasyon ve seyir tariflerinde kullanılan teknik bir terimdir.</div>
            <div class="info-card"><strong>Pupa:</strong> Teknenin arka yönünü ifade eden bir seyir ve yön terimidir. Aynı zamanda rüzgârın teknenin tam arkasından geldiği seyri ifade etmek için de kullanılır.</div>
            <div class="info-card"><strong>Rüzgâr Altı:</strong> Rüzgarın tekneyi terk ettiği tarafı ifade ederken kullanılan terimdir.</div>
            <div class="info-card"><strong>Rüzgâr Üstü:</strong> Rüzgarın tekneye geldiği tarafı ifade ederken kullanılan terimdir.</div>
            <div class="info-card"><strong>Salma:</strong> Teknenin altına yerleştirilen ve suyun içinde kalan dikey yüzeydir. Teknenin yana kaymasını azaltır ve devrilmeye karşı denge sağlar.</div>
            <div class="info-card"><strong>Sancak:</strong> Teknenin sağ tarafıdır. Denizcilikte yön tariflerinde kullanılan temel terimlerden biridir.</div>
            <div class="info-card"><strong>Tramola:</strong> Orsa seyrinde teknenin başını kör noktadan geçirerek yapılan yön değiştirme manevrasıdır.</div>
            <div class="info-card"><strong>Treyler:</strong> Tekneleri karada taşımak için kullanılan tekerlekli platformdur.</div>
            <div class="info-card"><strong>Yeke:</strong> Dümeni kontrol etmeyi sağlayan yatay çubuktur. Yelkencer bu parçayı sağa veya sola hareket ettirerek teknenin yönünü değiştirir.</div>
            <div class="info-card"><strong>a:</strong> a</div>
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
        document.querySelectorAll('.page').forEach(p => p.style.display = 'none');
        document.getElementById(id).style.display = 'block';
    }

    function openQuiz() {
        openPage('quiz');
        renderQuiz(0);
    }

    function renderQuiz(idx) {
        const item = questions[idx];
        const qText = document.getElementById('q-text');
        const box = document.getElementById('q-options');

        qText.innerText = item.q;
        box.innerHTML = '';

        // Sayfa geçişinde odağı tamamen sıfırla
        if (document.activeElement) {
            document.activeElement.blur();
        }

        item.a.forEach(opt => {
            const b = document.createElement('button');
            b.className = 'btn';
            b.innerText = opt;
            
            b.onclick = (e) => {
                // Tıklanan butondan odağı anında çek
                e.target.blur(); 

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
