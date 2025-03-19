---
layout: center
---
# Метрики качества классификации

---

# Матрица ошибок

#### Рассмотрим задачу классификации с 4 классами
<br>
<div class="grid grid-cols-[3fr_4fr] gap-20">
<div>
  <figure>
    <img src="/confusion_matrix_1.png" style="width: 290px !important;">
  </figure>
</div>
<div>

#### В матрице:
* Значение - число объектов $j$-го класса, которые были предсказаны как $i$-й класс

* Диагональные элементы - <span style="color:#82B366">**верные**</span> классификации

* Внедиагональные элементы - <span style="color:#B85450">**неверные**</span> классификации
</div>
</div>

---

# Бинарная классификация

#### Рассмотрим задачу бинарной классификации с классами **+** и **-**
<br>
<div class="grid grid-cols-[3fr_4fr] gap-30">
<div>
  <figure>
    <img src="/confusion_matrix_2.png" style="width: 390px !important;">
  </figure>
</div>
<div>


</div>
</div>

---

# Бинарная классификация

#### Рассмотрим задачу бинарной классификации с классами **+** и **-**
<br>
<div class="grid grid-cols-[3fr_4fr] gap-30">
<div>
  <figure>
    <img src="/accuracy.png" style="width: 390px !important;">
  </figure>
</div>
<div>

#### Метрики качества:
  <figure>
    <img src="/accuracy_f.png" style="height: 60px !important;">
  </figure>
</div>
</div>

---

# Бинарная классификация

#### Рассмотрим задачу бинарной классификации с классами **+** и **-**
<br>
<div class="grid grid-cols-[3fr_4fr] gap-30">
<div>
  <figure>
    <img src="/tpr.png" style="width: 390px !important;">
  </figure>
</div>
<div>

#### Метрики качества:
  <figure>
    <img src="/accuracy_f_clean.png" style="height: 60px !important;">
  </figure>
  <figure>
    <img src="/tpr_f.png" style="height: 60px !important;">
  </figure>
</div>
</div>

---

# Бинарная классификация

#### Рассмотрим задачу бинарной классификации с классами **+** и **-**
<br>
<div class="grid grid-cols-[3fr_4fr] gap-30">
<div>
  <figure>
    <img src="/fpr.png" style="width: 390px !important;">
  </figure>
</div>
<div>

#### Метрики качества:
  <figure>
    <img src="/accuracy_f_clean.png" style="height: 60px !important;">
  </figure>
  <figure>
    <img src="/tpr_f_clean.png" style="height: 60px !important;">
  </figure>
    <figure>
    <img src="/fpr_f.png" style="height: 60px !important;">
  </figure>
</div>
</div>

---

# Бинарная классификация

#### Рассмотрим задачу бинарной классификации с классами **+** и **-**
<br>
<div class="grid grid-cols-[3fr_4fr] gap-30">
<div>
  <figure>
    <img src="/precision.png" style="width: 390px !important;">
  </figure>
</div>
<div>

#### Метрики качества:
  <figure>
    <img src="/accuracy_f_clean.png" style="height: 60px !important;">
  </figure>
  <figure>
    <img src="/tpr_f_clean.png" style="height: 60px !important;">
  </figure>
  <figure>
    <img src="/fpr_f_clean.png" style="height: 60px !important;">
  </figure>
  <figure>
    <img src="/pr_f.png" style="height: 60px !important;">
  </figure>
</div>
</div>

---

# Бинарная классификация

#### Рассмотрим задачу бинарной классификации с классами **+** и **-**
<br>
<div class="grid grid-cols-[3fr_4fr] gap-30">
<div>
  <figure>
    <img src="/confusion_matrix_2.png" style="width: 390px !important;">
  </figure>
</div>
<div>

#### Метрики качества:
  <figure>
    <img src="/accuracy_f_clean.png" style="height: 60px !important;">
  </figure>
  <figure>
    <img src="/tpr_f_clean.png" style="height: 60px !important;">
  </figure>
  <figure>
    <img src="/fpr_f_clean.png" style="height: 60px !important;">
  </figure>
  <figure>
    <img src="/pr_f_clean.png" style="height: 60px !important;">
  </figure>
  <figure>
    <img src="/F1_f.png" style="height: 60px !important;">
  </figure>
</div>
</div>

---

# Предсказание непрерывных значений

#### Многие алгоритмы классификации работают с непрерывными функциями оценки
<br>
<div class="grid grid-cols-[2fr_2fr] gap-20">
<div>
    <figure>
    <img src="/continuous_classification_1.png" style="height: 250px !important">
    <br>
    <figcaption style="font-size: 16px;"><center>Предсказание модели классификации</center>
    </figcaption>
  </figure>
</div>
<div>
    <figure>
    <img src="/continuous_classification_2.png" style="height: 250px !important">
    <br>
    <figcaption style="font-size: 16px;"><center>Значение функции оценки в данных</center>
    </figcaption>
  </figure>
</div>
</div>

---

# ROC-кривая

#### Receiver Operating Characteristic = **TPR** как функция **FPR**
<br>
    <figure>
    <img src="/ROC_curve.png" style="width: 500px !important">
  </figure>

[Интерактивный пример](http://arogozhnikov.github.io/2015/10/05/roc-curve.html)

---

# Кривая Precision-Recall

  <figure>
    <img src="/Precision_Recall_curve.png" style="width: 500px !important">
  </figure>

##### Кривая Precision-Recall показывает компромисс между Precision и Recall для различных пороговых значений. Большая площадь под кривой означает как высокое значение Precision (низкий уровень ложноположительных результатов), так и высокое значение Recall (низкий уровень ложноотрицательных результатов)
