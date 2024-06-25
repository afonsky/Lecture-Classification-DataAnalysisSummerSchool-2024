---
layout: center
---
# Дополнительные материалы

---

# Условные обозначения

* $a \in A$ - **принадлежность** множеству: $a$ - *элемент* множества $A$
* $\lvert B \rvert$ - **мощность** множества: количество элементов в множестве $B$

<div class="grid grid-cols-[5fr_3fr] gap-5]">
<div>

* $\lVert \bm{v} \rVert$ - **норма**: "длина" вектора $\bm{v}$<br> Расстояния:
  * **манхэттенское** ($L_1$)
  * **евклидово** ($L_2$)
* $\sum$ - сумма
* $\int$ - интеграл
* $\R$ - пространство **вещественных** чисел
* $\R^n$ - то же, но размерности $n$
</div>
<div>
  <figure>
    <img src="/1280px-Manhattan_distance.svg.png" style="width: 500px !important;">
    <figcaption style="color:#b3b3b3ff; font-size: 11px; position: absolute;">Источник:<br>
      <a href="https://ru.wikipedia.org/wiki/Расстояние_городских_кварталов">https://ru.wikipedia.org/wiki/Расстояние_городских_кварталов</a>
    </figcaption>
  </figure>   
</div>
</div>

---

# Условные обозначения

* $\frac{\mathrm{d}y}{\mathrm{d}x}$ - **производная** функции $y$ по переменной $x$
* $f: A \rightarrow B$ - функция (отображение) области определений $A$ в область значений $B$
  * $A$ и $B$ могут быть подмножествами многомерного пространства $\R^n, n > 1$
    * Например: $f(x), f(\bm{x}), \bm{f}(x), \bm{f}(\bm{x})$
<div class="grid grid-cols-[5fr_3fr] gap-5]">
<div>

* $\frac{\partial{y}}{\partial{x_i}}$ - частная производная функции $y$<br> по $i$-ой компоненте вектора $\bm{x}$
* $X_{n \times p}$ - **матрица данных** размера $n \times p$
  * столбцы $X_i$ **признаков**<br> (фичей, переменных, предикторов)
  * строки $x_j$ **наблюдений**
* $\bm{x}, \bm{y}, \bm{z}$ - векторы; $\bm{A}, \bm{B}, \bm{X}$ - матрицы

</div>
<div>
  <figure>
    <img src="/data_matrix.png" style="width: 200px !important; position:absolute; bottom:5px">
  </figure>   
</div>
</div>

---

# Бесплатного завтрака не бывает (Теорема NFL)

* Зачем нам множество функций, моделей, подходов?
* Почему просто не использовать нейронные сети (или градиентный бустинг) **всюду**?
* Пусть $A$ - любой алгоритм обучения для задачи бинарной классификации с потерями $0-1$ в области $X$, и $N \leq 0.5 \lvert X \rvert$. Тогда существует распределение (набор данных) $D$ при следующих условиях:
  1. Существует функция $f$ с $\mathcal{L} (D, f) = 0$
  1. С вероятностью по крайней мере $1/7$ при выборе $S \sim D^N$, мы получим $\mathcal{L} (D, \mathcal{A}(S)) \geq 1/8$ (cм. [understanding-machine-learning/](https://www.cambridge.org/core/books/understanding-machine-learning/3059695661405D25673058E43C8BE2A6))
* Даже если мы найдем очень хороший алгоритм $A$, который хорошо работает на одних данных, он все равно может потерпеть неудачу на других данных
* Это справедливо только при отсутствии знании о данных!   
* Поэтому искусство машинного обучения заключается в тщательном выборе наилучшего метода для конкретного набора данных. 

---

# Методы регуляризации

* Здесь мы добавляем штраф $\mathrm{RSS}$, чтобы уменьшить коэффициенты модели до нуля во время обучения
    * Это приводит к уменьшению вычислений и меньшему разбросу коэффициентов <br>
    $\mathrm{RSS}(\lambda, \beta, X) := \sum(y_i - \hat{y}_i)^2 + \lambda \lVert\beta\rVert_k$, $~~\lambda \geq 0$
        * где $\lambda$ - **гиперпараметр настройки**, $\lambda \lVert\beta\rVert_k$ - **штраф**, $\beta := \beta_{1:p}$

<v-clicks depth="2">

* **Ridge**: $k = 2$, т.е. $\lVert\beta\rVert_2^2 = \beta^{\prime}\beta = \sum \beta_i^2$
    * она же 2-норма, евклидово расстояние (от нуля), $L_2$, $L^2$, $L2$, $\ell_2$
        * Это длина вектора $\beta$
    * $\beta_i$ постепенно приближается к нулю с увеличением $\lambda$
* **Lasso**: $k = 1$, т.е. $\lVert\beta\rVert_1 = \bm{1}^{\prime} \beta = \sum\lvert\beta_i\rvert$
    * она же 1-норма, манхэттенское расстояние, $L_1$, $L^1$, $L1$, $\ell_1$
    * $\beta_i$ постепенно приближается, а затем **сходит на нет** при увеличении $\lambda$

</v-clicks>

---

# Методы регуляризации

* $\mathrm{RSS}(\lambda, \beta, X) := \sum(y_i - \hat{y}_i)^2 + \lambda \lVert\beta\rVert_k$, $~~\lambda \geq 0$
* Как для **Ridge**, так и для **Lasso**:
    * По мере того, как $\lambda \to \infty$, оптимизатор больше фокусируется на минимизации штрафа
        * Это **гиперпараметр**, который мы должны выбрать (пробуя различные значения)
            * Сам $\beta_0$ исключается из штрафа, поскольку не связывает признаки с ответом


---

# Методы регуляризации: Lasso и Ridge

<br>
<div>
<figure>
  <img src="/ridge_lasso_explained.png" style="width: 690px !important;">
  <figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: -50px; left: 650px;">Источник:
    <a href="https://hastie.su.domains/ISLR2/ISLP_website.pdf#page=255">ISLP Fig. 6.7</a>
  </figcaption>
</figure>
</div>