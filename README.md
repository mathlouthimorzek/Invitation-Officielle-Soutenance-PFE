<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Invitation Soutenance - Morzek Mathlouthi</title>
    <!-- Google Fonts pour une belle typographie -->
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700&display=swap" rel="stylesheet">
    
    <style>
    
        :root {
            --primary-color: #1a252f;
            --accent-color: #d4af37; /* Couleur Or */
            --text-color: #333;
            --bg-gradient: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background: var(--bg-gradient);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            color: var(--text-color);
        }

        /* Conteneur de la carte */
        .invitation-card {
            background: #ffffff;
            border-radius: 16px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            padding: 40px 30px;
            max-width: 500px;
            width: 100%;
            text-align: center;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(212, 175, 55, 0.3);
            transition: transform 0.3s ease;
        }

        .invitation-card:hover {
            transform: translateY(-5px);
        }

        /* En-tête */
        .badge {
            background: var(--primary-color);
            color: #fff;
            padding: 6px 16px;
            border-radius: 50px;
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            display: inline-block;
            margin-bottom: 20px;
        }

        h1 {
            font-size: 1.8rem;
            color: var(--primary-color);
            margin-bottom: 15px;
            font-weight: 700;
        }

        .subtitle {
            font-size: 1rem;
            color: #666;
            margin-bottom: 25px;
            line-height: 1.5;
        }

        .project-title {
            font-style: italic;
            font-weight: 600;
            color: var(--primary-color);
            padding: 15px;
            background: #f8f9fa;
            border-left: 4px solid var(--accent-color);
            border-radius: 4px;
            margin: 20px 0;
            font-size: 0.95rem;
        }

        /* Détails */
        .details-section {
            margin: 30px 0;
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
        }

        .detail-item {
            padding: 10px;
            border-bottom: 1px dashed #ddd;
        }

        .detail-item:last-child {
            border-bottom: none;
        }

        .detail-label {
            font-size: 0.8rem;
            text-transform: uppercase;
            color: #888;
            letter-spacing: 1px;
            margin-bottom: 3px;
        }

        .detail-value {
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--primary-color);
        }

        /* Bouton interactif */
        .btn-maps {
            display: inline-block;
            background: var(--primary-color);
            color: white;
            text-decoration: none;
            padding: 12px 25px;
            border-radius: 30px;
            font-weight: 600;
            font-size: 0.9rem;
            margin-top: 15px;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .btn-maps:hover {
            background: transparent;
            color: var(--primary-color);
            border-color: var(--primary-color);
        }

        /* Compte à rebours */
        .countdown-container {
            margin-top: 30px;
            background: var(--primary-color);
            color: white;
            padding: 15px;
            border-radius: 12px;
        }

        .countdown-title {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 10px;
            color: var(--accent-color);
        }

        .countdown {
            display: flex;
            justify-content: space-around;
        }

        .countdown-item {
            display: flex;
            flex-direction: column;
        }

        .countdown-time {
            font-size: 1.4rem;
            font-weight: 700;
        }

        .countdown-label {
            font-size: 0.7rem;
            color: #ccc;
        }

        /* Footer */
        .footer {
            margin-top: 30px;
            font-size: 0.9rem;
            font-weight: 600;
        }

        .footer span {
            color: var(--accent-color);
        }
    </style>
</head>
<body>

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
                <div class="detail-label">Date & Heure</div>
                <div class="detail-value">Samedi 13 Juin 2026 à 09h45</div>
            </div>
            <div class="detail-item">
                <div class="detail-label">Lieu</div>
                <div class="detail-value">ISET Sfax, Salle CC11</div>
            </div>
        </div>

        <!-- Bouton d'action JavaScript (Simulation de géolocalisation ou action) -->
        <button class="btn-maps" onclick="ouvrirLocalisation()">Voir le lieu sur la carte</button>

        <!-- Compte à rebours dynamique -->
        <div class="countdown-container">
            <div class="countdown-title">L'événement commence dans</div>
            <div class="countdown" id="countdown">
                <div class="countdown-item">
                    <span class="countdown-time" id="days">00</span>
                    <span class="countdown-label">Jours</span>
                </div>
                <div class="countdown-item">
                    <span class="countdown-time" id="hours">00</span>
                    <span class="countdown-label">Heures</span>
                </div>
                <div class="countdown-item">
                    <span class="countdown-time" id="minutes">00</span>
                    <span class="countdown-label">Min</span>
                </div>
                <div class="countdown-item">
                    <span class="countdown-time" id="seconds">00</span>
                    <span class="countdown-label">Sec</span>
                </div>
            </div>
        </div>

        <div class="footer">
            Présenté par <span>Morzek Mathlouthi</span>
        </div>
    </div>

    <!-- --- SCRIPT JAVASCRIPT --- -->
    <script>
        // 1. Fonction interactive pour le bouton
        function ouvrirLocalisation() {
            // Lien vers la position de l'ISET Sfax sur Google Maps
            const urlMaps = "https://maps.google.com/?q=ISET+Sfax";
            window.open(urlMaps, '_blank');
        }

        // 2. Logique du compte à rebours
        const dateSoutenance = new Date("June 13, 2026 09:45:00").getTime();

        const x = setInterval(function() {
            const maintenant = new Date().getTime();
            const distance = dateSoutenance - maintenant;

            // Calcul du temps pour les jours, heures, minutes et secondes
            const jours = Math.floor(distance / (1000 * 60 * 60 * 24));
            const heures = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const secondes = Math.floor((distance % (1000 * 60)) / 1000);

            // Affichage du résultat dans les éléments correspondants
            document.getElementById("days").innerText = jours < 10 ? "0" + jours : jours;
            document.getElementById("hours").innerText = heures < 10 ? "0" + heures : heures;
            document.getElementById("minutes").innerText = minutes < 10 ? "0" + minutes : minutes;
            document.getElementById("seconds").innerText =callSec = secondes < 10 ? "0" + secondes : secondes;

            // Si le compte à rebours est terminé
            if (distance < 0) {
                clearInterval(x);
                document.querySelector(".countdown-container").innerHTML = "<div style='padding: 5px; font-weight: bold; color: #d4af37;'>La soutenance a lieu en ce moment ou s'est terminée !</div>";
            }
        }, 1000);
    </script>
</body>
</html>
