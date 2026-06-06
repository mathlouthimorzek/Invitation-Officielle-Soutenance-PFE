
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Invitation Soutenance - Morzek Mathlouthi</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <style>
        /* --- ARCHITECTURE CSS AVANCÉE --- */
        :root {
            --bg-dark: #090d16;
            --gold: #f3c63f;
            --gold-light: #fef08a;
            --card-white: rgba(255, 255, 255, 0.07);
            --card-border: rgba(255, 255, 255, 0.15);
            --text-white: #f8fafc;
            --text-gray: #94a3b8;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--bg-dark);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 30px;
            color: var(--text-white);
            overflow-x: hidden;
            perspective: 1000px; /* Nécessaire pour l'effet 3D */
        }

        /* --- ARRIÈRE-PLAN : MESH GRADIENT ANIMÉ & CHAPEAUX --- */
        .bg-glows {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            pointer-events: none;
            background: 
                radial-gradient(circle at 10% 20%, rgba(212, 175, 55, 0.08) 0%, transparent 40%),
                radial-gradient(circle at 90% 80%, rgba(30, 41, 59, 0.5) 0%, transparent 50%);
            animation: meshMove 20s ease infinite alternate;
        }

        @keyframes meshMove {
            0% { transform: scale(1); }
            100% { transform: scale(1.1); }
        }

        .hats-container {
            position: fixed;
            width: 100%;
            height: 100%;
            z-index: 2;
            pointer-events: none;
        }

        .floating-hat {
            position: absolute;
            font-size: 2.5rem;
            opacity: 0.12;
            bottom: -100px;
            animation: floatUp 22s linear infinite;
        }

        .floating-hat:nth-child(1) { left: 15%; animation-delay: 0s; animation-duration: 18s; }
        .floating-hat:nth-child(2) { left: 35%; animation-delay: 3s; animation-duration: 25s; font-size: 1.8rem; }
        .floating-hat:nth-child(3) { left: 55%; animation-delay: 7s; animation-duration: 21s; }
        .floating-hat:nth-child(4) { left: 75%; animation-delay: 1s; animation-duration: 16s; font-size: 2rem; }
        .floating-hat:nth-child(5) { left: 85%; animation-delay: 9s; animation-duration: 28s; }

        @keyframes floatUp {
            0% {
                transform: translateY(0) rotate(0deg) translateX(0);
                opacity: 0;
            }
            10% { opacity: 0.15; }
            90% { opacity: 0.15; }
            100% {
                transform: translateY(-115vh) rotate(360deg) translateX(50px);
                opacity: 0;
            }
        }

        /* --- CONTENEUR INTERACTIF 3D (TILT CONTAINER) --- */
        .tilt-box {
            position: relative;
            z-index: 10;
            width: 100%;
            max-width: 550px;
            transform-style: preserve-3d;
            transition: transform 0.1s ease-out;
        }

        /* --- LA CARTE : GLASSMORPHISM FUTURISTE --- */
        .invitation-card {
            background: rgba(15, 23, 42, 0.45);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-radius: 30px;
            padding: 50px 40px;
            text-align: center;
            border: 1px solid var(--card-border);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.4),
                        inset 0 1px 0 rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
            transform: translateZ(50px); /* Extrude la carte en 3D */
        }

        /* Effet de reflet lumineux (Glow) qui suit la souris */
        .invitation-card::before {
            content: '';
            position: absolute;
            top: var(--mouse-y, -500px);
            left: var(--mouse-x, -500px);
            width: 350px;
            height: 350px;
            background: radial-gradient(circle, rgba(243, 198, 63, 0.12) 0%, transparent 70%);
            transform: translate(-50%, -50%);
            pointer-events: none;
            z-index: 1;
        }

        /* --- TYPOGRAPHIE & ÉLÉMENTS INTERNES --- */
        .badge {
            background: linear-gradient(90deg, rgba(243, 198, 63, 0.15), transparent);
            color: var(--gold);
            padding: 8px 24px;
            border-radius: 100px;
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 3px;
            display: inline-block;
            margin-bottom: 30px;
            border: 1px solid rgba(243, 198, 63, 0.2);
        }

        h1 {
            font-size: 2.3rem;
            font-weight: 700;
            color: #ffffff;
            line-height: 1.2;
            margin-bottom: 20px;
            background: linear-gradient(180deg, #ffffff 0%, #cbd5e1 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .subtitle {
            font-size: 1.05rem;
            color: var(--text-gray);
            line-height: 1.6;
            margin-bottom: 30px;
        }

        .subtitle strong {
            color: var(--text-white);
        }

        /* Encadré Projet Extrudé */
        .project-title {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.05);
            border-left: 4px solid var(--gold);
            padding: 24px;
            border-radius: 16px;
            font-size: 1.05rem;
            line-height: 1.6;
            color: #e2e8f0;
            text-align: left;
            margin: 30px 0;
            transform: translateZ(30px); /* Effet de profondeur */
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        /* Grid des Détails */
        .details-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin: 35px 0;
        }

        @media (max-width: 500px) {
            .details-section { grid-template-columns: 1fr; }
        }

        .detail-item {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(255, 255, 255, 0.04);
            border-radius: 16px;
            padding: 18px;
            transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
        }

        .detail-item:hover {
            background: rgba(255, 255, 255, 0.06);
            border-color: rgba(243, 198, 63, 0.3);
            transform: translateY(-3px);
        }

        .detail-label {
            font-size: 0.75rem;
            color: var(--gold);
            text-transform: uppercase;
            letter-spacing: 1.5px;
            margin-bottom: 6px;
            font-weight: 600;
        }

        .detail-value {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--text-white);
        }

        /* Bouton Néo-brutaliste lumineux */
        .btn-maps {
            width: 100%;
            background: linear-gradient(135deg, var(--gold) 0%, #d97706 100%);
            color: #090d16;
            border: none;
            padding: 16px 32px;
            border-radius: 16px;
            font-size: 1rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 0 20px rgba(243, 198, 63, 0.2);
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            transform: translateZ(20px);
        }

        .btn-maps:hover {
            transform: translateZ(30px) translateY(-2px);
            box-shadow: 0 0 30px rgba(243, 198, 63, 0.45);
            background: linear-gradient(135deg, var(--gold-light) 0%, var(--gold) 100%);
        }

        /* Compte à rebours High-Tech */
        .countdown-container {
            margin-top: 40px;
            background: rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.05);
            padding: 24px;
            border-radius: 20px;
        }

        .countdown-title {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: var(--text-gray);
            margin-bottom: 16px;
        }

        .countdown {
            display: flex;
            justify-content: space-around;
        }

        .countdown-time {
            font-size: 2rem;
            font-weight: 700;
            color: #ffffff;
            text-shadow: 0 0 10px rgba(255,255,255,0.1);
        }

        .countdown-label {
            font-size: 0.65rem;
            color: var(--gold);
            text-transform: uppercase;
            margin-top: 4px;
            font-weight: 500;
        }

        /* Footer */
        .footer {
            margin-top: 40px;
            font-size: 0.95rem;
            color: var(--text-gray);
            border-top: 1px solid rgba(255,255,255,0.06);
            padding-top: 24px;
        }

        .footer span {
            color: var(--gold);
            font-weight: 700;
        }
    </style>
</head>
<body>

    <div class="bg-glows"></div>
    <div class="hats-container">
        <span class="floating-hat">🎓</span>
        <span class="floating-hat">🎓</span>
        <span class="floating-hat">🎓</span>
        <span class="floating-hat">🎓</span>
        <span class="floating-hat">🎓</span>
    </div>

    <div class="tilt-box" id="tiltCard">
        <div class="invitation-card">
            <div class="badge">Invitation Officielle</div>
            <h1>Soutenance de PFE</h1>
            
            <p class="subtitle">
                J'ai le plaisir de vous inviter à la présentation de mon projet de fin d'études mené chez <strong>VERMEG</strong> pour le client <strong>Banque de France</strong>.
            </p>

            <div class="project-title">
                « Conception et développement d'une application microservices pour la génération et la signature électronique de factures »
            </div>

            <div class="details-section">
                <div class="detail-item">
                    <div class="detail-label">🗓️ Date & Heure</div>
                    <div class="detail-value">Samedi 13 Juin 2026</div>
                    <div style="font-size: 0.85rem; color: var(--text-gray); margin-top:4px;">à 09h45</div>
                </div>
                <div class="detail-item">
                    <div class="detail-label">📍 Lieu</div>
                    <div class="detail-value">ISET Sfax</div>
                    <div style="font-size: 0.85rem; color: var(--text-gray); margin-top:4px;">Salle CC11</div>
                </div>
            </div>

            <button class="btn-maps" onclick="ouvrirLocalisation()">
                <span>Localiser l'événement</span> ➔
            </button>

            <div class="countdown-container">
                <div class="countdown-title">Lancement dans</div>
                <div class="countdown">
                    <div class="countdown-item"><span class="countdown-time" id="days">00</span><span class="countdown-label">Jours</span></div>
                    <div class="countdown-item"><span class="countdown-time" id="hours">00</span><span class="countdown-label">Heures</span></div>
                    <div class="countdown-item"><span class="countdown-time" id="minutes">00</span><span class="countdown-label">Min</span></div>
                    <div class="countdown-item"><span class="countdown-time" id="seconds">00</span><span class="countdown-label">Sec</span></div>
                </div>
            </div>

            <div class="footer">
                Présenté par : <span>Morzek Mathlouthi</span>
            </div>
        </div>
    </div>

    <script>
        // 1. Redirection Géolocalisation
        function ouvrirLocalisation() {
            window.open("https://maps.google.com/?q=ISET+Sfax", '_blank');
        }

        // 2. Logique Avancée de l'effet Parallaxe 3D (Tilt)
        const card = document.getElementById('tiltCard');
        const innerCard = card.querySelector('.invitation-card');

        document.addEventListener('mousemove', (e) => {
            const xAxis = (window.innerWidth / 2 - e.pageX) / 25;
            const yAxis = (window.innerHeight / 2 - e.pageY) / 25;
            card.style.transform = `rotateY(${xAxis}deg) rotateX(${-yAxis}deg)`;

            // Calcul du reflet lumineux (Glow effect mapped variables)
            const rect = innerCard.getBoundingClientRect();
            const x = e.clientX - rect.left;
            const y = e.clientY - rect.top;
            innerCard.style.setProperty('--mouse-x', `${x}px`);
            innerCard.style.setProperty('--mouse-y', `${y}px`);
        });

        // Reset de l'inclinaison quand la souris sort de l'écran
        document.addEventListener('mouseleave', () => {
            card.style.transform = `rotateY(0deg) rotateX(0deg)`;
        });

        // 3. Compte à Rebours Synchrone
        const dateSoutenance = new Date("June 13, 2026 09:45:00").getTime();

        setInterval(function() {
            const maintenant = new Date().getTime();
            const distance = dateSoutenance - maintenant;

            const jours = Math.floor(distance / (1000 * 60 * 60 * 24));
            const heures = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const secondes = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("days").innerText = jours < 10 ? "0" + jours : jours;
            document.getElementById("hours").innerText = heures < 10 ? "0" + heures : heures;
            document.getElementById("minutes").innerText = minutes < 10 ? "0" + minutes : minutes;
            document.getElementById("seconds").innerText = secondes < 10 ? "0" + secondes : secondes;

            if (distance < 0) {
                document.querySelector(".countdown-container").innerHTML = "<div style='color: var(--gold); font-weight:600;'>La soutenance est en cours ou terminée !</div>";
            }
        }, 1000);
    </script>
</body>
</html>
