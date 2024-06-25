---
layout: center
---
# Деревья решений

---

# Деревья решений

<div class="grid grid-cols-[5fr_3fr] gap-1">
<div>

* Мы делим пространство признаков на **прямоугольные области** $\{R_m\}_{1:M}$ и присваиваем **константу** $c_m$ каждой из них
* Используем **бинарное рекурсивное разделение**
* **Разделение** делается исходя из<br> “лучшего” различения получившегося
  * “лучшее” означает:
    * В регрессии: 
      * Наименьшая общая ошибка в каждой ветви
    * В классификации: 
      * **Самые чистые** классы в каждой ветви
</div>
<div>
    <figure>
    <img src="/ESL_figure_9.2.png" style="width: 420px !important">
    <figcaption style="color:#b3b3b3ff; font-size: 11px;"><br>Источник:
      <a href="https://hastie.su.domains/ElemStatLearn/printings/ESLII_print12.pdf#page=325">ESL Fig. 9.2</a>
    </figcaption>
  </figure>
</div>
</div>

* Модель: $\hat{f}(\bm{X}_{1 \times p}) := \sum_m c_m I (\bm{X} \in R_m)$

---

# Построение деревьев регрессии

* Выбираем $\{R_m\}$ для получения минимального RSS в каждой области $R_m$
* Минимизация $\hat{c}_m := \bar{y} |_{R_m} = \frac{1}{N_m} \sum_{x_i \in R_m} y_i$
  * усредненный ответ на $R_m$
  * $N_m := \# \{x_i \in R_m \}$
  * Поиск всевозможных комбинаций $\{R_m\}$ вычислительно труден
* "Жадный" способ:
  * В каждом узле мы ищем разделяющую переменную $j$ и точку $s$ для получения минимального RSS:
  $\min_{j, s} \big[\min_{c_1}~ \mathrm{RSS}_{\mathrm{Left}}(j, s)~~+~~ \min_{c_2}~ \mathrm{RSS}_{\mathrm{Right}}(j, s) \big] =$
  $~~~~~~~~\min_{j, s} \big[\min_{c_1}\sum_{x_i \in R_1(j, s)} (y_i - c_1)^2 ~~+~~ \min_{c_2} \sum_{x_i \in R_2(j, s)} (y_i - c_2)^2 \big]$
  * Повторяем разделение на каждой получившейся области
* Без дополнительных ограничений мы получаем переобучение

---

# Контроль переобучения

* Один из подходов:
  * Рассмотрим порог $\tau$
  * Если $\Delta \mathrm{RSS} > \tau$, продолжаем разделение

<div class="grid grid-cols-[5fr_5fr] gap-5">
<div>

* $\Delta \mathrm{RSS}$ (или $\Delta \mathrm{MSE}$) могут возрасти <br> или уменьшиться с ростом дерева
  * Мы должны предусмотреть остановку алгоритма
* Пример:
  * Если $\tau_{\mathrm{MSE}} = 6$, тогда левая ветвь не построится
  * Но $\mathrm{MSE}$ уменьшится на $30.5$
</div>
<div>
    <figure>
    <img src="/Decision Trees Explained.png" style="width: 420px !important">
    <figcaption style="color:#b3b3b3ff; font-size: 11px;"><br>Источник:
      <a href="https://towardsdatascience.com/decision-trees-explained-3ec41632ceb6">https://towardsdatascience.com/decision-trees-explained-3ec41632ceb6</a>
    </figcaption>
  </figure>
</div>
</div>


---

# Построение деревьев решений

<div>
    <figure>
    <img src="/trees_1.png" style="width: 420px !important">
  </figure>
</div>

---

# Построение деревьев решений

<div>
    <figure>
    <img src="/trees_2.png" style="width: 840px !important">
  </figure>
</div>

---

# Построение деревьев решений

<div>
    <figure>
    <img src="/trees_3.png" style="width: 840px !important">
  </figure>
</div>

---

# Построение деревьев решений

<div>
    <figure>
    <img src="/trees_4.png" style="width: 840px !important">
  </figure>
</div>

---

# Построение деревьев решений

<div>
    <figure>
    <img src="/trees_5.png" style="width: 840px !important">
  </figure>
</div>

---

# Демо различных методов классификации

[Демо различных методов классификации](http://www.ccom.ucsd.edu/~cdeotte/programs/classify.html)