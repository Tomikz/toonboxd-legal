# Publier la politique de confidentialité

`index.md` est la politique. Elle se rédige depuis `docs/COLLECTE.md` et rien d'autre ; une phrase sans ligne d'inventaire derrière elle se retire ou passe en « non vérifié ». Ce dossier se copie tel quel dans un dépôt public séparé, et l'URL obtenue va dans la fiche App Store Connect (champ « URL de la politique de confidentialité ») puis, dans son propre commit, sur l'écran d'achat de l'app.

## Publication

1. Un dépôt public, `index.md` et ce fichier à sa racine.
2. Settings, Pages, source « Deploy from a branch », branche `main`, dossier `/ (root)`.
3. L'URL est `https://<compte>.github.io/<dépôt>/`. Pas de domaine personnalisé pour l'instant : `toonboxd.app` est réservé au site de la Phase 10 (`constants/Handle.ts` réserve déjà `confidentialite` et `cgu`), l'URL de la fiche se change à tout moment, et celle de l'app sera une constante.
4. Ce README est publié aussi (Jekyll rend tout `.md`), à `/README.html`. Sans conséquence.

## Ce qui se vérifie avant de publier

- `contact@toonboxd.app` reçoit (redirection OVH, créée le 30 août 2026).
- La région Supabase : Paris, lue au tableau de bord le 30 août 2026 (`docs/COLLECTE.md`, section 1). Fait, à ne pas relire sauf migration du projet.
- Le SQL de la suppression de compte est appliqué : sans lui, le chemin que la page décrit rend « La suppression a échoué ».
- La rangée « Ton identifiant » des Réglages est livrée (`48ed991`) : la page la cite trois fois, et `grep -o -F 'Ton identifiant' legal/index.md | wc -l` rend 3. Ce compte a rendu 1 la première fois qu'il a été joué, sur une page qui disait « dans les Réglages » sans nommer la rangée : un renvoi qui ne nomme pas ce qu'il désigne ne se contrôle pas.
- Chaque chaîne de l'app citée dans la page se retrouve par `grep` dans `locales/fr.json`, jamais dans un document qui la répète.

## Deux instruments, parce que le rendu peut introduire ce que la source ne contient pas

Le cadratin et le point médian sont bannis du projet (`CLAUDE.md`, *Critical Rules*), et cette page est la plus publique du projet. Le balayage habituel lit la source ; il ne voit pas ce que le moteur de rendu ajoute. Jekyll rend le Markdown avec kramdown, dont la typographie automatique convertit `---` en cadratin et `--` en demi-cadratin **dans le texte** (pas dans le code) : la source serait propre, la page publiée ne le serait pas, et aucun `grep` du dépôt ne le verrait. L'aperçu Markdown de GitHub n'est pas kramdown et ne montre pas cette conversion : il ne vaut rien comme contrôle.

**Sur la source**, avant la copie. Les deux lignes attendues sont les délimiteurs du front matter, et rien d'autre :

```
printf '\xe2\x80\x94\n\xc2\xb7\n' > /tmp/bannis.txt
grep -rn -F -f /tmp/bannis.txt legal/            # attendu : rien
grep -c -F -f /tmp/bannis.txt CLAUDE.md          # témoin positif : > 0, le fichier énonce la règle
grep -n -- '--' legal/index.md                   # attendu : exactement les lignes 1 et 3 (front matter)
```

**Sur la page publiée**, après chaque déploiement (Pages met jusqu'à une minute). Le contrôle cherche le caractère et ses formes d'entité, parce que kramdown peut émettre l'un ou l'autre selon `entity_output` :

```
URL='https://<compte>.github.io/<dépôt>/'
printf 'a\xe2\x80\x94b\n' | grep -c -F -f /tmp/bannis.txt                    # témoin forcé : 1
printf '&mdash;\n' | grep -c -i -E '&mdash;|&#8212;|&#x2014;|&middot;|&#183;|&#xb7;'   # témoin forcé : 1
curl -sL "$URL" | grep -c -F 'Toonboxd'                                          # la page est bien celle-là : > 0
curl -sL "$URL" | grep -c -F "$(printf '\xc2\xab')"                              # un caractère UTF-8 connu, « : > 0
curl -sL "$URL" | grep -n -F -f /tmp/bannis.txt                                  # attendu : rien
curl -sL "$URL" | grep -n -i -E '&mdash;|&#8212;|&#x2014;|&middot;|&#183;|&#xb7;'  # attendu : rien
```

Les quatre premières lignes sont les contrôles de l'instrument : sans elles, un `grep` qui rend zéro parce que la page n'est pas arrivée, parce que le terminal a perdu l'UTF-8, ou parce que le motif est faux, se lit comme un succès. Un zéro ne vaut que si le témoin à côté rend un.
