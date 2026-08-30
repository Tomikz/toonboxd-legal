---
title: Politique de confidentialité de Toonboxd
---

# Politique de confidentialité de Toonboxd

Dernière mise à jour : 30 août 2026.

Toonboxd est une application iPhone pour suivre ta lecture de manhwas, manhuas et webtoons. Cette page dit ce que l'app sait de toi, où ça va, et ce que tu peux en faire.

## Qui en répond

Paul Maxime Nadin, entrepreneur individuel (SIREN 991987819), France. C'est le responsable du traitement au sens du RGPD. Il n'y a pas de délégué à la protection des données : la taille de l'activité ne l'impose pas.

Pour toute question ou demande sur tes données : contact@toonboxd.app.

## En une phrase

Toonboxd n'affiche pas de publicité, ne pratique aucun suivi publicitaire, et ne vend ni ne loue rien de ce qu'il sait de toi. Ce qu'il collecte sert à faire marcher l'app et à comprendre comment elle est utilisée. Le détail suit.

## Ce que Toonboxd garde sur toi

**Un compte, créé sans rien te demander.** Au premier lancement, l'app crée un compte anonyme avec un identifiant technique, une suite de lettres et de chiffres. Pas d'email, pas de nom, pas de mot de passe. Toute l'app fonctionne avec ce compte.

**Si tu lies ton compte à Apple.** Tu peux lier ce compte à ton identifiant Apple pour retrouver ta bibliothèque sur un autre iPhone. Apple nous transmet alors une adresse email : la tienne, ou une adresse relais si tu as choisi de la masquer. Nous ne demandons jamais ton nom. Cette adresse sert à te reconnaître et n'est affichée nulle part dans l'app.

**Ta bibliothèque.** Les séries que tu suis, leur statut (en cours, en pause, prévue, terminée, abandonnée), le dernier chapitre lu, les dates d'ajout et de dernière modification, les séries que tu épingles, et la note que tu donnes à une série.

**Tes mémos de reprise.** Le texte que tu écris quand tu mets une série en pause. Il est privé : personne d'autre que toi ne le voit, et il ne quitte pas notre base.

**Ton pseudo.** Celui que tu choisis sur ton profil, si tu en choisis un. Aujourd'hui, personne d'autre ne le voit. Il est conçu pour devenir public le jour où les profils s'ouvriront ; cette page sera mise à jour à ce moment.

**Tes suggestions de titres.** Le titre que tu proposes, et le lien ou la note que tu ajoutes éventuellement.

**Tes signalements.** Quand tu signales qu'une série en pause a repris : la série et la date, rien d'autre.

**Ce que ta note devient.** Ta note sur une série entre dans une moyenne communautaire anonyme. Si tu retires ta note ou si tu supprimes ton compte, elle en est retirée.

**Combien de temps.** Tant que ton compte existe. Rien n'est effacé automatiquement : c'est toi qui décides, avec le bouton décrit plus bas. Une exception connue : si tu utilises « Retrouver ma bibliothèque » pour reprendre un compte lié à Apple, le compte anonyme que tu quittes reste en base, avec ce qu'il contenait et sans rien qui permette de te reconnaître. Une purge automatique de ces comptes est prévue.

**Où trouver ton identifiant.** Dans l'app : Réglages, section Compte, « Ton identifiant ». C'est ce que nous te demanderons pour toute demande sur tes données.

**Ce que Toonboxd ne stocke pas.** Ta position, tes contacts, tes photos, ton nom, tes moyens de paiement. L'app ne demande aucune de ces autorisations à ton iPhone.

## Ce qui reste sur ton téléphone

Sur l'appareil, l'app garde ta session, tes réponses aux premiers écrans (nombre de séries, sélection, chapitres), ta préférence de tri, un cache des couvertures, et une file d'attente des événements d'usage avant leur envoi. Tout part avec la désinstallation.

## Les services que Toonboxd utilise

Six services reçoivent des données depuis ton téléphone. Pour chacun : à quoi il sert, ce qu'il reçoit, où c'est hébergé.

### Supabase : la base de données et les comptes

- Rôle : héberge tout ce que la section précédente décrit, et gère ton compte.
- Reçoit : tout ce que la section précédente décrit. Quand tu cherches une série, le texte tapé lui est envoyé pour lancer la recherche, sans être gardé.
- Hébergement : Paris, France.

### PostHog : l'analyse d'usage

- Rôle : nous dire comment l'app est utilisée (quels écrans, quelles actions), pour l'améliorer.
- Reçoit : tes actions dans l'app (ajout ou retrait d'une série, changement de statut ou de chapitre, écran ouvert, achat), avec l'identifiant de la série concernée ; **le texte de ta recherche quand elle ne donne aucun résultat** ; la version de l'app, la langue et le fuseau horaire de ton téléphone, la taille de l'écran, le type d'appareil ; le fait que tu es abonné ou non. Le tout est rangé sous ton identifiant de compte. Il ne reçoit jamais tes mémos, ton pseudo ni tes suggestions.
- Hébergement : Union européenne.
- Adresse IP : comme tout serveur, PostHog reçoit l'adresse IP de ton téléphone à chaque envoi. Ce qu'il en garde dépend d'un réglage que nous n'avons pas encore vérifié.

### Firebase Analytics (Google) : la même analyse, seconde destination

- Rôle : le même usage que PostHog, chez Google.
- Reçoit : les mêmes actions, rangées sous ton identifiant de compte et sous un identifiant d'installation généré par Google. Tes achats y arrivent aussi par RevenueCat (voir plus bas). Ce que le composant Google collecte de lui-même sur ton appareil (modèle, système, pays déduit) n'a pas pu être vérifié de notre côté.
- Hébergement : non vérifié à ce jour, possiblement hors Union européenne.

### Sentry : les rapports de plantage

- Rôle : nous dire quand l'app plante, et pourquoi.
- Reçoit : l'erreur et l'endroit de l'app où elle s'est produite, le modèle d'appareil et la version du système, et ton adresse IP, qu'il stocke avec le rapport. Aucun identifiant de compte : rien chez Sentry ne te désigne.
- Hébergement : Union européenne.

### RevenueCat : l'abonnement

- Rôle : gère l'abonnement Pro, l'essai gratuit et la restauration des achats.
- Reçoit : le reçu d'achat transmis par Apple, la formule choisie, un identifiant d'installation anonyme qu'il génère lui-même, et l'identifiant d'installation Firebase. Il ne reçoit pas ton identifiant de compte aujourd'hui. Le jour où ce lien existera, pour que ton abonnement te suive d'un iPhone à l'autre, cette page le dira.
- Hébergement : non vérifié à ce jour.

### Apple : la connexion et le paiement

Connexion avec Apple et l'achat passent par Apple. Ce qu'Apple fait de ces opérations relève de sa propre politique. Ce qui nous revient : un jeton d'identité quand tu lies ton compte, et un reçu quand tu achètes.

### Deux choses sans service

- Les couvertures des séries sont chargées depuis AniList (s4.anilist.co). Comme pour toute image sur le web, ce serveur reçoit l'adresse IP de ton téléphone et l'adresse de l'image.
- « Lire sur … » et « Chercher le chapitre N » ouvrent un navigateur dans l'app, vers la plateforme officielle ou vers une recherche Google. Ce qui se passe sur ces pages relève de ces sites, pas de Toonboxd.

## Le suivi publicitaire

Il n'y en a pas. L'app ne contient aucun outil d'attribution publicitaire, ne lit pas l'identifiant publicitaire de ton iPhone, et ne te demande donc jamais l'autorisation de suivi d'Apple. Ce n'est pas un réglage : ces outils sont absents de l'app.

Si un jour nous faisons de la publicité pour Toonboxd et voulons mesurer d'où viennent les installations, l'app te demandera l'autorisation d'Apple avant toute chose, et cette page changera.

## Supprimer ton compte

**Où.** Dans l'app : Réglages, section Compte, « Supprimer mon compte ». Un écran dit ce qui part et ce qui reste, puis l'app demande « Supprimer ton compte ? ».

**Ce qui part, tout de suite et pour de bon.** Tout ce que Toonboxd stocke sur toi : ton compte, ta bibliothèque, tes notes, tes mémos, ton pseudo, tes signalements, et l'adresse Apple si tu avais lié ton compte.

**Ce qui reste.**

- Tes suggestions de titres, sans plus rien qui les relie à toi : elles servent le catalogue.
- Ton abonnement, s'il existe. Il se gère dans les réglages Apple, et la suppression ne le résilie pas.
- La liaison à ton identifiant Apple, côté Apple. Tu la retires toi-même dans les réglages iOS, sous ton nom, puis Connexion avec Apple.

**Ce que la suppression ne fait pas.** Elle n'efface pas ce qui a déjà été envoyé aux services d'analyse. PostHog et Firebase gardent les événements reçus, rangés sous ton identifiant. Pour les effacer :

1. Note ton identifiant. L'app l'affiche dans les Réglages (« Ton identifiant »), et l'écran qui confirme la suppression l'affiche une dernière fois.
2. Envoie-le à contact@toonboxd.app en demandant l'effacement.
3. Nous demandons l'effacement à PostHog et à Firebase dans le mois qui suit. Chaque service traite ensuite la demande à son rythme, que nous ne contrôlons pas.

Sentry n'a rien qui te désigne, donc rien à effacer par personne. RevenueCat ne peut pas être relié à ton compte aujourd'hui, donc rien ne peut y être effacé à ton nom ; ton abonnement reste de toute façon chez Apple.

## Tes droits

Le RGPD te donne des droits sur tes données. Voici ce que chacun veut dire ici.

- Accès : savoir ce que nous avons sur toi. Ta bibliothèque, tes notes et tes mémos sont dans l'app ; pour le reste, écris-nous.
- Rectification : ton pseudo, ta bibliothèque, tes notes et tes mémos se modifient dans l'app.
- Effacement : le bouton « Supprimer mon compte », puis la demande décrite ci-dessus pour l'analyse d'usage.
- Portabilité : l'app n'a pas de fonction d'export. Sur demande, nous t'envoyons une copie de tes données dans un format lisible.
- Opposition et limitation : pour l'analyse d'usage, sur demande. Il n'existe pas de réglage dans l'app pour la désactiver.
- Réclamation : auprès de la CNIL (cnil.fr), si tu estimes que tes droits ne sont pas respectés.

Pour exercer un droit : un mail à contact@toonboxd.app avec ton identifiant (Réglages, section Compte, « Ton identifiant »). Sans lui, nous ne pouvons pas te retrouver : un compte anonyme n'a rien d'autre. Nous répondons dans le mois.

**Sur quelle base.** Le compte, la bibliothèque et l'abonnement sont nécessaires au service que tu utilises. L'analyse d'usage et les rapports de plantage relèvent de notre intérêt légitime à comprendre et à réparer l'app.

**Hors de l'Union européenne.** Google et RevenueCat peuvent héberger leurs données hors de l'UE ; nous n'avons pas encore vérifié où. Cette page sera précisée quand ce sera fait.

## Si cette page change

La date en tête change, et la liste ci-dessous dit ce qui a changé. L'historique complet de cette page est public dans le dépôt qui l'héberge : chaque version reste lisible.

- 30 août 2026 : première version.

## Ce que cette page ne couvre pas

Les conditions de l'abonnement Pro, qui relèvent du contrat de licence standard d'Apple.
