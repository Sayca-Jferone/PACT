# PACT - Production par Architecture Contractuelle et Tracée

> Tout problème. Tout domaine. Quatre phases.

```
0-Problem.md      →  Nommer le problème s'il n'est pas clair/évident
1-CheckList.md    →  Le décomposer sans ambiguïté en Checklist de référence
2-Architecture.md →  Planifier la solution (BIOPGE, schémas, ...)
3-[Livrable]      →  Construire et entretenir la solution sous sa forme concrète
```

> *Sans le nommer, on ne construit rien. On subit ce qu'on avait vaguement en tête.*

---

## Explication détaillée

### Phase 0 — Nommer le problème

**Ce n'est pas du travail. C'est un état qu'on subit.**

Tant que le problème reste dans la tête, il est invisible et non constructible.
`0-Problem.md` : 5 minutes. Le problème, la cible, le changement attendu.

- Problème évident → optionnel, passe en Phase I directement
- Problème flou, composite, ou contexte qui change → **obligatoire**

> Plus la Phase 0 est floue, plus tout ce qui suit sera décalé. Ce n'est pas moral. C'est mécanique.

---

### Phase I — Décomposer ✅

**Source de vérité du système. Premier vrai travail PACT.**

Lire le problème. Lister chaque requirement. Résoudre chaque ambiguïté.
Sortie : `1-CheckList.md` — lisible en 60 secondes.

| Catégorie | Contenu |
|---|---|
| **F** Formats | Cadre, contraintes, environnement |
| **M** Mandatory | Ce qui est requis. Sans eux, le système est invalide. |
| **B** Bonus | Ce qui est optionnel. Ciblé ou ignoré, avec raison. |
| **O** Open Points | Les choix laissés au constructeur. Le silence n'est pas une liberté. |
| **A** Ambiguities | Zones grises — résolues ou assumées explicitement. |

---

### Phase II — Planifier 📐

**Le plan avant de construire. Zéro livrable produit ici.**

Chaque composant du système reçoit un contrat **BIOPGE** :

```
Boundary   Périmètre et responsabilité unique
Inputs     Ce qui entre
Outputs    Ce qui sort
Process    Les étapes de transformation
Guarantees Les invariants vérifiables
Errors     Chaque mode d'échec et son comportement
```

Un composant = un fichier, un département, un agent, un process humain.
Un bug logique trouvé ici coûte infiniment moins qu'en Phase III.

---

### Phase III — Construire 🏗️

**On traduit le contrat en système réel.**

Logiciel, entreprise, campagne, système humain — la Phase III n'a pas de date de fin.

| Type d'erreur | Action |
|---|---|
| Erreur d'exécution | On corrige sur place |
| Erreur logique | Retour Phase II → amender → revalider → revenir |

---

### Rétroactivité

```
Phase 0  ←── contexte changé, problème flou
Phase I  ←── ambiguïté ou pivot
Phase II ←── erreur logique
Phase III ── erreur d'exécution : corrige ici
```

Remonter n'est pas un échec. C'est le protocole qui filtre au stade le moins coûteux.

---

*Authored by Sayca J. Ferone · saycalabs.com*
*Sous-branche spécialisée : [PACT Software Engineering](../software-engineering/)*
