<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Invitation Soutenance - Morzek Mathlouthi</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <style>
        /* --- ARCHITECTURE CSS AVANCÉE (PALETTE CLAIRE ET ÉPURÉE) --- */
        :root {
            --bg-light: #fdfdfd;
            --bg-mesh: #f1f5f9;
            --gold-deep: #b45309; /* Or ambré pour un contraste parfait et lisible */
            --gold-accent: #d97706;
            --gold-soft: #fef3c7;
            --card-pure-white: rgba(255, 255, 255, 0.85);
            --card-border: rgba(212, 175, 55, 0.2);
            --text-charcoal: #0f172a;
            --text-slate: #475569;
            --shadow-fluid: 0 30px 60px rgba(15, 23, 42, 0.06), 0 10px 20px rgba(15, 23, 42, 0.02);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--bg-light);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 30px;
            color: var(--text-charcoal);
            overflow-x: hidden;
            perspective: 1200px; /* Force l'immersion de l'effet 3D */
        }

        /* --- ARRIÈRE-PLAN : DÉGRADÉ MESH CLAIR & CHAPEAUX FLOUTÉS --- */
        .bg-glows {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            pointer-events: none;
            background: 
                radial-gradient(circle at 15% 15%, rgba(212, 175, 55, 0.08) 0%, transparent 35%),
                radial-gradient(circle at 85% 85%, var(--bg-mesh) 0%, transparent 50%);
            animation: meshVibe 25s ease infinite alternate;
        }

        @keyframes meshVibe {
            0% { transform: scale(1) translate(0px, 0px); }
            100% { transform: scale(1.05) translate(10px, -10px); }
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
            font-size: 2.2rem;
            opacity: 0.12;
            bottom: -100px;
            filter: drop-shadow(0 4px 6px rgba(0,0,0,0.02));
            animation: floatUpward 20s linear infinite;
        }

        .floating-hat:nth-child(1) { left: 10%; animation-delay: 0s; animation-duration: 18s; }
        .floating-hat:nth-child(2) { left: 30%; animation-delay: 4s; animation-duration: 24s; font-size: 1.6rem; }
        .floating-hat:nth-child(3) { left: 50%; animation-delay: 2s; animation-duration: 21s; }
        .floating-hat:nth-child(4) { left: 70%; animation-delay: 6s; animation-duration: 17s; font-size: 1.9rem; }
        .floating-hat:nth-child(5) { left: 90%; animation-delay: 1s; animation-duration: 26s; }

        @keyframes floatUpward {
            0% {
                transform: translateY(0) rotate(0deg) translateX(0);
                opacity: 0;
            }
            15% { opacity: 0.16; }
            85% { opacity: 0.16; }
            100% {
                transform: translateY(-115vh) rotate(180deg) translateX(40px);
                opacity: 0;
            }
        }

        /* --- CONTENEUR 3D INTERACTIF --- */
        .tilt-box {
            position: relative;
            z-index: 10;
            width: 100%;
            max-width: 550px;
            transform-style: preserve-3d;
            transition: transform 0.15s ease-out;
        }

        /* --- LA CARTE EMBLÉMATIQUE : GLASSMORPHISM CLAIR --- */
        .invitation-card {
            background: var(--card-pure-white);
            backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px);
            border-radius: 32px;
            padding: 50px 40px;
            text-align: center;
            border: 1px solid var(--card-border);
            box-shadow: var(--shadow-fluid), inset 0 1px 1px rgba(255, 255, 255, 0.9);
            position: relative;
            overflow: hidden;
            transform: translateZ(60px); /* Accentue l'effet d'élévation */
        }

        /* Halo lumineux subtil qui suit le curseur */
        .invitation-card::before {
            content: '';
            position: absolute;
            top: var(--mouse-y, -500px);
            left: var(--mouse-x, -500px);
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(212, 175, 55, 0.12) 0%, transparent 70%);
            transform: translate(-50%, -50%);
            pointer-events: none;
            z-index: 1;
        }

        /* --- STYLES INTERNES --- */
        .badge {
            background: linear-gradient(135deg, var(--gold-soft) 0%, rgba(254, 243, 199, 0.2) 100%);
            color: var(--gold-deep);
            padding: 8px 24px;
            border-radius: 100px;
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 3px;
            display: inline-block;
            margin-bottom: 28px;
            border: 1px solid rgba(217, 119, 6, 0.15);
        }

        h1 {
            font-size: 2.25rem;
            font-weight: 700;
            color: var(--text-charcoal);
            letter-spacing: -0.5px;
            line-height: 1.25;
            margin-bottom: 18px;
        }

        .subtitle {
            font-size: 1.05rem;
            color: var(--text-slate);
            line-height: 1.65;
            margin-bottom: 28px;
        }

        .subtitle strong {
            color: var(--text-charcoal);
            font-weight: 600;
        }

        /* Section Titre de Projet */
        .project-title {
            background: rgba(255, 255, 255, 0.6);
            border: 1px solid rgba(212, 175, 55, 0.18);
            border-left: 4px solid var(--gold-accent);
            padding: 24px;
            border-radius: 16px;
            font-size: 1.05rem;
            line-height: 1.6;
            color: var(--text-charcoal);
            text-align: left;
            margin: 28px 0;
            transform: translateZ(30px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.01);
        }

        /* Grille d'Informations */
        .details-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin: 32px 0;
        }

        @media (max-width: 500px) {
            .details-section { grid-template-columns: 1fr; gap: 15px; }
        }

        .detail-item {
            background: rgba(255, 255, 255, 0.4);
            border: 1px solid rgba(15, 23, 42, 0.04);
            border-radius: 16px;
            padding: 18px;
            transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .detail-item:hover {
            background: #ffffff;
            border-color: rgba(217, 119, 6, 0.25);
            transform: translateY(-3px);
            box-shadow: 0 12px 24px rgba(0, 0, 0, 0.03);
        }

        .detail-label {
            font-size: 0.75rem;
            color: var(--gold-accent);
            text-transform: uppercase;
            letter-spacing: 1.5px;
            margin-bottom: 6px;
            font-weight: 600;
        }

        .detail-value {
            font-size: 1.05rem;
            font-weight: 700;
            color: var(--text-charcoal);
        }

        /* Bouton Action Ultra Moderne */
        .btn-maps {
            width: 100%;
            background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
            color: #ffffff;
            border: none;
            padding: 16px 32px;
            border-radius: 16px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.25s ease;
            box-shadow: 0 10px 25px rgba(15, 23, 42, 0.1);
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            transform: translateZ(20px);
        }

        .btn-maps:hover {
            transform: translateZ(35px) translateY(-2px);
            box-shadow: 0 12px 28px rgba(217, 119, 6, 0.2);
            background: linear-gradient(135deg, var(--gold-accent) 0%, var(--gold-deep) 100%);
        }

        /* Compte à rebours Haute-Visibilité */
        .countdown-container {
            margin-top: 38px;
            background: #0f172a; /* Préservé en bleu nuit pour faire ressortir le compte à rebours technologique */
            color: #ffffff;
            padding: 24px;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(15, 23, 42, 0.08);
        }

        .countdown-title {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: #94a3b8;
            margin-bottom: 16px;
        }

        .countdown {
            display: flex;
            justify-content: space-around;
        }

        .countdown-time {
            font-size: 1.9rem;
            font-weight: 700;
            color: #ffffff;
        }

        .countdown-label {
            font-size: 0.65rem;
            color: var(--gold-accent);
            text-transform: uppercase;
            margin-top: 4px;
            font-weight: 600;
        }

        /* Pied de page */
        .footer {
            margin-top: 38px;
            font-size: 0.95rem;
            color: var(--text-slate);
            border-top: 1px solid rgba(0, 0, 0, 0.05);
            padding-top: 24px;
        }

        .footer span {
            color: var(--text-charcoal);
            font-weight: 700;
        }
    </style>
</head>
<body>

    <!-- Structure d'Arrière-plan -->
    <div class="bg-glows"></div>
    <div class="hats-container">
        <span class="floating-hat">🎓</span>
        <span class="floating-hat">🎓</span>
        <span class="floating-hat">🎓</span>
        <span class="floating-hat">🎓</span>
        <span class="floating-hat">🎓</span>
    </div>

    <!-- Conteneur Parallaxe 3D -->
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
                    <div style="font-size: 0.85rem; color: var(--text-slate); margin-top:4px;">à 09h45</div>
                </div>
                <div class="detail-item">
                    <div class="detail-label">📍 Lieu</div>
                    <div class="detail-value">ISET Sfax</div>
                    <div style="font-size: 0.85rem; color: var(--text-slate); margin-top:4px;">Salle CC11</div>
                </div>
            </div>

            <button class="btn-maps" onclick="ouvrirLocalisation()">
                <span>Localiser l'événement</span> ➔
            </button>

            <!-- Compte à rebours intégré -->
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

    <!-- --- LOGIQUE COMPORTEMENTALE (JAVASCRIPT) --- -->
    <script>
        function ouvrirLocalisation() {
            window.open("https://maps.google.com/?q=ISET+Sfax", '_blank');
        }

        // Gestion Avancée de l'effet d'inclinaison 3D (Tilt effect)
        const card = document.getElementById('tiltCard');
        const innerCard = card.querySelector('.invitation-card');

        document.addEventListener('mousemove', (e) => {
            const xAxis = (window.innerWidth / 2 - e.pageX) / 28;
            const yAxis = (window.innerHeight / 2 - e.pageY) / 28;
            card.style.transform = `rotateY(${xAxis}deg) rotateX(${-yAxis}deg)`;

            // Positionnement dynamique du reflet de lumière interne
            const rect = innerCard.getBoundingClientRect();
            const x = e.clientX - rect.left;
            const y = e.clientY - rect.top;
            innerCard.style.setProperty('--mouse-x', `${x}px`);
            innerCard.style.setProperty('--mouse-y', `${y}px`);
        });

        // Remise à plat lorsque la souris quitte la zone active
        document.addEventListener('mouseleave', () => {
            card.style.transform = `rotateY(0deg) rotateX(0deg)`;
        });

        // Calcul exact et synchronisation temporelle du compte à rebours
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
                document.querySelector(".countdown-container").innerHTML = "<div style='color: var(--gold-accent); font-weight:600;'>La soutenance a débuté ou s'est terminée !</div>";
            }
        }, 1000);
    </script>
</body>
</html>
