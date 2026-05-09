# Produire grâce à l'Architecture Contractuelle Traçable

#### README version lecture rapide

> Info: [PACT spécifique au développement informatique](https://github.com/Sayca-jferone/PACT_SoftwareEngineering)

Tout problème non nommé reste un fantasme.
Tout système non architecturé avant d'être construit accumule une dette invisible, payée en temps, en énergie, en désynchronisation croissante entre ce qu'on voulait et ce qu'on a produit.

PACT s'applique à n'importe quel domaine.

| Phase | Document | Nature | Domaine | Utilité |
|---|---|---|---|---|
| **0** | `0-Problem.md` | Problème clair pour une solution claire | Mental / Volatile | Ecrire le problème clairement. Optionnel si c'est évident. |
| **I** | `1-CheckList.md` | Checklist complète/solide à cocher | Ecrit / Permanent | Problème corrigé. Ce qu'il doit être fait. Comportements listés. Ambiguïtés résolues. |
| **II** | `2-Architecture.md` | Plan du système-solution | Formel / Logique | Corriger la logique avant de corriger un produit défaillant. |
| **III** | Produire le plan. | Construction & entretien du système fonctionnel | Concret / Retours | Traduire l'architecture logique en système réel et fonctionnel. |

---

## 1️⃣ | QUI devrait utiliser PACT ?

| | |
|---|---|
| **Tout créateur de système** | Tu construis quelque chose — un produit, une entreprise, un outil, un process. Tu veux que ce que tu produis corresponde au problème que tu voulais résoudre. |
| **Équipes & collaborateurs** | Un référentiel partagé élimine les désaccords d'interprétation. Chaque décision est tracée, chaque phase est un contrat lisible par tous. |
| **Agents IA & systèmes de traitement** | PACT est lisible par tout système capable d'interpréter du markdown structuré. Les phases sont des contrats formels, pas des notes informelles. |
| **Individus à forte charge cognitive** | Externaliser le problème avant de le résoudre réduit l'entropie mentale. PACT est une prothèse de clarté, pas un fardeau supplémentaire. |

---

## 2️⃣ | QUAND utiliser PACT ?

```txt
0. Le problème est-il clairement nommé ?
   └─ Non → Phase 0 obligatoire (0-Problem.md)
   └─ Oui, évident → Phase I directement

1. La solution demande-t-elle une préparation structurée ?
   └─ Non (micro-problème) → Phase I suffit, Phase III directement
   └─ Oui → Phase II requise

2. Le système est-il complexe ou irréversible ?
   └─ Faible complexité  → allège les phases, garde la traçabilité
   └─ Forte complexité   → toutes les phases, aucun raccourci
   └─ Forte irréversibilité → Phase 0 et Phase I obligatoires, même si "évident"

3. Le problème ou le contexte a changé ?
   └─ Retour en Phase 0 → mise à jour → propagation en cascade I → II → III
```

---

## 3️⃣ | QU'EST-CE QUE PACT ?

### Un fiabilisateur de production : plus de temps en logique pour ne pas subir en physique

Pas d'over-engineering : un problème simple demande quelques minutes de Phases 0 et I. Un système complexe — des jours, des semaines, des mois.

**Pourquoi ?** Le coût réel n'est pas le temps de construction. C'est le temps perdu à construire sur un problème mal compris, à déconstruire sans référentiel, à repartir de zéro après avoir découvert l'incohérence dans le béton.

1. **Réduire le coût total** — fatigue, temps, ressources dépensées sur la mauvaise fondation.
2. **Renforcer la cohérence** — chaque bug, chaque désalignement remonte en entonnoir `I ← II ← III`.
3. **Produire un référentiel lisible** — pour les changements, les pivots, les nouveaux membres, les agents IA.

Le livrable devient la traduction d'un contrat existant. Pas une exploration à l'aveugle.

---

# Partie détaillée

## Phase 0 — Reconnaissance 🔍

**Si vous savez déjà quel est le problème, arrêtez d'y penser et écrivez le. Ensuite, Phase I.**

Une frustration, une observation, une idée, un besoin. Quelque chose qui ne fonctionne pas, qui manque, qui pourrait exister. Tant que cet état reste dans la tête — il est invisible, instable, non partageable. Il ne peut pas être construit.

> *Sans le nommer, on ne construit rien. On subit ce qu'on avait vaguement en tête.*

**Ce que la Phase 0 produit : `0-Problem.md`**

Un document court. Pas une spécification. Pas une architecture. Juste le problème nommé, la cible identifiée, le changement attendu. Cinq minutes suffisent. C'est le point d'entrée de tout ce qui suit.

**Quand est-elle obligatoire ?**

- Le problème est flou, composite, ou difficile à formuler en une phrase → **obligatoire**
- Le contexte vient de changer (pivot, nouveau marché, nouvelle contrainte) → **mise à jour obligatoire**
- Le problème est micro, évident, tient en deux lignes → **optionnelle**, passe en Phase I directement

**La règle mécanique :**

> Plus la Phase 0 est floue, plus tout ce qui suit sera décalé. Chaque heure investie en Phase I, II, III sur un problème mal défini est une heure dépensée sur la mauvaise fondation. Ce n'est pas une règle morale. C'est de la mécanique.

**Exemples :**

| Domaine | Phase 0 floue | Phase 0 nommée |
|---|---|---|
| **Business** | "Je veux créer une appli pour les restaurants" | "Les gérants de petits restaurants perdent 2h/jour à gérer les réservations manuellement. Je veux réduire ce temps à 10 minutes." |
| **Logiciel** | "Faut que ça gère les erreurs" | "Le service crash silencieusement sur timeout réseau. Il faut détecter, logger, et retry avec backoff exponentiel." |

---

## Phase I — CheckList 📝

**Premier vrai travail PACT. Source de vérité du système.**

Lire le problème, le décomposer entièrement, corriger la perception. Chaque requirement devient une case à cocher. Chaque ambiguïté est résolue ou assumée explicitement. Aucune question ouverte ne peut survivre si elle peut invalider la Phase II.

Décomposer en 5 catégories **(F.M.B.O.A)** :

- **Formats (F-XX)** : cadre du système — contraintes, normes, livrables, environnement.
- **Mandatory (M-XX)** : ce qui est explicitement requis. Système invalide sans eux.
- **Bonus (B-XX)** : ce qui est optionnel. Ciblé ou ignoré, avec raison.
- **Open Points (O-XX)** : les choix laissés au constructeur. Le silence n'est pas une liberté — c'est une décision non tracée.
- **Ambiguities (A-XX)** : zones grises résolues par Q&A ou assumées explicitement (`[ASSUMED]`).

Sortie : `1-CheckList.md`. Dense, lisible en 60 secondes. Zéro prose. Zéro architecture.

**Exemples :**

| Domaine | Ambiguïté Phase I | Résolution |
|---|---|---|
| **Business** | "Cible : PME" → quelle taille ? quel secteur ? | `[ASSUMED]` : PME 5-50 employés, secteur restauration, France métropolitaine |
| **Logiciel** | "Gérer les erreurs" → lesquelles ? quel comportement ? | Résolu par Q&A : timeout réseau uniquement, retry x3, log structuré JSON |

> Si le contexte change, si le client pivote, si une nouvelle contrainte apparaît : **retour en Phase I en premier**. On met à jour `1-CheckList.md`, puis on propage en Phase II, puis en Phase III.

---

## Phase II — Architecture 📐

**Le plan du système avant de le construire.**

Chaque composant du système reçoit un **bloc BIOPGE** — un contrat formel qui définit ce qu'il fait, ce qu'il reçoit, ce qu'il produit, ses garanties, ses modes d'échec.

```
Boundary  : Nom, périmètre, responsabilité unique de ce composant.
Inputs    : Ce qui entre. Typé, sans ambiguïté.
Outputs   : Ce qui sort ou les effets produits.
Process   : Les étapes de transformation, dans l'ordre.
Guarantees: Les invariants vérifiables après exécution.
Errors    : Chaque mode d'échec, son déclencheur, son comportement.
```

**BIOPGE est domain-agnostic.** Un composant peut être un fichier source, un département, un agent IA, un process humain, une API, une cellule d'organisation.

**Exemples :**

*Business — Composant : Équipe Acquisition Client*
| | |
|---|---|
| **Boundary** | Équipe Acquisition — responsable du pipeline entrant. Ne touche pas à la rétention. |
| **Inputs** | Budget mensuel alloué, ICP défini en Phase I, canaux validés |
| **Outputs** | Leads qualifiés transmis à l'équipe Closing |
| **Process** | Ciblage → Outreach → Qualification → Handoff |
| **Guarantees** | Chaque lead transmis a passé les 3 critères ICP. Aucun handoff sans scoring. |
| **Errors** | Budget épuisé avant objectif → escalade immédiate. Lead hors ICP → rejeté, pas transmis. |

*Logiciel — Composant : `retry_handler.py`*
| | |
|---|---|
| **Boundary** | `retry_handler.py` — gestion des retries réseau. Ne gère pas les erreurs métier. |
| **Inputs** | `fn: Callable`, `max_retries: int`, `backoff: float` |
| **Outputs** | Résultat de `fn` ou raise `MaxRetriesExceeded` |
| **Process** | Appel → échec réseau → attente `backoff * attempt` → retry → repeat |
| **Guarantees** | Jamais plus de `max_retries` tentatives. Backoff toujours croissant. |
| **Errors** | Erreur non-réseau → propagée immédiatement, pas de retry. |

Sortie : `2-Architecture.md`. Un bloc BIOPGE par composant. Zéro code.

**Règle : on ne construit pas tant que le bloc concerné n'est pas défini. Un bug conceptuel en Phase II coûte infiniment moins qu'un bug logique découvert en Phase III.**

---

## Phase III — Production 🏗️

**Le contrat existe. On le traduit en système réel.**

Logiciel, entreprise en marche, campagne lancée, système humain déployé — la Phase III est la construction concrète et son entretien dans la durée. Il n'y a pas de date de fin : un système produit se maintient, s'améliore, s'adapte.

Deux types d'erreurs en Phase III :

1. **Erreur d'exécution** *(syntaxe, détail d'implémentation, contrainte d'environnement)* : on corrige sur place.
2. **Erreur logique** *(flux incorrect, garantie impossible, cas oublié)* : retour en Phase II. On amende le bloc BIOPGE. On revalide. On revient.

Cette distinction est la règle critique de Phase III. La confondre, c'est accumuler une dette invisible.

Sortie : le livrable + `3-Notes.md` optionnel — journal des décisions non triviales, retroactivités, ressources. Il complète la traçabilité, il ne la remplace pas.

---

## Rétroactivité

```
Phase 0  (Problème nommé)      <------ flou détecté, contexte changé ------+
   |                                                                        |
   v                                                                        |
Phase I  (CheckList)           <------ ambiguïté ou pivot de demande ------+
   |                                                                        |
   v                                                                        |
Phase II (Architecture)        <------ erreur logique détectée ------------+
   |                                                                        |
   v                                                                        |
Phase III (Production)         ------- erreur d'exécution : corrige ici ---+
```

Retourner en arrière n'est pas un échec. C'est le protocole qui filtre une incohérence au stade le moins coûteux.

---

## Le livrable PACT

À la fin d'un projet construit sous PACT :

```
docs/
    0-Problem.md          ← le problème nommé (optionnel si micro)
    1-CheckList.md        ← source de vérité, lisible en 60 secondes
    2-Architecture.md     ← contrat de chaque composant
    3-Notes.md            ← journal optionnel de production
[livrable/]               ← le système construit
```

Ce référentiel suffit à produire un README final cohérent, à onboarder un nouveau membre ou agent, à auditer une décision prise six mois plus tôt.

---

## Racines et convergences

PACT converge avec des standards établis, dont la proximité a été découverte après coup :

| Référence | Domaine | Convergence | Différence |
|---|---|---|---|
| **Design by Contract** (Meyer, 1986) | Génie logiciel formel | Bloc BIOPGE = contrat pre/post/invariant/error | DbC opère au niveau fonction ; PACT systématise au niveau composant et impose une phase conceptuelle amont |
| **arc42** (Starke & Hruschka, 2005) | Documentation d'architecture | Format markdown structuré, pragmatisme, compartiments optionnels | arc42 couvre 12 aspects ; PACT restreint au contrat de composant + traçabilité phase |
| **Wardley Mapping** (Ward, 2005) | Stratégie business & système | Reconnaissance du contexte avant toute décision (Phase 0) | Wardley cartographie la chaîne de valeur ; PACT contractualise la construction |

La convergence est réelle, elle n'est pas une imitation. PACT est un protocole de terrain né sous contrainte, pas une synthèse théorique.

---

*Protocole de terrain, pas de théorie académique. Testé sur projets réels, raffiné sous contraintes réelles. Tous retours bienvenus.*
*Authored by Sayca (Jason FERONE) - saycalabs.com*
