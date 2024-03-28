---
# https://vitepress.dev/reference/default-theme-home-page
layout: home

hero:
  name: "Exercice 16"
  text: "Revue de code documentée"
  actions:
    - theme: brand
      text: Hubert Beaupré
      link: https://qwerff.itch.io/fly-feast
    - theme: alt
      text: Jean-Thomas Lamonde
---

## **Typage de variables**
Typage manquant pour multiples variables (*selectedSong*, *audioPlayer*, *...*).
```js
const selectedSong = ref<Song | null>(null);
```

## **Nommage de fonction**
notifyParentOnUpdate serais plus adéquat que notifyParent lors du changement d'une chanson.

```js
function notifyParent() {
  emit("update", selectedSong.value as Song);
}
```


## **Optimisation de la mise à jour de songPlayerTime**
Le temps étant mis à jour dans songPlayerTime pourrait être mis à jour à chaque milliseconde au lieu de par intervalle de 100 millisecondes.
