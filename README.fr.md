**[Télécharger Northstar](https://github.com/speaktoyourdatabase/northstar-odoo-demo/releases/latest/download/northstar-odoo20.zip)** | [Page des versions](https://github.com/speaktoyourdatabase/northstar-odoo-demo/releases) | [English](README.md)

Le bouton vert Code > Download ZIP ne contient pas la base de données.

## Démarrage rapide

1. Installez [Docker Desktop](https://www.docker.com/products/docker-desktop/) et lancez-le.
2. Décompressez le téléchargement dans un dossier vide, ouvrez un terminal dans ce dossier et lancez `docker compose up`. Quand il affiche `Northstar is ready`, ouvrez <http://localhost:8069> et connectez-vous avec `admin` / `admin`.

# Northstar : une entreprise fictive pour Odoo 20 Community

Northstar Office & Industrial Supply Inc. est une entreprise américaine fictive de Columbus (Ohio) : un distributeur B2B de fournitures de
bureau, d'entretien et d'industrie légère, avec environ 25 salariés. Elle se présente comme une base Odoo 20 Community prête à l'emploi, avec
12 mois d'historique, toutes les applications reliées entre elles et une comptabilité juste au centime.

**Données jusqu'au 10 novembre 2026, actualisées chaque semaine.** (Historique depuis le 10 novembre 2025. Odoo 20.0-20261102, édition Community.)

Le téléchargement est gratuit, sans inscription et sans limite de durée. Un seul zip contient une sauvegarde Odoo standard et un petit fichier
Docker qui utilise les images officielles d'Odoo et de PostgreSQL. De nouvelles journées chaque nuit sont en option, dans le même
téléchargement (plus bas).

Applications : Sales, CRM, Purchase, Inventory, Invoicing, Point of Sale, Manufacturing, Employees, Time Off, Attendances, Project, Timesheets and To-Do, reliées entre elles. Les chiffres détaillés, les identifiants et la foire aux questions sont dans le
[README en anglais](README.md).

## Lancer Northstar avec Docker (Windows, macOS, Linux)

1. Installez Docker Desktop (Windows, macOS) ou Docker Engine avec le plugin Compose (Linux). Il faut Docker Compose 2.20 ou plus récent ;
   toutes les versions actuelles de Docker Desktop l'ont.
2. [Téléchargez Northstar](https://github.com/speaktoyourdatabase/northstar-odoo-demo/releases/latest/download/northstar-odoo20.zip) (`northstar-odoo20.zip`, environ 8.7 MB) et décompressez-le dans un dossier vide.
3. Ouvrez un terminal dans ce dossier et lancez :

   ```
   docker compose up
   ```

4. Le premier démarrage prend quelques minutes, c'est normal : Docker télécharge une fois les deux images officielles, puis Northstar
   affiche `Restoring Northstar` et une ligne `Still restoring` toutes les 10 secondes (60 à 120 secondes en tout, en général).
5. Quand vous voyez `Northstar is ready`, ouvrez <http://localhost:8069> et connectez-vous avec admin / admin (les quatre commerciaux ont
   le mot de passe `northstar`). La fenêtre reste ouverte tant que Northstar tourne.

Bon à savoir :

- Les démarrages suivants gardent vos données et s'ouvrent en quelques secondes. Arrêt : `Ctrl+C` (ou `docker compose down`).
- Le port 8069 est déjà pris ? Lancez `NORTHSTAR_PORT=8079 docker compose up` (PowerShell : `$env:NORTHSTAR_PORT=8079; docker compose up`).
- Repartir des données d'origine : `docker compose down -v`, puis `docker compose up`. Cela efface tous vos changements.
- Odoo n'écoute que sur votre ordinateur (127.0.0.1), pas sur votre réseau. Rien ne se connecte à notre service tant que vous n'activez pas
  les nouvelles journées ci-dessous.

## De nouvelles journées chaque nuit (optionnel)

**De nouvelles journées chaque nuit (optionnel) : `docker compose --profile live up -d`, puis ouvrez <http://localhost:8070> et cliquez sur Associer.**

Les données s'arrêtent au 10 novembre 2026. Northstar Live garde votre copie vivante : chaque nuit, nous ajoutons la journée qui vient de
se terminer (devis, commandes, livraisons, factures, paiements, achats, le comptoir, l'atelier, les projets, les congés, les pistes), et
les journées depuis le 10 novembre 2026 sont rattrapées d'abord. C'est désactivé tant que vous ne l'activez pas, et cela utilise la même
installation : les mêmes données, rien à retélécharger sauf notre petit relais. Il faut un compte gratuit sur <https://speaktoyourdatabase.com/northstar?utm_source=github&utm_medium=readme>.

**Bientôt disponible.** Notre service Live n'est pas encore ouvert. D'ici là, la page du relais indique qu'il n'est pas connecté, et rien
d'autre ne change.

1. Dans le dossier de Northstar, lancez :

   ```
   docker compose --profile live up -d
   ```

2. Ouvrez <http://localhost:8070>. La page affiche votre code d'association en grand, sa durée de validité (15 minutes) et un grand bouton,
   **Associer à Speak To Your Database**. Cliquez dessus : notre site s'ouvre dans un nouvel onglet avec le code déjà rempli. Connectez-vous
   à votre compte gratuit et confirmez. Faites-le sur le même réseau que cet ordinateur (la même connexion internet) : une association
   depuis un autre réseau est refusée.
3. La page passe d'elle-même à **En direct**.

Pas de navigateur sur cet ordinateur ? `docker compose exec northstar-live northstar-live code` affiche le code et le lien complet : ouvrez
le lien sur un autre appareil du même réseau. Vous pouvez aussi saisir le code vous-même sur notre site (le bouton **Copier le code** aide).

Comment cela marche, ce que cela peut faire et ce que cela ne peut pas faire :

- Sans `--profile live`, rien dans ce paquet ne se connecte à notre service : le relais ne démarre pas, et son image n'est même pas téléchargée.
- Avec, un petit relais (`northstar-live`) ouvre une seule connexion chiffrée **sortante** vers notre service. Rien n'écoute sur votre
  réseau : Odoo et la page du relais sont sur 127.0.0.1 seulement.
- Votre clé d'API Odoo est créée sur votre ordinateur au démarrage de Live et **ne le quitte jamais**. Le relais l'ajoute lui-même à chaque appel.
- Le relais transmet à votre Odoo les appels de la vie quotidienne de Northstar et seulement ceux-là (environ 60 modèles Odoo, avec des
  limites de taille, de durée et de rythme). Il ne peut joindre aucune autre adresse, ni utiliser le gestionnaire de bases, ni lire ou
  modifier les utilisateurs, les mots de passe, les droits ou les clés d'API, ni installer d'application, ni exécuter de code dans Odoo, ni
  envoyer d'e-mail, ni supprimer d'enregistrement.
- Laissez-le tourner. Une nuit où l'ordinateur est éteint est rattrapée à son retour, jusqu'à 45 jours.
- Avec Live activé, ajoutez `--profile live` pour arrêter et pour repartir de zéro : `docker compose --profile live stop` arrête tout,
  `docker compose --profile live up -d` redémarre, et `docker compose --profile live down -v` repart des données d'origine (et oublie
  l'association). Le relais seul : `docker compose stop northstar-live` (Odoo continue ; les journées manquées viendront ensuite).
- Déconnecter cet ordinateur de son compte : le bouton de <http://localhost:8070> (cochez la case d'abord), ou
  `docker compose exec northstar-live northstar-live unpair`. Votre Odoo et vos changements restent. Pour l'associer à un autre compte,
  déconnectez-le d'abord.
- Mémoire : environ 450 Mo après une nuit (le relais environ 26 Mo, plafonné à 128 Mo). Dans Docker Desktop, laissez au moins 4 Go à Docker.

## Licence

Northstar est publié sous **CC0 1.0 Universal** (dédicace au domaine public, voir [LICENSE](LICENSE)) : utilisez-le, copiez-le,
modifiez-le et partagez-le pour tout usage, privé ou commercial, sans autorisation. Une mention est appréciée, pas obligatoire :

```
Demo data: Northstar by Speak To Your Database, speaktoyourdatabase.com/northstar
```

Ces mots de passe de démonstration sont publics : gardez Odoo sur votre ordinateur, comme le fait ce paquet. Plus d'informations : <https://speaktoyourdatabase.com/northstar?utm_source=github&utm_medium=readme>

**Des questions ?** Écrivez à contact@speaktoyourdatabase.com.

Speak To Your Database
