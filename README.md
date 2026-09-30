<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <title>Proff Bilvask – Bestill time</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        :root {
            --primary: #0b5fff;
            --dark: #111827;
            --light: #f9fafb;
            --accent: #fbbf24;
        }
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body {
            font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            background: var(--light);
            color: #111;
            line-height: 1.6;
        }
        header {
            background: linear-gradient(135deg, #020617, #0b5fff);
            color: white;
            padding: 2.5rem 1.5rem;
        }
        .container {
            max-width: 1100px;
            margin: 0 auto;
        }
        .hero {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 2rem;
        }
        .hero-text {
            flex: 1 1 280px;
        }
        .hero-text h1 {
            font-size: 2.4rem;
            margin-bottom: 0.5rem;
        }
        .hero-text p {
            margin-bottom: 1rem;
        }
        .hero-badge {
            display: inline-block;
            background: rgba(15,23,42,0.7);
            padding: 0.4rem 0.8rem;
            border-radius: 999px;
            font-size: 0.85rem;
            margin-bottom: 0.8rem;
        }
        .hero-price {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--accent);
            margin-bottom: 1rem;
        }
        .hero-actions {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
        }
        .btn {
            border: none;
            cursor: pointer;
            padding: 0.7rem 1.4rem;
            border-radius: 999px;
            font-weight: 600;
            font-size: 0.95rem;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.4rem;
        }
        .btn-primary {
            background: var(--accent);
            color: #111827;
        }
        .btn-outline {
            background: transparent;
            border: 1px solid rgba(148,163,184,0.7);
            color: #e5e7eb;
        }
        .hero-image {
            flex: 1 1 260px;
            min-height: 220px;
            border-radius: 1rem;
            background: radial-gradient(circle at top left, #fbbf24 0, #0b5fff 40%, #020617 100%);
            position: relative;
            overflow: hidden;
        }
        .hero-car {
            position: absolute;
            bottom: 0;
            right: 5%;
            width: 70%;
            height: 55%;
            border-radius: 1rem;
            background: linear-gradient(145deg, #020617, #111827);
            box-shadow: 0 20px 40px rgba(0,0,0,0.7);
        }
        .hero-glow {
            position: absolute;
            top: 10%;
            left: 5%;
            width: 40%;
            height: 40%;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(248,250,252,0.9), transparent 70%);
            opacity: 0.7;
        }

        main {
            padding: 2.5rem 1.5rem 3rem;
        }
        section {
            margin-bottom: 2.5rem;
        }
        section h2 {
            font-size: 1.6rem;
            margin-bottom: 1rem;
            color: var(--dark);
        }

        /* Pakker */
        .packages {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 1.5rem;
        }
        .card {
            background: white;
            border-radius: 1rem;
            padding: 1.4rem;
            box-shadow: 0 10px 25px rgba(15,23,42,0.08);
            border: 1px solid #e5e7eb;
        }
        .card h3 {
            font-size: 1.2rem;
            margin-bottom: 0.4rem;
        }
        .card-price {
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 0.6rem;
        }
        .card ul {
            list-style: none;
            margin-top: 0.4rem;
        }
        .card li {
            font-size: 0.95rem;
            margin-bottom: 0.3rem;
        }
        .card li::before {
            content: "• ";
            color: var(--accent);
        }

        /* Booking */
        .booking {
            display: grid;
            grid-template-columns: minmax(0, 1.4fr) minmax(0, 1fr);
            gap: 1.8rem;
            align-items: flex-start;
        }
        @media (max-width: 800px) {
            .booking {
                grid-template-columns: 1fr;
            }
        }
        form {
            background: white;
            border-radius: 1rem;
            padding: 1.4rem;
            box-shadow: 0 10px 25px rgba(15,23,42,0.08);
            border: 1px solid #e5e7eb;
        }
        .form-row {
            margin-bottom: 0.9rem;
        }
        label {
            display: block;
            font-size: 0.9rem;
            margin-bottom: 0.2rem;
            color: #374151;
        }
        input, select, textarea {
            width: 100%;
            padding: 0.55rem 0.6rem;
            border-radius: 0.5rem;
            border: 1px solid #d1d5db;
            font-size: 0.95rem;
        }
        textarea {
            min-height: 70px;
            resize: vertical;
        }
        .form-row-inline {
            display: flex;
            gap: 0.8rem;
        }
        .form-row-inline .form-row {
            flex: 1;
            margin-bottom: 0;
        }
        .booking-info {
            font-size: 0.95rem;
            color: #4b5563;
        }
        .booking-info p {
            margin-bottom: 0.6rem;
        }
        .booking-highlight {
            background: #eff6ff;
            border-radius: 0.75rem;
            padding: 0.8rem;
            border: 1px solid #bfdbfe;
            margin-top: 0.6rem;
        }

        /* Om oss */
        .about {
            display: grid;
            grid-template-columns: minmax(0, 1.3fr) minmax(0, 1fr);
            gap: 1.5rem;
        }
        @media (max-width: 800px) {
            .about {
                grid-template-columns: 1fr;
            }
        }
        .about-highlight {
            background: #111827;
            color: #e5e7eb;
            border-radius: 1rem;
            padding: 1.2rem;
        }

        footer {
            background: #020617;
            color: #9ca3af;
            padding: 1.5rem;
            font-size: 0.85rem;
        }
        footer a {
            color: #e5e7eb;
            text-decoration: none;
        }
        footer a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
<header>
    <div class="container hero">
        <div class="hero-text">
            <span class="hero-badge">Lokal proff bilvask</span>
            <h1>Proff bilvask – innvendig & utvendig</h1>
            <p>Gi bilen din en skikkelig spa‑behandling med grundig innvendig og utvendig vask – perfekt for både hverdagsbil og firmabil.</p>
            <p class="hero-price">Fra kun 500 kr · + voksing 50 kr ekstra</p>
            <div class="hero-actions">
                <a href="#booking" class="btn btn-primary">Bestill time nå</a>
                <a href="#pakker" class="btn btn-outline">Se pakker</a>
            </div>
        </div>
        <div class="hero-image" aria-hidden="true">
            <div class="hero-glow"></div>
            <div class="hero-car"></div>
        </div>
    </div>
</header>

<main class="container">
    <!-- Pakker -->
    <section id="pakker">
        <h2>Våre pakker</h2>
        <p>Velg pakken som passer best for deg. Alle vasker utføres nøye og med fokus på detaljer.</p>
        <div class="packages">
            <div class="card">
                <h3>Standard vask</h3>
                <p class="card-price">500 kr</p>
                <ul>
                    <li>Innvendig støvsuging og enkel interiørrengjøring</li>
                    <li>Utvendig håndvask med skånsomme produkter</li>
                    <li>Felgrens og vindusvask</li>
                </ul>
            </div>
            <div class="card">
                <h3>Premium vask</h3>
                <p class="card-price">550 kr</p>
                <ul>
                    <li>Alt i Standard vask</li>
                    <li>Voksing av bil for ekstra glans</li>
                    <li>Ekstra fokus på detaljer og finish</li>
                </ul>
            </div>
            <div class="card">
                <h3>Bedrift / flåte</h3>
                <p class="card-price">Pris etter avtale</p>
                <ul>
                    <li>Fast avtale for flere biler</li>
                    <li>Fleksible tider og prioritet</li>
                    <li>Faktura og bedriftsavtale mulig</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- Booking -->
    <section id="booking">
        <h2>Bestill time</h2>
        <div class="booking">
            <form>
                <div class="form-row-inline">
                    <div class="form-row">
                        <label for="navn">Navn</label>
                        <input id="navn" type="text" placeholder="Fullt navn">
                    </div>
                    <div class="form-row">
                        <label for="telefon">Telefon</label>
                        <input id="telefon" type="tel" placeholder="Telefonnummer">
                    </div>
                </div>

                <div class="form-row-inline" style="margin-top:0.9rem;">
                    <div class="form-row">
                        <label for="dato">Ønsket dato</label>
                        <input id="dato" type="date">
                    </div>
                    <div class="form-row">
                        <label for="tid">Ønsket klokkeslett</label>
                        <input id="tid" type="time">
                    </div>
                </div>

                <div class="form-row" style="margin-top:0.9rem;">
                    <label for="pakke">Velg pakke</label>
                    <select id="pakke">
                        <option>Standard vask – 500 kr</option>
                        <option>Premium vask (inkl. voks) – 550 kr</option>
                        <option>Bedrift / flåte – pris etter avtale</option>
                    </select>
                </div>

                <div class="form-row">
                    <label for="bil">Biltype / registreringsnummer</label>
                    <input id="bil" type="text" placeholder="F.eks. VW Golf, XX12345">
                </div>

                <div class="form-row">
                    <label for="melding">Tilleggsinfo</label>
                    <textarea id="melding" placeholder="Skriv gjerne om spesielle ønsker eller ekstra skitten bil."></textarea>
                </div>

                <div class="form-row">
                    <button type="submit" class="btn btn-primary">Send forespørsel</button>
                </div>
            </form>

            <div class="booking-info">
                <p><strong>Slik fungerer booking:</strong></p>
                <p>Du sender inn ønsket tid og pakke, så bekrefter vi tidspunktet via SMS eller e‑post. Dersom tiden er opptatt, foreslår vi nærmeste ledige tidspunkt.</p>
                <div class="booking-highlight">
                    <p><strong>Åpningstider (eksempel):</strong><br>
                        Mandag–fredag: 09:00–18:00<br>
                        Lørdag: 10:00–15:00
                    </p>
                    <p style="margin-top:0.4rem;">
                        Ønsker du hastevask eller fast avtale for flere biler? Ta kontakt direkte på telefon.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Om oss -->
    <section id="om-oss">
        <h2>Om oss</h2>
        <div class="about">
            <div>
                <p>Vi brenner for rene biler og fornøyde kunder. Med fokus på detaljer, gode produkter og personlig service sørger vi for at bilen din ser best mulig ut – både innvendig og utvendig.</p>
                <p style="margin-top:0.6rem;">Enten du har en hverdagsbil, firmabil eller bilflåte, tilpasser vi vasken etter behov. Målet vårt er enkelt: du skal være stolt av bilen din når du kjører herfra.</p>
            </div>
            <div class="about-highlight">
                <p><strong>Kontakt</strong></p>
                <p>Telefon: 000 00 000<br>
                   E‑post: post@dinbilvask.no</p>
                <p style="margin-top:0.6rem;"><strong>Adresse</strong><br>
                   (Skriv inn din adresse her)</p>
                <p style="margin-top:0.6rem;"><strong>Følg oss</strong><br>
                   Instagram / TikTok: @dinbilvask</p>
            </div>
        </div>
    </section>
</main>

<footer>
    <div class="container">
        <p>© <span id="year"></span> Din Bilvask. Alle rettigheter forbeholdt.</p>
        <p>Nettsideutkast generert – tilpass tekst, kontaktinfo og åpningstider etter din bedrift.</p>
    </div>
    <script>
        document.getElementById('year').textContent = new Date().getFullYear();
    </script>
</footer>
</body>
</html>
