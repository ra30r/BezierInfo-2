# Интервал Безье [0,1]

В математике кривых Безье, вы могли заметить одну любопытную деталь — кривые Безье всегда считают вдоль одного и того же интервала t, `t=0` to `t=1`. Почему же именно этот интервал? 

Последнее обусловленно тем, как мы определяем "начало" и "конец" нашей кривой.  Если у нас есть значение, которое представляет собой сочетание двух других значений, тогда общая формула для этого будет:

\[
  mixture = a \cdot value_1 + b \cdot value_2
\]

Очевидно, что начальное и конечное значения `a` и `b` должны быть `a=1, b=0`, чтобы в начале получать вывод 100% первого показателя и 0% второго; и `a=0, b=1`, чтобы в конце получать 0% value 1 и 100% value 2. В дополнение, мы не хотим чтобы "a" и "b" были независимыми, в коем случае можно было бы присвоить им любые значения и на выводе получить, например, 100% первого показателя **и** 100% второго. В принципе, с последним все ок, но в случае кривых Безье, мы всегда должны получать значение *между* двух крайностей, потому нельзя присвоить `a` и `b` значения, которые бы вместе составляли суму более 100% на выводе, что можно записать как:

\[
  m = a \cdot value_1 + (1 - a) \cdot value_2
\]

С этим у нас есть гарантия, что мы не получим суму значений пропорций более 100%. Мы ограничиваем значение `a` интервалом [0,1], потому всегда получаем вывод из пропорционального смешения двух показателей, с сумой смесителей не превышающей 100%.

Но... что если мы воспользуемся этой формой, предполагающей что мы всегда будем использовать значения а между 0 и 1, для подсчета точек лежащих вне стандартного интервала? Наши вычисления пойдут по откосной? Что ж... не то чтобы, мы попросту увидим больше.

В случае кривой Безье, продление интервала просто продляет развитие кривой. Кривые Безье всего лишь сегменты полиноминальных кривых. Выбирая более широкий отрезок — мы можем проследить дальнейшее развитие кривой. И как же это выглядит?

Ниже представлены графики кривых Безье, зарисованных "обычным путем", по верх зарисовки кривых на которых они лежат, полученных путем расширения интервала значений `t`. Как мы можем наблюдать, кривая Безье есть частью большей формы, скрытой за границами нашего интервала, которую мы так-же можем регулировать путем перемещения контрольных точек.

<div class="figure">
<graphics-element title="Квадратный бесконечный интервал кривой Безье" src="./extended.js" data-type="quadratic"></graphics-element>
<graphics-element title="Кубический бесконечный интервал кривой Безье" src="./extended.js" data-type="cubic"></graphics-element>
</div>

В области компьютерной графики, существуют множество кривых, которые действуют по противоположному кривым Безье принципу: вместо фиксированного интервала и свободного выбора контрольных точек формирующих развитие искривлений, они фиксируют форму кривой, предоставляя возможность выбора интервала. Отличным примером последней есть [кривая "Spiro"](https://levien.com/phd/phd.html), которая частично базируется на [спирали Корню](https://ru.wikipedia.org/wiki/%D0%9A%D0%BB%D0%BE%D1%82%D0%BE%D0%B8%D0%B4%D0%B0), также известной как [спираль Эйлера](https://ru.qaz.wiki/wiki/Euler_spiral) (* в оригинале другая [ссылка на Корню и Эйлера](https://en.wikipedia.org/wiki/Euler_spiral) ). Эту эстетически  приятную кривую можно встретить в нескольких графических пакетах: [FontForge](https://fontforge.org/en-US/) и [Inkscape](https://inkscape.org). Ее даже используют в дизайне шрифтов, например в начертания шрифта Inconsolata.  

