# Thesis

TODO List pour ma thèse

## Général

- [ ] Vérifier l'emploi de \K et \KE
- [ ] Vérifier l'emploi de \in et \subset, y compris dans les \sum et \max
- [ ] Vérifier l'emploi des opérateurs mathématiques, éviter les chaînes de caractères dans les formules mathématiques
- [ ] Evoquer la différence entre notre technique d'agrégation et le clustering
- [ ] Attention aux références manquantes [??]
- [ ] Attention aux titres trop longs : proposer une version courte pour le haut de page
- [ ] Cohérence des notations temporelles : commencer à 0 et non à 1

## Chapitres

### Résumé
TODO

### Abstract
TODO

### Chapitre 1 - Intro
TODO

### Chapitre 2
TODO

### Chapitre 3
TODO

### Chapitre 4
TODO

### Chapitre 5
TODO

### Chapitre 6

- [ ] Intro
- [ ] Figures Appli multimedia
- [ ] Description Appli calcul parallèle
- [ ] Algo complet (Annexe?)
- [ ] Mode
- [ ] Citations
- [ ] Use cases
- [ ] Bilan
- [ ] Future work

### Chapitre 7

- [ ] Intro
- [ ] Intro des sous-parties
- [ ] Citations
- [ ] Critères multidimensionnels (garder ici ou déplacer)
- [ ] Figures avec les agrégats interdits
- [ ] Comparaison avec d'autres types d'agrégations (rédiger)
- [ ] Use cases
- [ ] Bilan
- [ ] Future work 

### Chapitre 8

- [ ] Intro
- [ ] Citations
- [ ] Citer github (Ocelotl et LPAggreg)
- [ ] Expliquer bouton HOME
- [ ] Figure des composants
- [ ] Figure switch Gantt chart
- [ ] Figure stats
- [ ] Figure click for more details
- [ ] évoquer le problème général et les axes de recherche d'optimisation générique des queries
- [ ] Perf queries
- [ ] Perf cache
- [ ] Exemple de réduction de taille de trace
- [ ] Compléter calcul dicho agrégation temporelle
- [ ] Limites de l'outil
- [ ] Proportion des temps des étapes de l'analyse
- [ ] Comparaison use cases cache approximé et modèle micro parfait
- [ ] Bilan
- [ ] Future work

### Conclusion

TODO

## XP

### Analyse temporelle

En utilisant LTTng pour tracer. Utiliser éventuellement LTTng Eclipse viewer pour comparaisons

_Edit : il est peut-être préférable d'utiliser GStreamer._

- [ ] Lecture d'une vidéo avec fréquence du processeur différente :
      - performance
      - ondemand
      - conservative
      - powersave
- [ ] Lecture d'une vidéo à partir d'une set top box
      - sans activité sur le réseau
      - avec forte activité sur le réseau mais pas sur le disque (scp d'un gros volume de données depuis un autre PC sur le même réseau)
      - avec forte activité sur le disque (lecture simultannée d'autres vidéos depuis un autre poste)

### Traces synthétiques

- [ ] Générer les traces suivantes (elles ne contiennent que des states):
- 10000 EP feuilles, 5 niveaux hiérarchiques équitablement répartis (root, 10 fils, 10 fils chacun, 10 fils chacun, 10 fils feuilles chacun)
- 10 ET
- Pas de trou, trace parallèle: chaque feuille est, à un instant t, dans un seul état à la fois.
- Distribution homogène des durées : entre 1 (le minimum) et (valeur temps max)/(nombre d'évènements)
où la valeur temps max est définie par le type du temps (int, long, etc).
- Tailles de traces : 1Mevent, 10Mevent, 100Mevent, 1Gevent, 2Gevent, max Gevent

### Influence des queries

- [ ] Effectuer un test exhaustif (métrique : states) de temps de lecture + reconstruction du modèle micro avec différentes tailles de traces, différents nombres de TS (10 à x000), 4 threads et 100000 events per query, et différentes optimisations des queries QUERY: 
- full optimization (OPT)
- time optimization only (T)
- event producers optimization only (EP)
- event types optimization only (ET)
- time + event producers optimization (TEP)
- time + event types optimization (TET)
- event producers + event types optimization (EPET)
- no optimization (NOPT)
 
Header:
"TRACE", "PRODUCERS", "LEAVES", "START", "END", "EVENTS", "TRACESIZE", "TS", "QUERY", "MICROMODEL"


### Influence du cache

- [ ] Effectuer un test exhaustif  (métrique : states) de temps de lecture + reconstruction du modèle micro avec différentes tailles de traces, différents nombres de TS (10 à x000), 4 threads et 100000 events per query et différentes politiques de cache DATACACHE :
- NOCACHE
- OPTIMAL
- APPROX
 
Header:
"TRACE", "PRODUCERS", "LEAVES", "START", "END", "EVENTS", "TRACESIZE", "TS", "DATACACHE", "MICROMODEL"

Nous ne traiterons pas la reconstruction à query partielle
