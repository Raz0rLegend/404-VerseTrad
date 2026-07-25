# 404Trad — Traduction française de Star Citizen par Raz0rLegend et la [404]

Traduction communautaire du fichier `global.ini` (localisation anglais → français) de Star Citizen, maintenue par **[404]Raz0rLegend**, en collaboration avec **MrKraken** (pack de chaînes QoL).

## 📁 Structure du dépôt

```
Trad-Ang/     → Copie de référence du global.ini anglais (source CIG + MrKraken)
Trad-France/  → Fichier global.ini traduit en français
```

Le fichier `USER.cfg` (`g_language = english`) sert de config de test pour comparer le rendu en jeu.

## 🎯 Objectif

Fournir une traduction française complète, cohérente et à jour du fichier de localisation du jeu, patch après patch, en respectant au maximum le ton, l'univers et les conventions déjà établies par CIG — tout en gardant une cohérence interne stricte entre les milliers de clés du fichier.

## 🔄 Workflow de mise à jour à chaque patch

1. **Récupération du diff** : à chaque nouveau patch (ex: 4.8 → 4.9), un diff Git (`modif.txt`) est généré entre l'ancien et le nouveau `global.ini` anglais.
2. **Catégorisation des clés** :
   - Clés **nouvelles** (n'existaient pas avant)
   - Clés **modifiées** (texte changé, même nom de clé)
   - Clés **renommées** (suffixe `,P` ajouté/retiré — fréquent quand CIG finalise un objet en placeholder)
   - Clés **supprimées** (retirées du jeu, à nettoyer du fichier FR)
3. **Traduction** en respectant le glossaire et les conventions ci-dessous.
4. **Génération d'une session** (fichier JSON) chargeable dans l'outil `comparateur_6.html` via le bouton **"📂 Reprendre"**, pour appliquer les traductions et suivre l'avancement.
5. **Mise à jour du compendium** (`Journal_General_Mining_Compendium_Content`) si de nouveaux blueprints (BP) apparaissent dans les pools de récompenses de mission.

Pour les patchs volumineux (centaines de clés), le travail est découpé en **passes thématiques** (ex : objets/armures, missions d'une faction, divers) afin de garder une qualité de traduction constante plutôt que de tout traiter d'un bloc.

## 🛠️ Outil : comparateur_6.html

Outil de traduction interne codé sur mesure :
- Compare les clés EN/FR côte à côte
- Permet de sauvegarder et reprendre une session de traduction via import/export JSON (`📂 Reprendre`)
- Facilite le suivi des clés traitées / restantes sur un gros patch

## 📖 Conventions de traduction établies

### Format général
- Encodage **UTF-8 avec BOM**, fins de ligne **CRLF**
- **Aucun accent** (contrainte moteur de jeu)
- **Espace** comme séparateur de milliers (`1 500`, pas `1,500` ni `1500`)
- **Espace avant les deux-points** français (`Fabricant :`, pas `Fabricant:`)

### Objets & équipement
- `undersuit` → **sous-vêtement**
- Descripteurs de position d'armure **déplacés devant** le nom : `Bras`, `Jambes`, `Casque`, `Torse`, `Sac a dos` (ex: *"BUL-H4 Armor Arms Stronghold"* → *"Bras BUL-H4 Stronghold"*)
- **Noms commerciaux d'armes et d'objets gardés en anglais** (ex: CQ7, Vendetta, Kiba, Snapper, Deathroll…)
- Blocs de stats d'armure : `Type d'article :`, `Reduction des degats :`, `Temperature de fonctionnement :`, `Protection contre les radiations :`, `Neutralisation des radiations :`, `Capacite de charge :`, `Tolerance aux forces G :`
- `rpm` → **`cpm`** (coups par minute)
- `CrimeStat` : **jamais traduit**, terme de jeu conservé tel quel
- Peintures de vaisseau (clés `item_NameXXX_Paint_XXX`) au format unique : `Paint "Nom" du/de l'/de la [Vaisseau]` (nom entre guillemets, article correct selon le vaisseau)
- Terme **"répéteur"** (pas "répétiteur") pour les armes de type *repeater*

### Factions
- `CrimeStat`, `Moraine`, `United Resource Workers`, noms de gangs/organisations (`Foxwell Enforcement`, `Red Wind`, `United Wayfarers Club`…) : **gardés en anglais**
- `Citizens for Prosperity` → **Citoyens pour la Prosperite**
- `Governing Committee` (People's Alliance) → **Comite Directeur**
- Bannière People's Alliance : `*********** People's Alliance ***********` / tagline `'Stronger When United'` conservée en anglais
- Rangs Battaglia : `Prospective Associate` → Associe potentiel · `Associate` → Associe · `Trusted Associate` → Associe de confiance
- Clés `Foxwell_X2_*` / `Foxwell_X2_*` (XenoThreat) : **jamais touchées** lors des synchros/audits

### Cas particuliers
- `Journal_General_Mining_Compendium_Content` : compendium des BP par faction, maintenu à jour à chaque patch introduisant de nouveaux objets dans les pools de récompenses. Format `\n` pour un collage direct dans le jeu.
- Voix de Wikelo : rendue en français simplifié/cassé pour coller au personnage
- `Frontend_PU_Version,P` : ligne de crédit personnalisée, mise à jour à chaque version (`[404]Raz0r` / `[404]Raz0rLegend` selon les patchs)

## 🙏 Crédits

- **[404]Raz0rLegend** — traduction, maintenance du dépôt
- **MrKraken** — pack de chaînes QoL ([mrkraken.space/starstrings](https://mrkraken.space/starstrings))

## 📌 Notes pour contributeurs

- Toujours vérifier une clé existante avant de la retraduire — beaucoup de gabarits (blocs de stats, bannières de faction, éditions cosmétiques) sont réutilisés tels quels ailleurs dans le fichier ; les reprendre garantit la cohérence.
- En cas de renommage de clé côté EN (ajout/retrait de `,P`), bien supprimer l'ancienne clé en plus d'ajouter la nouvelle — un simple remplacement de valeur ne suffit pas.
- Toujours croiser les nouveaux objets de type Blueprint avec le compendium pour voir s'il faut l'enrichir.
