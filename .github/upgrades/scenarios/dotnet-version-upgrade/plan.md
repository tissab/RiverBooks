# .NET Version Upgrade Plan

## Overview

**Target**: Remplacer le SDK et les cibles .NET 11 par .NET 10 dans la solution RiverBooks.
**Scope**: 16 projets SDK-style dans `src/RiverBooks.slnx`, ainsi que les fichiers de configuration SDK, CI/CD et documentation qui référencent .NET 11.

## Upgrade Options

| Option | Selected | Why |
|--------|----------|-----|
| Upgrade Strategy | Top-Down (Application-First) | La solution comporte 16 projets ; cette approche limite la durée pendant laquelle la solution est partiellement migrée. |

## Tasks

### 01-toolchain-validation: Vérifier le SDK et les références globales

Vérifier la présence du SDK .NET 10, inspecter `global.json`, les fichiers `Directory.Build.*`, les fichiers projet, les workflows CI/CD et la documentation pertinente. Cette étape doit distinguer les références .NET 11 réellement actives des occurrences historiques ou textuelles avant toute modification.

**Done when**: Les fichiers pertinents et les contraintes du SDK .NET 10 sont identifiés, le SDK est disponible ou le blocage est documenté, et la modification locale préexistante est préservée.

---

### 02-application-projects: Mettre à jour les projets applicatifs et de test

Mettre à jour les projets d’entrée (`RiverBooks.Web` et `RiverBooks.AppHost`) ainsi que leurs projets de test associés vers `net10.0`, en conservant les références de projets et le comportement fonctionnel. Les packages déjà compatibles ne seront pas modifiés sauf si la restauration avec .NET 10 l’exige.

**Done when**: Les applications et tests concernés ciblent .NET 10, sans erreur de compilation introduite et sans modification fonctionnelle.

---

### 03-library-projects: Mettre à jour les bibliothèques et contrats

Mettre à jour l’ensemble des bibliothèques, contrats et `ServiceDefaults` vers `net10.0`, en maintenant la structure des dépendances. Si le multi-ciblage temporaire est nécessaire pour préserver une compilation intermédiaire, il doit être limité à la transition et supprimé lors de la consolidation.

**Done when**: Tous les projets de bibliothèques et contrats ciblent finalement `net10.0`, sans référence active à `net11.0`.

---

### 04-consolidate-configuration: Consolider la configuration SDK, CI/CD et documentation

Aligner `global.json`, `Directory.Build.*`, les workflows CI/CD, les scripts et la documentation qui déclarent ou sélectionnent le SDK/framework. Ne modifier que les versions .NET nécessaires et ne changer aucun comportement fonctionnel ou de déploiement au-delà de la cible SDK/framework.

**Done when**: Les configurations pertinentes sélectionnent .NET 10 de façon cohérente et les recherches ciblées ne trouvent plus de référence active à .NET 11.

---

### 05-final-validation: Restaurer, compiler et tester la solution

Restaurer la solution avec le SDK .NET 10 lorsqu’il est disponible, compiler tous les projets avec zéro erreur et zéro avertissement nouveau, puis exécuter la suite de tests. Vérifier également l’état Git pour confirmer que seules les modifications prévues ont été apportées et que la modification locale initiale est intacte.

**Done when**: La restauration, la compilation et les tests passent avec le SDK .NET 10, ou chaque blocage est décrit précisément avec sa commande et sa sortie utile.
