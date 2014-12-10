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

### Influence des queries

Effectuer un test exhaustif de temps de lecture + reconstruction du modèle micro avec différentes tailles de traces (jusqu'à 3 milliards -1 events, soit environ 100 Go), différents nombres de TS, et différentes optimisations des queries: 

- full optimization (query "*")
- time optimization
- event producers optimization
- event types optimization
- time + event producers optimization
- time + event types optimization
- event producers + event types optimization
- no optimization
