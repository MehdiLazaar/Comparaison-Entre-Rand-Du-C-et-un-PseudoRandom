# Analyse et Description du Code en C pour la Génération de Nombres Aléatoires

Ce code C, développé par Mehdi Lazaar, vise à générer des nombres aléatoires et à évaluer statistiquement leur répartition en utilisant deux méthodes différentes : le générateur de nombres pseudo-aléatoires standard et un générateur de nombres pseudo-aléatoires personnalisé.

## Objectif

L'objectif principal du code est de :

- Générer une grande quantité de nombres aléatoires.
- Étudier statistiquement la répartition des nombres générés.
- Calculer le coefficient de variation pour évaluer l'équilibre des nombres générés.

## Principales fonctionnalités

### Génération des nombres aléatoires

- Le programme utilise deux méthodes distinctes pour générer des nombres aléatoires :
  1. **Méthode standard** : Utilisation de la fonction `rand()` de la bibliothèque standard pour générer des nombres aléatoires.
  2. **Méthode personnalisée** : Utilisation d'un générateur de nombres pseudo-aléatoires personnalisé en utilisant l'algorithme de Lehmer pour produire des nombres aléatoires dans un intervalle donné.

### Traitement par processus

- Le code utilise des processus forkés pour exécuter les calculs de manière parallèle afin d'accélérer le traitement des nombres aléatoires.
- Les fils créés exécutent des boucles pour générer et accumuler des nombres aléatoires dans des tableaux distincts.

### Utilisation de mémoire partagée

- Le programme utilise la mémoire partagée pour stocker les résultats générés par les fils afin que le processus parent puisse les récupérer et les analyser.
- Un segment de mémoire partagée est créé pour chaque méthode de génération de nombres aléatoires.

### Calcul statistique

- Pour évaluer la distribution des nombres générés, le programme calcule le coefficient de variation.
- Le coefficient de variation est comparé à un seuil (0.05) pour déterminer si la distribution est équilibrée ou non.

## Principaux points d'intérêt

- Utilisation de sémaphores pour assurer la synchronisation entre les processus.
- Calcul du coefficient de variation pour évaluer l'équilibre de la distribution des nombres générés.
- Affichage des occurrences de chaque chiffre pour avoir un aperçu de la répartition.

## Conclusion

En résumé, ce code implémente des méthodes de génération de nombres aléatoires, les exécute en parallèle à l'aide de processus forkés, stocke les résultats dans des segments de mémoire partagée, et effectue des calculs statistiques pour évaluer la répartition des nombres générés. Cela permet d'étudier la qualité de la génération des nombres aléatoires et d'analyser leur distribution pour des applications nécessitant une randomisation efficace.
