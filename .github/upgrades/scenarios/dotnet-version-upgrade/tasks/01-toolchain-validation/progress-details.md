# Validation de l’outillage et des références

- SDK .NET 10 disponible : `10.0.404` installé ; `dotnet --version` retourne `10.0.404`.
- Aucun `global.json`, `Directory.Build.targets` ou `Directory.Packages.props` détecté.
- `src/Directory.Build.props` centralise actuellement la cible `net11.0`.
- La recherche ciblée a trouvé les cibles et packages version 11 à traiter dans les projets, ainsi qu’une mention documentaire dans `README.md`.
- `.github/workflows/build.yml` ne contient pas de référence .NET 11.
- La modification locale préalable de `src/RiverBooks.Web/RiverBooks.Web.csproj` a été inspectée et reste inchangée.

Validation : étape de recherche terminée ; aucun blocage SDK.
