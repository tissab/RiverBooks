# 03-library-projects: Mettre à jour les bibliothèques et contrats

Mettre à jour l’ensemble des bibliothèques, contrats et `ServiceDefaults` vers `net10.0`, en maintenant la structure des dépendances. Si le multi-ciblage temporaire est nécessaire pour préserver une compilation intermédiaire, il doit être limité à la transition et supprimé lors de la consolidation.

**Done when**: Tous les projets de bibliothèques et contrats ciblent finalement `net10.0`, sans référence active à `net11.0`.
