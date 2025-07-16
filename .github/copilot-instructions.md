# Instructions Copilot

## Politique linguistique
Toutes les instructions doivent être écrites en français. Cela s'applique à :
- Tous les fichiers de règles et d'instructions dans `.github/instructions/`

## Génération de code de développement
Lors de la manipulation de code PHP, suivez ces instructions très attentivement.
Il est **EXTRÊMEMENT important que vous suiviez les instructions dans les fichiers de règles très attentivement.**

### Implémentation du flux de travail
**IMPORTANT :** Suivez toujours ces étapes lors de l'implémentation de nouvelles fonctionnalités :
1. Consultez tous les fichiers d'instructions pertinents listés ci-dessous et commencez par lister les fichiers de règles qui ont été utilisés pour guider l'implémentation (par exemple, `Instructions utilisées : [clean-architecture.md]`).
2. Suivez le TDD lorsque cela est possible. Commencez toujours les nouvelles modifications en écrivant de nouveaux cas de test (ou en modifiant les tests existants).
    - Écrivez d'abord les tests avant de commencer l'implémentation.
