# .NET Version Upgrade

## Preferences
- **Flow Mode**: Automatic
- **Target Framework**: net10.0
- **Scope**: src/RiverBooks.slnx
- **Functional behavior**: Do not modify
- **Existing local changes**: Preserve the pre-existing modification in src/RiverBooks.Web/RiverBooks.Web.csproj

## Source Control
- **Source Branch**: main
- **Working Branch**: main
- **Pending Changes**: Preserve; no automatic commit or discard
- **Commit Strategy**: Manual
- **Branch Sync**: Disabled

## Upgrade Options
- **Upgrade Strategy**: Top-Down — la solution comporte 16 projets ; cette approche limite la durée pendant laquelle la solution est partiellement migrée.

## Strategy
**Selected**: Top-Down (Application-First)
**Rationale**: La solution comporte 16 projets et doit rester cohérente pendant le passage de .NET 11 à .NET 10.

### Execution Constraints
- Vérifier le SDK .NET 10 et la compatibilité de global.json avant toute modification.
- Mettre à jour les applications et leurs dépendances sans modifier le comportement fonctionnel.
- Utiliser temporairement le multi-ciblage uniquement si nécessaire pour maintenir la compilation pendant la transition.
- Consolider ensuite tous les projets sur net10.0 et supprimer toute référence résiduelle à net11.0.
- Restaurer, compiler et exécuter les tests après la consolidation finale.
