<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SKLive</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background: url('/mnt/data/S&K BNC.webp') no-repeat center center fixed;
            background-size: cover;
            color: #333;
        }
        header {
            background: rgba(51, 51, 51, 0.8);
            color: #fff;
            padding: 10px 0;
            text-align: center;
        }
        nav {
            background: rgba(68, 68, 68, 0.8);
            color: #fff;
            display: flex;
            justify-content: space-around;
            padding: 10px;
        }
        nav a {
            color: #fff;
            text-decoration: none;
            padding: 5px 10px;
        }
        nav a:hover {
            background: rgba(85, 85, 85, 0.8);
        }
        section {
            max-width: 1200px;
            margin: auto;
            padding: 20px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        footer {
            background: rgba(51, 51, 51, 0.8);
            color: #fff;
            text-align: center;
            padding: 10px 0;
            margin-top: 20px;
        }
        .hero {
            text-align: center;
            padding: 50px 20px;
            background: rgba(47, 128, 237, 0.8);
            color: #fff;
        }
        .hero h1 {
            margin: 0;
        }
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        .card {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 5px;
            padding: 15px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        .card h3 {
            margin-top: 0;
        }
        .card p {
            margin: 0;
        }
        .live-data {
            background: rgba(238, 238, 255, 0.9);
            border-left: 5px solid #2f80ed;
            padding: 15px;
            margin-top: 20px;
        }
        #logo-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8) url('/mnt/data/S&K BNC.webp') no-repeat center;
            background-size: contain;
            z-index: 1000;
        }
    </style>
    <script>
        async function fetchMarketData() {
            try {
                const response = await fetch('https://api.example.com/market-data'); // Replace with actual API endpoint
                const data = await response.json();
                document.getElementById('live-kurse').textContent = `Aktueller BTC/USD Kurs: $${data.btcUsd}`;
                document.getElementById('handel-zeiten').textContent = `Handelszeiten (Wall Street): ${data.marketHours}`;
            } catch (error) {
                console.error('Fehler beim Abrufen der Marktdaten:', error);
            }
        }

        function hideLogoOverlay() {
            const overlay = document.getElementById('logo-overlay');
            overlay.style.display = 'none';
        }

        window.onload = function() {
            fetchMarketData();
            setTimeout(hideLogoOverlay, 3000); // Hide logo overlay after 3 seconds
        };
    </script>
</head>
<body>
    <div id="logo-overlay"></div>
    <header>
        <h1>SKLive</h1>
    </header>
    <nav>
        <a href="#overview">Überblick</a>
        <a href="#tips">Tipps & Tricks</a>
        <a href="#coins">Münzen kaufen/verkaufen</a>
        <a href="#faq">FAQ</a>
    </nav>
    <div class="hero">
        <h1>Willkommen bei SKLive</h1>
        <p>Erfahren Sie alles über den Handel, das Investieren und mehr!</p>
    </div>
    <section id="overview">
        <h2>Überblick</h2>
        <p>Willkommen bei Ihrer Anlaufstelle für alles rund um Kryptowährungen. Ob Anfänger oder Experte, wir haben die Ressourcen, die Sie benötigen, um erfolgreich zu sein.</p>
    </section>
    <section id="tips">
        <h2>Tipps & Tricks</h2>
        <div class="grid">
            <div class="card">
                <h3>Was ist Krypto?</h3>
                <p>Kryptowährungen sind digitale oder virtuelle Währungen, die Kryptografie für Sicherheit nutzen.</p>
            </div>
            <div class="card">
                <h3>Wie startet man?</h3>
                <p>Fangen Sie klein an. Investieren Sie nur, was Sie sich leisten können, zu verlieren.</p>
            </div>
            <div class="card">
                <h3>Markttrends analysieren</h3>
                <p>Verstehen Sie die Markttrends und achten Sie auf News und Updates.</p>
            </div>
        </div>
    </section>
    <section id="coins">
        <h2>Münzen kaufen & verkaufen</h2>
        <p>Hier finden Sie detaillierte Erklärungen, wann und wo Sie Kryptowährungen kaufen oder verkaufen sollten.</p>
        <ul>
            <li><strong>Bitcoin (BTC):</strong> Idealer Zeitpunkt: Wenn der Markt stabil ist.</li>
            <li><strong>Ethereum (ETH):</strong> Beobachten Sie neue Updates.</li>
            <li><strong>Altcoins:</strong> Vorsichtig investieren, da diese volatiler sind.</li>
        </ul>
        <div class="live-data">
            <p id="live-kurse">Aktueller BTC/USD Kurs: Wird geladen...</p>
            <p id="handel-zeiten">Handelszeiten (Wall Street): Wird geladen...</p>
        </div>
    </section>
    <section id="faq">
        <h2>FAQ</h2>
        <p>Haben Sie Fragen? Hier sind einige häufig gestellte Fragen:</p>
        <ul>
            <li><strong>Ist Krypto sicher?</strong> Ja, wenn Sie sichere Wallets verwenden.</li>
            <li><strong>Wie fange ich an?</strong> Melden Sie sich bei einer vertrauenswürdigen Börse an.</li>
            <li><strong>Welche Wallet sollte ich verwenden?</strong> Hardware-Wallets bieten die beste Sicherheit.</li>
        </ul>
    </section>
    <footer>
        <p>&copy; 2025 SKLive. Alle Rechte vorbehalten.</p>
    </footer>
</body>
</html>
