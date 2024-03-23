# ДЗ №5: Свойства логистической регрессии

Вес = 0,5

Дедлайн - 30.03.2023

В лекциях была рассмотрена модель логистической регрессии.

Напомним, в этой модели с практической точки зрения есть два ключевых свойства:

- Вероятность для объекта быть объектом класса $c=1$ в бинарном случае моделируется как математическое ожидание случайной величины $y_i$:
  $$
  y_i \sim \mathcal{B}\left(p_i\right),
  $$
  где $\mathcal{B}\left(p_i\right)$ - обозначение распределения Бернулли с параметром $p_i$, $i$ - индекс, нумерующий объекты выборки. При этом параметр $p_i$ этого распределения предполагается связанным с признаковым описанием $x_i$ объекта следующей обобщенной линейной функцией (сигмоидой):
  $$
  p=\frac{1}{1+e^{-z}},\\
  z=\theta\cdot x
  $$
  где  $\theta$ - параметры модели, оптимизируемые в подходе максимального правдоподобия (MLE, Maximum Likelihood Estimation).

- Подход оптимизации (максимизации) правдоподобия в случае бинарной задачи приводит к следующей функции потерь:
  $$
  \mathcal{L}\left(\theta,X\right) = -\sum_{i=1}^{N}\left(y_i*\operatorname{ln}p_i + \left( 1-y_i \right)*\operatorname{ln}\left( 1-p_i \right) \right)
  $$



На лекции без доказательства были произнесены следующие свойства логистической регрессии:



<h1>1.</h1>

У функции потерь (3) есть минимум, он единственный и потому глобальный. **Покажите это.**

> > Подсказка: для этого необходимо показать, что:
> >
> > - функции $f_1=-\operatorname{ln}\left(\sigma\left(z\right)\right)$ и $f_2=-\operatorname{ln}\left(1-\sigma\left(z\right)\right)$ выпуклые на одномерном пространстве $z$. А именно: производная этих функций по $z$ везде возрастает, или, что эквивалентно с допущением о двойном дифференцировании, вторая производная по $z$ везде положительна;
> > - Дважды дифференцируемая функция аффинной функции ($\theta\cdot x$) выпукла на пространстве $\theta$.



<h1>2.</h1>

Разделяющая гиперповерхность в решении с применением модели логистической регрессии линейна. То есть, в случае двумерного признакового описания это прямая, в случае трехмерного - плоскость, в случае многомерного - гиперплоскость. **Покажите это.**

> > Подсказка: для этого имеет смысл воспользоваться смыслом разделяющей поверхности: это поверхность, во всех точках которой выполняется условие $p=С$, где $C$ - некоторая константа, например, $C=0,5$.