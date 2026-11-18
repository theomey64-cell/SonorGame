# SONOR — Jeu musical multijoueur

## Démarrer
1. Installer Node.js 18 ou plus récent.
2. Ouvrir un terminal dans ce dossier.
3. Lancer `npm install` puis `npm start`.
4. Ouvrir http://localhost:3000.

## Jouer en ligne
Héberger ce projet sur un service Node.js prenant en charge les WebSockets (Render, Railway, VPS, etc.). Le serveur utilise automatiquement la variable d'environnement `PORT`. Partager ensuite l'URL publique et le code du salon.

## Règles
- Un joueur crée le salon, les autres le rejoignent avec le code.
- Le premier chef écrit la situation.
- Les autres ont 120 secondes pour envoyer un lien YouTube (le délai se termine plus tôt si tout le monde a répondu).
- Une phase d'écoute dure au moins 20 secondes, puis 25 secondes par proposition.
- Le vote dure 45 secondes maximum. Chaque joueur peut voter une fois, sauf pour sa propre musique.
- Le gagnant gagne 1 point et devient chef à la manche suivante.

## Limites de cette première version
- Les salons sont en mémoire et disparaissent au redémarrage.
- Il n'y a pas de comptes permanents, de base de données ni de reconnexion automatique.
- YouTube peut bloquer l'intégration de certaines vidéos ou la lecture automatique ; chaque joueur peut devoir lancer lui-même la vidéo. Les extraits démarrent à 30 secondes quand la vidéo le permet, mais ne sont pas coupés automatiquement à une durée fixe.
- Le passage à la manche suivante est contrôlé par l'hôte. Le système est une première version jouable, pas un service de production sécurisé.
