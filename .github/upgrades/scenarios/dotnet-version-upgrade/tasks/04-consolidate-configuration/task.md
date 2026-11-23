# 04-consolidate-configuration: Consolider la configuration SDK, CI/CD et documentation

Aligner `global.json`, `Directory.Build.*`, les workflows CI/CD, les scripts et la documentation qui déclarent ou sélectionnent le SDK/framework. Ne modifier que les versions .NET nécessaires et ne changer aucun comportement fonctionnel ou de déploiement au-delà de la cible SDK/framework.

**Done when**: Les configurations pertinentes sélectionnent .NET 10 de façon cohérente et les recherches ciblées ne trouvent plus de référence active à .NET 11.
