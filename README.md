# Inscription-COLLEGE5G
Site officiel du collège 5G
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portail d'Inscription - Collège 5G</title>
    <!-- Intégration d'une police moderne (Poppins) et d'icônes -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #0f172a; /* Bleu nuit ultra-professionnel */
            --accent: #2563eb;  /* Bleu moderne "Tech" */
            --accent-hover: #1d4ed8;
            --success: #10b981; /* Vert émeraude */
            --warning: #f59e0b; /* Ambre */
            --danger: #ef4444;  /* Rouge corail */
            --bg-gradient: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
            --text-main: #1e293b;
            --text-muted: #64748b;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: var(--bg-gradient);
            color: var(--text-main);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            width: 100%;
            max-width: 850px;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 24px;
            box-shadow: 0 20px 40px rgba(15, 23, 42, 0.08);
            border: 1px solid rgba(255, 255, 255, 0.7);
            overflow: hidden;
            transition: all 0.5s ease;
        }

        /* En-tête Institutionnel */
        .header-brand {
            background: var(--primary);
            color: white;
            padding: 30px;
            text-align: center;
            position: relative;
        }

        .header-brand h1 {
            font-size: 1.8rem;
            font-weight: 700;
            letter-spacing: 1px;
            margin-bottom: 5px;
        }

        .header-brand p {
            color: #94a3b8;
            font-size: 0.9rem;
        }

        .content-box {
            padding: 40px;
        }

        /* Animations de transition */
        .fade-in {
            animation: fadeIn 0.6s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Écran d'accueil */
        .welcome-card {
            text-align: center;
            padding: 20px 0;
        }

        .welcome-card i {
            font-size: 4rem;
            color: var(--accent);
            margin-bottom: 20px;
        }

        .welcome-card h2 {
            font-size: 1.4rem;
            color: var(--primary);
            line-height: 1.6;
            margin-bottom: 30px;
            font-weight: 600;
        }

        /* Formulaire stylisé */
        fieldset {
            border: none;
            margin-bottom: 30px;
            background: #f8fafc;
            padding: 25px;
            border-radius: 16px;
            border: 1px solid #edf2f7;
        }

        legend {
            font-weight: 600;
            color: var(--primary);
            font-size: 1.1rem;
            padding: 0 10px;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .grid-2 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .form-group {
            margin-bottom: 18px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-size: 0.85rem;
            font-weight: 500;
            color: var(--text-main);
        }

        input, select {
            width: 100%;
            padding: 12px 16px;
            border: 2px solid #cbd5e1;
            border-radius: 10px;
            font-size: 0.95rem;
            background-color: white;
            color: var(--text-main);
            transition: all 0.3s ease;
        }

        input:focus, select:focus {
            outline: none;
            border-color: var(--accent);
            box-shadow: 0 0 0 4px rgba(37, 99, 235, 0.15);
        }

        /* Boutons */
        .btn {
            background-color: var(--accent);
            color: white;
            border: none;
            padding: 14px 32px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 4px 12px rgba(37, 99, 235, 0.2);
        }

        .btn:hover {
            background-color: var(--accent-hover);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(37, 99, 235, 0.3);
        }

        .btn-center {
            display: flex;
            justify-content: center;
            margin-top: 10px;
        }

        .hidden {
            display: none !important;
        }

        #affichage-age {
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--accent);
            margin-top: -5px;
            display: block;
        }

        /* Notifications & Messages de Retour */
        .notification {
            padding: 25px;
            border-radius: 16px;
            margin-top: 10px;
            line-height: 1.6;
            display: flex;
            align-items: flex-start;
            gap: 15px;
            font-size: 1rem;
        }

        .notification i {
            font-size: 1.5rem;
            margin-top: 3px;
        }

        .success { background-color: #ecfdf5; color: #065f46; border: 1px solid #a7f3d0; }
        .warning { background-color: #fffbeb; color: #92400e; border: 1px solid #fde68a; }
        .danger { background-color: #fef2f2; color: #991b1b; border: 1px solid #fecaca; }

        .schedule-box {
            background: #f1f5f9;
            border-left: 5px solid var(--primary);
            padding: 20px;
            border-radius: 0 12px 12px 0;
            margin: 20px 0;
        }

        .schedule-box h4 {
            margin-bottom: 10px;
            color: var(--primary);
        }

        .schedule-box ul {
            list-style-type: none;
        }

        .schedule-box li {
            margin-bottom: 6px;
            padding-left: 15px;
            position: relative;
        }

        .schedule-box li::before {
            content: "•";
            color: var(--accent);
            font-weight: bold;
            position: absolute;
            left: 0;
        }
    </style>
</head>
<body>

<div class="container">
    
    <!-- En-tête fixe -->
    <div class="header-brand">
        <h1>COLLÈGE 5G</h1>
        <p>Excellence - Innovation - Avenir</p>
    </div>

    <div class="content-box">
        
        <!-- FACETTE 1 : INSCRIPTION -->
        <div id="page-inscription" class="fade-in">
            
            <!-- Étape A : Bienvenue -->
            <div id="section-accueil" class="welcome-card">
                <i class="fa-solid fa-graduation-cap"></i>
                <h2>BIENVENUE SUR LE SITE OFFICIEL D'INSCRIPTION EN LIGNE DU COLLÈGE 5G</h2>
                <div class="btn-center">
                    <button class="btn" onclick="commencerInscription()">
                        Commencer l'inscription <i class="fa-solid fa-arrow-right"></i>
                    </button>
                </div>
            </div>

            <!-- Étape B : Formulaire -->
            <form id="form-inscription" class="hidden" onsubmit="traiterInscription(event)">
                
                <fieldset>
                    <legend><i class="fa-solid fa-user"></i> Identité de l'Élève</legend>
                    <div class="grid-2">
                        <div class="form-group">
                            <label>Nom de l'élève</label>
                            <input type="text" id="nom-eleve" placeholder="Ex: Kabamba" required>
                        </div>
                        <div class="form-group">
                            <label>Postnom et Prénom</label>
                            <input type="text" id="prenom-eleve" placeholder="Ex: Jean-Paul" required>
                        </div>
                    </div>
                    <div class="grid-2">
                        <div class="form-group">
                            <label>Lieu de naissance</label>
                            <input type="text" id="lieu-naissance" placeholder="Ex: Kinshasa" required>
                        </div>
                        <div class="form-group">
                            <label>Date de naissance</label>
                            <input type="date" id="date-naissance" required onchange="calculerAge()">
                        </div>
                    </div>
                    <div class="form-group">
                        <span id="affichage-age"></span>
                    </div>
                    <div class="form-group">
                        <label>Adresse de résidence de l'élève</label>
                        <input type="text" id="adresse-eleve" placeholder="N°, Avenue, Quartier, Commune" required>
                    </div>
                </fieldset>

                <fieldset>
                    <legend><i class="fa-solid fa-users"></i> Contacts d'Urgence (Parents & Tuteur)</legend>
                    <div class="grid-2">
                        <div class="form-group">
                            <label>Nom et Postnom du Père</label>
                            <input type="text" id="nom-pere">
                        </div>
                        <div class="form-group">
                            <label>Numéro de Téléphone du Père</label>
                            <input type="tel" id="tel-pere" placeholder="+243...">
                        </div>
                    </div>
                    <div class="grid-2">
                        <div class="form-group">
                            <label>Nom et Postnom de la Mère</label>
                            <input type="text" id="nom-mere">
                        </div>
                        <div class="form-group">
                            <label>Numéro de Téléphone de la Mère</label>
                            <input type="tel" id="tel-mere" placeholder="+243...">
                        </div>
                    </div>
                    <div class="form-group">
                        <label>Adresse de résidence des Parents</label>
                        <input type="text" id="adresse-parents">
                    </div>
                    <hr style="border: 0; height: 1px; background: #e2e8f0; margin: 20px 0;">
                    <div class="grid-2">
                        <div class="form-group">
                            <label>Nom complet du Tuteur</label>
                            <input type="text" id="nom-tuteur">
                        </div>
                        <div class="form-group">
                            <label>Téléphone du Tuteur</label>
                            <input type="tel" id="tel-tuteur" placeholder="+243...">
                        </div>
                    </div>
                    <div class="form-group">
                        <label>Adresse du Tuteur</label>
                        <input type="text" id="adresse-tuteur">
                    </div>
                </fieldset>

                <fieldset>
                    <legend><i class="fa-solid fa-award"></i> Dossier Scolaire</legend>
                    <div class="grid-2">
                        <div class="form-group">
                            <label>Pourcentage obtenu à l'ancienne école (%)</label>
                            <input type="number" id="pourcentage-ancien" min="0" max="100" step="0.1" placeholder="Ex: 65" required>
                        </div>
                        <div class="form-group">
                            <label>Classe souhaitée</label>
                            <select id="classe-souhaitee" required>
                                <option value="">-- Sélectionnez la classe --</option>
                                <option value="7EB">7ème EB</option>
                                <option value="8EB">8ème EB</option>
                                <option value="1_elec">1ère Électronique</option>
                                <option value="2_elec">2ème Électronique</option>
                                <option value="3_elec">3ème Électronique</option>
                                <option value="4_elec">4ème Électronique</option>
                            </select>
                        </div>
                    </div>
                </fieldset>

                <div class="btn-center">
                    <button type="submit" class="btn">
                        <i class="fa-solid fa-paper-plane"></i> Soumettre le dossier
                    </button>
                </div>
            </form>

            <!-- Étape C : Résultat Inscription Directe / Invitation au Test -->
            <div id="resultat-inscription" class="hidden fade-in"></div>
        </div>

        <!-- FACETTE 2 : PAGE ADMIS (TEST D'ADMISSION) -->
        <div id="page-admis" class="hidden fade-in">
            <h2 style="font-size: 1.5rem; margin-bottom: 10px; color: var(--primary);"><i class="fa-solid fa-file-signature"></i> Bureau d'Évaluation du Test</h2>
            <p style="color: var(--text-muted); margin-bottom: 25px;">Veuillez renseigner la performance finale de l'élève ci-dessous.</p>
            
            <div id="infos-test-eleve" style="background: #f8fafc; padding: 20px; border-radius: 12px; margin-bottom: 25px; border-left: 4px solid var(--accent);"></div>
            
            <div class="form-group">
                <label style="font-size: 1rem;">Pourcentage obtenu au test d'admission (%)</label>
                <input type="number" id="pourcentage-test" min="0" max="100" step="0.1" placeholder="Ex: 52" style="max-width: 250px; margin-top: 8px;">
            </div>
            
            <button class="btn" onclick="validerTestAdmission()" style="background-color: var(--primary);">
                <i class="fa-solid fa-square-check"></i> Enregistrer la décision
            </button>
            
            <div id="resultat-test" class="hidden fade-in" style="margin-top: 25px;"></div>
        </div>

    </div>
</div>

<script>
    const ANNEE_EN_COURS = 2026;
    let eleveActuel = {};

    function commencerInscription() {
        document.getElementById('section-accueil').classList.add('hidden');
        document.getElementById('form-inscription').classList.remove('hidden');
    }

    function calculerAge() {
        const dateNaissInput = document.getElementById('date-naissance').value;
        if(dateNaissInput) {
            const dateNaissance = new Date(dateNaissInput);
            const age = ANNEE_EN_COURS - dateNaissance.getFullYear();
            document.getElementById('affichage-age').innerHTML = `<i class="fa-solid fa-clock"></i> Âge calculé pour la rentrée : <strong>${age} ans</strong>`;
            return age;
        }
        return 0;
    }

    function traiterInscription(event) {
        event.preventDefault();
        
        eleveActuel.nom = document.getElementById('nom-eleve').value.toUpperCase();
        eleveActuel.prenom = document.getElementById('prenom-eleve').value;
        eleveActuel.pourcentageAncien = parseFloat(document.getElementById('pourcentage-ancien').value);
        eleveActuel.classe = document.getElementById('classe-souhaitee').value;

        const formIns = document.getElementById('form-inscription');
        const resIns = document.getElementById('resultat-inscription');
        
        formIns.classList.add('hidden');
        resIns.classList.remove('hidden');

        // Cas 1 : Admis d'office (> 60%)
        if (eleveActuel.pourcentageAncien > 60) {
            resIns.innerHTML = `
                <div class="notification success">
                    <i class="fa-solid fa-circle-check"></i>
                    <div>
                        <strong>Félicitations !</strong><br>
                        Votre enfant <strong>${eleveActuel.nom} ${eleveActuel.prenom}</strong> a été officiellement inscrit au Collège 5G. 
                        La rentrée scolaire est fixée au <strong>07 septembre 2026</strong>.
                    </div>
                </div>
            `;
        } 
        // Cas 2 : Doit passer le test (< 60%)
        else {
            let matieres = "";
            let nomClasse = "";
            if (eleveActuel.classe === "7EB" || eleveActuel.classe === "8EB") {
                nomClasse = eleveActuel.classe === "7EB" ? "7ème EB" : "8ème EB";
                matieres = "<li>Français</li><li>Mathématiques</li><li>Culture générale</li>";
            } else {
                nomClasse = eleveActuel.classe.charAt(0) + "ère Électronique";
                matieres = "<li>Mathématiques</li><li>Français</li><li>Électronique</li><li>Hyper fréquences</li>";
            }

            resIns.innerHTML = `
                <div class="notification warning">
                    <i class="fa-solid fa-circle-exclamation"></i>
                    <div>
                        <strong>Test d'admission obligatoire</strong><br>
                        Le pourcentage requis pour l'accès direct n'étant pas atteint, l'élève doit passer un test d'admission le <strong>17/08/2026 à 08h00</strong> précises au sein de l'établissement.
                    </div>
                </div>
                <div class="schedule-box">
                    <h4><i class="fa-solid fa-calendar-days"></i> Matières à composer (${nomClasse}) :</h4>
                    <ul>${matieres}</ul>
                </div>
                <div class="btn-center">
                    <button class="btn" onclick="ouvrirPageTest()" style="background-color: var(--primary);">
                        Passer à l'évaluation du Test <i class="fa-solid fa-chevron-right"></i>
                    </button>
                </div>
            `;
        }
    }

    function ouvrirPageTest() {
        document.getElementById('page-inscription').classList.add('hidden');
        document.getElementById('page-admis').classList.remove('hidden');
        
        let labelClasse = document.getElementById('classe-souhaitee').options[document.getElementById('classe-souhaitee').selectedIndex].text;
        
        document.getElementById('infos-test-eleve').innerHTML = `
            <p style="margin-bottom: 5px;">Élève : <strong style="color: var(--primary);">${eleveActuel.nom} ${eleveActuel.prenom}</strong></p>
            <p>Orientation : <strong>${labelClasse}</strong></p>
        `;
    }

    function validerTestAdmission() {
        const noteTest = parseFloat(document.getElementById('pourcentage-test').value);
        const resTest = document.getElementById('resultat-test');
        
        if (isNaN(noteTest) || noteTest < 0 || noteTest > 100) {
            alert("Veuillez entrer une note valide entre 0 et 100.");
            return;
        }

        resTest.classList.remove('hidden');

        // Test validé (>= 50%)
        if (noteTest >= 50) {
            resTest.innerHTML = `
                <div class="notification success">
                    <i class="fa-solid fa-party-horn"></i>
                    <div>
                        <strong>Félicitations !</strong> Votre enfant <strong>${eleveActuel.nom} ${eleveActuel.prenom}</strong> a réussi le test d'admission et est officiellement <strong>admis</strong> au COLLÈGE 5G. Bienvenue !
                    </div>
                </div>
            `;
        } 
        // Échec (< 50%)
        else {
            resTest.innerHTML = `
                <div class="notification danger">
                    <i class="fa-solid fa-circle-xmark"></i>
                    <div>
                        <strong>Candidature Rejetée</strong><br>
                        Nous sommes désolés, votre enfant n'a pas atteint la note seuil requise pour le test. Sa candidature a été rejetée. Fermeture de la session...
                    </div>
                </div>
            `;
            setTimeout(() => {
                window.close();
                document.body.innerHTML = `
                    <div class="container fade-in" style="text-align:center; padding: 50px;">
                        <i class="fa-solid fa-lock" style="font-size: 3rem; color: var(--danger); margin-bottom: 20px;"></i>
                        <h2>Session close</h2>
                        <p style="color: var(--text-muted); margin-top: 10px;">L'inscription n'a pas pu être validée.</p>
                    </div>`;
            }, 5000);
        }
    }
</script>

</body>
</html>
