---
Appliquer sur : '**/*.php'
---
# Architecture Propre
Lors de l'implémentation de services backend, suivez ces principes d'Architecture Propre pour assurer la maintenabilité, la scalabilité et la séparation des préoccupations.

## 1. Structure de la Solution
- La solution **doit** être organisée en trois couches principales :
  - `src/Domain` (logique métier principale, entités, objets de valeur, événements de domaine)
  - `src/Application` (cas d'utilisation, commandes, requêtes, interfaces pour les services externes)
  - `src/Infrastructure` (implémentations pour les services externes, accès à la base de données, intégrations tierces)
- Les tests doivent être dans une couche séparée

## 2. Dépendances Entre les Couches
- **Domain** : n'a aucune dépendance.
- **Application** : dépend uniquement de **Domain**.
- **Infrastructure** : dépend de **Application** et **Domain**.

## 3. Structure des Dossiers et Fichiers
- Utilisez une structure de dossiers **orientée fonctionnalité** (orientée domaine) dans chaque couche (par exemple, `Subscription/`, `Supplier/`).
- Ne **pas** utiliser de dossiers racines techniques (Entités, Objets de Valeur, Services, etc.).

## 4. Style de Codage et Conventions
- Organisez les fichiers par fonctionnalité/domaine.

## 5. Lignes Directrices pour l'Implémentation
- **Couche Domain** : Toute la logique métier, les entités, les objets de valeur et les événements de domaine. Aucune dépendance aux autres couches.
- **Couche Application** : Cas d'utilisation, commandes, requêtes, interfaces pour les dépôts/services. Aucune logique métier.
- **Couche Infrastructure** : Implémentations pour les interfaces, accès à la base de données, intégrations externes. Aucune logique métier.
- Utilisez l'injection de dépendances pour toutes les dépendances inter-couches.
- Évitez les dépendances circulaires.

# References
- [Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
