---
theme: seriph
addons:
  - "@twitwi/slidev-addon-ultracharger"
addonsConfig:
  ultracharger:
    inlineSvg:
      markersWorkaround: false
    disable:
      - metaFooter
      - tocFooter
NObackground: >-
  https://images.unsplash.com/photo-1511149755252-35875b273fd6?ixlib=rb-4.0.3&dl=leon-contreras-qpdfU6vehgs-unsplash.jpg&w=1920&q=80&fm=jpg&crop=entropy&cs=tinysrgb
background: false
highlighter: shiki
routerMode: hash
lineNumbers: false
info: >
  ## Slidev ultracharger demo

  A doc / demo presentation for the ultracharger set of
  [Sli.dev](https://sli.dev) addons.

  It also acts as an experimental area for some features I can imagine.


  NB: [Source code
  available](https://github.com/twitwi/slidev-addon-ultracharger)
css: unocss
title: Летняя школа по анализу данных
subtitle: Задача классификации
date: 25/06/2024
venue: ВШЭ
author: Алексей Болдырев
---

<br>
<br>
<br>
<br>
<br>

# <span style="font-size:28.0pt" v-html="$slidev.configs.title?.replaceAll(' ', '<br/>')"></span>
# <span style="font-size:24.0pt" v-html="$slidev.configs.subtitle?.replaceAll(' ', '<br/>')"></span>
# <span style="font-size:18.0pt" v-html="$slidev.configs.author?.replaceAll(' ', '<br/>')"></span>

<span style="font-size:18.0pt" v-html="$slidev.configs.date?.replaceAll(' ', '<br/>')"></span>

<div class="abs-tr mx-5 my-5">
  <img src="/FCS_logo_full_ru_L.svg" class="h-18">
</div>

<!-- <div class="abs-tl mx-5 my-5">
  <img src="/gp_logo.png" class="h-24">
</div> -->


<style>
  :deep(footer) { padding-bottom: 3em !important; }
</style>

<!--
NB: This demo uses a custom syntax (using preparser extensions), with all the @@@@.
-->


---
src: ./slides/0_introduction.md
---

---
src: ./slides/1_trees.md
---

---
src: ./slides/2_classification_metrics.md
---

---
src: ./slides/3_resampling.md
---

---
src: ./slides/4_dimensionality_reduction.md
---

---
src: ./slides/5_supplementary.md
---

---
src: ./slides/0_end.md
---