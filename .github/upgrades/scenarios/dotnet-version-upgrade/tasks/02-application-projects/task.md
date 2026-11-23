# 02-application-projects: Mettre à jour les projets applicatifs et de test

Mettre à jour les projets d’entrée (`RiverBooks.Web` et `RiverBooks.AppHost`) ainsi que leurs projets de test associés vers `net10.0`, en conservant les références de projets et le comportement fonctionnel. Les packages déjà compatibles ne seront pas modifiés sauf si la restauration avec .NET 10 l’exige.

## Recherche et portée

- `src/Directory.Build.props` fournit la cible par défaut `net11.0` à tous les projets ; son passage à `net10.0` couvre les bibliothèques et tests SDK-style qui n’ont pas de cible explicite.
- `src/RiverBooks.AppHost/RiverBooks.AppHost.csproj` redéfinit explicitement `net11.0` et doit donc être modifié directement.
- `src/RiverBooks.Web/RiverBooks.Web.csproj` n’a pas de cible explicite et hérite de `Directory.Build.props` ; sa modification locale préexistante concerne uniquement des packages déjà ramenés en version 10 et doit être conservée.
- Les projets de test `RiverBooks.Books.Tests`, `RiverBooks.OrderProcessingTests` et `RiverBooks.SharedKernel.Tests` héritent également de la cible centralisée.
- L’évaluation de `RiverBooks.AppHost` ne signale aucune incompatibilité ni incident API ; ses packages Aspire et MessagePack sont compatibles. Le package `System.Security.Cryptography.Pkcs` 11.0.0 est traité séparément comme référence de package, sans changement fonctionnel.
- L’évaluation de la solution signale zéro incident API/package et zéro recommandation de couverture supplémentaire.

**Done when**: Les applications et tests concernés ciblent .NET 10, sans erreur de compilation introduite et sans modification fonctionnelle.
