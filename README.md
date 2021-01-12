# Un gestionnaire de consentement (RGPD) en javascript.
Lorsqu'ils visitent un site web, les utilisateurs doivent être informés et donner leur consentement préalablement au dépôt ou la lecture de cookies ou autres traceurs.

## Mise en place de la Règlementation Générale pour la Protection des Données
### Comment recueillir un consentement valide ?
    Informer l’utilisateur
    Permettre à l’utilisateur de consentir par un acte positif clair
    Permettre à l’utilisateur de faire un choix par finalité
    Permettre à l’utilisateur d’exercer ses choix avec le même degré de simplicité
    Permettre à l’utilisateur de revenir sur sa décision à tout moment

## [LANCER LA DEMO](https://ricou12.github.io/Gestionnaire-de-consentement/)

##
Ajouter dans vos pages: le code HTML, le fichier CSS et le script JS ci-dessous.

    <head>
        <-- Necessite l'installation de Bootstrap. -->
        <-- https://getbootstrap.com/docs/4.5/getting-started/introduction/ -->
        ...
        <link rel="stylesheet" href="./assets/css/cookiesManager.css"> 
    </head>
    <body>
        ...
        <article class="cookiesManager__box text-white" id="cookie-root"></article>
        <script src="./assets/js/cookiesManager.js"></script>
    </body>
  


### Usages: 
Créer des **catégories** de cookies et ajouter **le(s) script(s)** dans ***le tableau const CookiesList = []*** au début du fichier cookiesManager.js.
Une page sera créée pour chaque catégorie de cookies.

EXEMPLE de catégorie

    const CookiesList = [
        // Votre configuration
        {
            categoryName: "Statistiques et audience",
            categoryTitle: "Compter nos calories, c’est important !",
            categoryDescription: "Nous souhaitons gagner en popularité ! Et pour cette raison, la plupart des sites internet mesurent leur audience en utilisant des solutions spécialisées.",
            // AJOUTER LE OU LES SCRIPTS POUR CETTE CATEORIE
            scripts: [
                {
                    // CET IDENTIFIANT DOIT ETRE UNIQUE DANS LE TABLEAU
                    id: "googleAnalytics",
                    name: "Google Analytics",
                    description: "Permet d'analyser les statistiques de consultation de notre site",
                    // LA PROPRIETE CHECKED DOIT TOUJOURS ETRE INITIALISEE A FALSE
                    checked: false,
                    script_src: "https://www.googletagmanager.com/gtag/js?id=UA-000000000-1",
                    script_config: `
                        window.dataLayer = window.dataLayer || [];
                        function gtag(){dataLayer.push(arguments);}
                        gtag('js', new Date());
                        gtag('config', 'UA-000000000-1');`,
                },
            ],
        },
    ]


**Information:**
    * La législation porte le délai de validité du consentement au dépôt des Cookies à 13 mois au maximum.
    * À l'expiration de ce délai, le consentement devra être à nouveau recueilli.
 
*Définition de la durée de vie du cookie en jours.*
    
    const cookieLifeTime = "365";
>>>>>>> 82c8c28f92d1f138aa129c0b25959e4f74a26694
