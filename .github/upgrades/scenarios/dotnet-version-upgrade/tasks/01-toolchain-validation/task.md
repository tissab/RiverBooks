# 01-toolchain-validation: Vérifier le SDK et les références globales

Vérifier la présence du SDK .NET 10, inspecter `global.json`, les fichiers `Directory.Build.*`, les fichiers projet, les workflows CI/CD et la documentation pertinente. Cette étape doit distinguer les références .NET 11 réellement actives des occurrences historiques ou textuelles avant toute modification.

## Résultats de recherche

- La solution `src/RiverBooks.slnx` contient 16 projets, tous au format SDK-style.
- Aucun `global.json`, `Directory.Build.targets` ou `Directory.Packages.props` n’a été trouvé ; `src/Directory.Build.props` définit actuellement `<TargetFramework>net11.0</TargetFramework>`.
- Les références de cible `net11.0` sont centralisées dans `src/Directory.Build.props` et explicites dans `src/RiverBooks.AppHost/RiverBooks.AppHost.csproj` et `src/RiverBooks.ServiceDefaults/RiverBooks.ServiceDefaults.csproj`.
- Des références de packages Microsoft/AspNetCore/EF/Extensions en version 11.0.0 existent dans plusieurs `.csproj` et devront être traitées lors des tâches projet ; elles sont distinctes de la cible `net11.0`.
- La documentation `README.md` contient une mention descriptive de .NET 11 à actualiser si elle décrit l’état courant du projet.
- `.github/workflows/build.yml` a été inspecté ; aucune référence .NET 11 n’a été retournée par la recherche ciblée.
- Le SDK .NET 10 est disponible : `10.0.404` est installé et `dotnet --version` retourne `10.0.404`.
- Une modification locale préexistante est présente dans `src/RiverBooks.Web/RiverBooks.Web.csproj` : les packages OpenAPI, EF Design et Swashbuckle y sont déjà passés de la ligne 11 à la ligne 10. Elle doit être conservée telle quelle.

**Done when**: Les fichiers pertinents et les contraintes du SDK .NET 10 sont identifiés, le SDK est disponible ou le blocage est documenté, et la modification locale préexistante est préservée.
