# Publier la politique de confidentialité

`index.md` est la politique. Elle se rédige depuis `docs/COLLECTE.md` et rien d'autre ; une phrase sans ligne d'inventaire derrière elle se retire ou passe en « non vérifié ». Ce dossier se copie tel quel dans un dépôt public séparé, et l'URL obtenue va dans la fiche App Store Connect (champ « URL de la politique de confidentialité ») et dans l'app, en constante : `constants/Legal.ts` (`PRIVACY_POLICY_URL`), lue par l'écran d'achat (12/12) et par la section « À propos » des Réglages depuis p6-9 (30 août 2026). Publiée à `https://tomikz.github.io/toonboxd-legal/`. Le jour où l'adresse change, la constante et la fiche changent le même jour.

## Publication

1. Un dépôt public, `index.md` et ce fichier à sa racine.
2. Settings, Pages, source « Deploy from a branch », branche `main`, dossier `/ (root)`.
3. L'URL est `https://<compte>.github.io/<dépôt>/`. Pas de domaine personnalisé pour l'instant : `toonboxd.app` est réservé au site de la Phase 10 (`constants/Handle.ts` réserve déjà `confidentialite` et `cgu`), l'URL de la fiche se change à tout moment, et celle de l'app sera une constante.
4. Ce README est publié aussi (Jekyll rend tout `.md`), à `/README.html`. Sans conséquence.

**Le sens est toujours source vers copie, et il n'y en a qu'un.** Une correction faite directement dans le dépôt public se transcrit ici **avant** tout autre changement de la page, sinon la source ment et la recopie suivante écrase la correction. Le cas est arrivé le 3 septembre 2026 (`DECISIONS.md` §9) : les deux fichiers étaient justes séparément, et rien dans aucun des deux dépôts ne disait lequel faisait foi. Une divergence ne se voit qu'en comparant les deux, donc la comparaison est le contrôle : avant de publier, relire la page en ligne à côté d'`index.md` sur les passages que la journée a touchés.

**Cette règle ne couvre qu'un sens, et le second est arrivé le 5 septembre 2026 sur l'autre copie du produit.** La page de `web/l/` servie était **en retard d'un commit** sur sa source, un commit l'ayant modifiée après la publication : la règle ci-dessus vise la copie **plus récente**, celle-là était **plus ancienne**. La cause vaut ici mot pour mot, tout commit qui touche `legal/` après une copie la périmant sans que rien ne le signale. **La parade est une comparaison et non une discipline** : une discipline demande de la vigilance et échoue en silence quand elle manque, une comparaison ne raisonne pas sur qui a écrit en dernier, donc elle est indifférente au sens du défaut.

**L'instrument n'est pas celui de `web/`, et les confondre donnerait un faux négatif.** Là-bas la page est copiée **telle quelle**, donc l'artefact et la source sont le même fichier et un `diff` d'octets tranche. Ici `index.md` passe par kramdown : **l'artefact est du HTML, la source du Markdown**, et un `diff` d'octets rendrait « différent » sur deux fichiers parfaitement synchronisés. Le contrôle est donc un `grep` de phrases connues sur la page servie, sous témoin positif, la même forme que celle des caractères bannis plus bas.

```bash
curl -s -o /tmp/legal.html https://tomikz.github.io/toonboxd-legal/
grep -c 'Politique de confidentialit' /tmp/legal.html   # TEMOIN, doit etre non nul
grep -c '<phrase ajoutee par le dernier commit>' /tmp/legal.html
```

**Le témoin passe en premier et il n'est pas de la cérémonie** : sans lui, un `grep` qui rend zéro ne distingue pas « la copie est en retard » de « l'URL rend une 404 », et le 3 septembre ce piège exact a fait lire la page 404 de GitHub comme si c'était la nôtre. **Relevé du 5 septembre 2026** : les trois phrases de titres 4 sont présentes, sous un témoin à 5 occurrences. La copie est à jour. **Rapporté le 30 septembre 2026** : la version de Notif 2 (la section Expo) a été republiée et vérifiée en ligne ; la date, les phrases et le témoin non rapportés. La mise à jour de Notif 5 (la notification d'une suggestion acceptée, le même jour) est à republier.

## Ce qui se vérifie avant de publier

- `contact@toonboxd.app` reçoit (redirection OVH, créée le 30 août 2026).
- La région Supabase : Paris, lue au tableau de bord le 30 août 2026 (`docs/COLLECTE.md`, section 1). Fait, à ne pas relire sauf migration du projet.
- Le SQL de la suppression de compte est appliqué : sans lui, le chemin que la page décrit rend « La suppression a échoué ».
- La rangée « Ton identifiant » des Réglages est livrée (`48ed991`) : la page la cite trois fois, et `grep -o -F 'Ton identifiant' legal/index.md | wc -l` rend 3. Ce compte a rendu 1 la première fois qu'il a été joué, sur une page qui disait « dans les Réglages » sans nommer la rangée : un renvoi qui ne nomme pas ce qu'il désigne ne se contrôle pas.
- Chaque chaîne de l'app citée dans la page se retrouve par `grep` dans `locales/fr.json`, jamais dans un document qui la répète ; celles d'une notification (Notif 2, 29 septembre 2026, la section Expo) dans `supabase/functions/envoyer-notifications/chaines.ts`, leur seul domicile.

## Deux instruments, parce que le rendu peut introduire ce que la source ne contient pas

Le cadratin et le point médian sont bannis du projet (`CLAUDE.md`, *Critical Rules*), et cette page est la plus publique du projet. Le balayage habituel lit la source ; il ne voit pas ce que le moteur de rendu ajoute. Jekyll rend le Markdown avec kramdown, dont la typographie automatique convertit `---` en cadratin et `--` en demi-cadratin **dans le texte** (pas dans le code) : la source serait propre, la page publiée ne le serait pas, et aucun `grep` du dépôt ne le verrait. L'aperçu Markdown de GitHub n'est pas kramdown et ne montre pas cette conversion : il ne vaut rien comme contrôle.

**Sur la source**, avant la copie. Les deux lignes attendues sont les délimiteurs du front matter, et rien d'autre.

Le fichier de motifs `/tmp/bannis.txt` se construit par la forme des *Critical Rules* de `CLAUDE.md`, son seul domicile (`py -3`, les deux caractères en clair, le chemin converti par `cygpath -w`), jamais par un `printf` à échappements, qui a menti le 5 septembre 2026 et survivait dans ce fichier jusqu'au 29 septembre 2026 (`DECISIONS.md` §5). La recopier ici mettrait les deux caractères dans `legal/`, dont le balayage attend « rien ». Ce qui reste ici : le contrôle de ses octets et le témoin tiers, joué AVANT.

```
od -An -tx1 /tmp/bannis.txt                                          # attendu : e2 80 94 0a c2 b7 0a
grep -c -F -f /tmp/bannis.txt node_modules/react-native/README.md   # témoin tiers, AVANT : 5
grep -rn -F -f /tmp/bannis.txt legal/                               # attendu : rien
grep -n -- '--' legal/index.md                                      # attendu : exactement les lignes 1 et 3 (front matter)
```

**Sur la page publiée**, après chaque déploiement (Pages met jusqu'à une minute). Le contrôle cherche le caractère et ses formes d'entité, parce que kramdown peut émettre l'un ou l'autre selon `entity_output` :

```
URL='https://<compte>.github.io/<dépôt>/'
grep -c -F -f /tmp/bannis.txt node_modules/react-native/README.md               # témoin tiers : 5
printf '&mdash;\n' | grep -c -i -E '&mdash;|&#8212;|&#x2014;|&middot;|&#183;|&#xb7;'   # témoin forcé : 1
curl -sL "$URL" | grep -c -F 'Toonboxd'                                          # la page est bien celle-là : > 0
curl -sL "$URL" | grep -c -F '«'                                                # un caractère UTF-8 connu, en clair : > 0
curl -sL "$URL" | grep -n -F -f /tmp/bannis.txt                                  # attendu : rien
curl -sL "$URL" | grep -n -i -E '&mdash;|&#8212;|&#x2014;|&middot;|&#183;|&#xb7;'  # attendu : rien
```

Les quatre premières lignes sont les contrôles de l'instrument : sans elles, un `grep` qui rend zéro parce que la page n'est pas arrivée, parce que le terminal a perdu l'UTF-8, ou parce que le motif est faux, se lit comme un succès. Un zéro ne vaut que si le témoin à côté rend un.
