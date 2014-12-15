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

### Chapitre 6

- [ ] Figures avec les agrégats interdits


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

- [ ] Générer les traces suivantes :
- 10000 EP feuilles, 5 niveaux hiérarchiques équitablement répartis (root, 10 fils, 10 fils chacun, 10 fils chacun, 10 fils feuilles chacun)
- 10 ET
- Pas de trou, trace parallèle: chaque feuille est, à un instant t, dans un et un seul état particulier.
- Distribution homogène des durées : entre 1 (le minimum) et (valeur temps max)/(nombre d'évènements)
où la valeur temps max est définie par le type du temps (int, long, etc).
- Tailles de traces : 1Mevent, 10Mevent, 100Mevent, 1Gevent, 2Gevent, max Gevent

### Influence des queries

- [ ] Effectuer un test exhaustif de temps de lecture + reconstruction du modèle micro avec différentes tailles de traces, différents nombres de TS (10 à x000), 4 threads et 100000 events per query, et différentes optimisations des queries QUERY: 
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

- [ ] Effectuer un test exhaustif de temps de lecture + reconstruction du modèle micro avec différentes tailles de traces, différents nombres de TS (10 à x000), 4 threads et 100000 events per query et différentes politiques de cache DATACACHE :
- NOCACHE
- OPTIMALCACHE
- APPROX
 
Header:
"TRACE", "PRODUCERS", "LEAVES", "START", "END", "EVENTS", "TRACESIZE", "TS", "DATACACHE", "MICROMODEL"

Nous ne traiterons pas la reconstruction à query partielle
