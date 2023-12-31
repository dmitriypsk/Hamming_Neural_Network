# Hamming_Neural_Network
Нейронная сеть Хэмминга
Введение

Искусственная нейронная сеть Хэмминга используется для решения задач классификации бинарных входных векторов. В основе ее работы лежат процедуры, направленные на выбор в качестве решения задачи классификации одного из эталонных образов, наиболее близкого к поданному на вход сети зашумленному входному образу, и отнесение данного образа к соответствующему классу. Для оценки меры близости к каждому классу используется критерий, учитывающий расстояние Хэмминга – количество различающихся переменных у зашумленного и эталонного входных образов. 
Структурно нейронная сеть Хэмминга включает два слоя, количество нейронов в которых K равно количеству классов (K = N). Число входов M соответствует числу бинарных признаков, по которым различаются образы. Значения входных переменных принадлежат множеству {–1; 1}. Выходные значения подаются по обратным связям на входы нейронов второго слоя, в том числе свой собственный. 
Алгоритмы обучения нейросетей без учителя используют данные без классификации или меток. НС сама выстраивает логическую цепочку и усваивает понимание этих действий, ориентируясь лишь на вводные данные. По сути, это повторяет человеческое самообучение: индивид, предпринимая какие-либо действия, делает выводы о правильности либо ошибочности решения, ориентируясь на последствия.

Задание: 
Реализовать нейронную сеть Хэмминга.
Глава 1. Решение [1, 2]
1.1.	Формируется матрица эталонных образов   размера K x M 

1.2.	Рассчитывается матрица весовых коэффициентов нейронов первого слоя.
1.3.	Определяются настройки активационной функции.

Таким образом, очевидно, что выходы нейронной сети могут принимать любые значения в пределах [0, T].
1.4.	Задаются значения синапсов обратных связей нейронов второго слоя в виде элементов квадратной матрицы размера K x K.

Синапсы обратных связей нейронной сети Хэмминга, имеющие отрицательный вес, называются ингибиторными, или тормозящими.
1.5.	Устанавливается максимально допустимое значение нормы разности выходных векторов на двух последовательных итерациях Emax, требующееся для оценки стабилизации решения. Обычно достаточно принимать Emax = 0,1.
1.6. На входы сети подается неизвестный, в общем случае, зашумленный вектор сигналов.
1.7. Рассчитываются состояния и выходные значения нейронов первого слоя.
Для расчета выходов нейронов первого слоя к полученным значениям состояний применяется активационная функция.
1.8. Выходам нейронов второго слоя в качестве начальных величин присваиваются значения выходов нейронов первого слоя, полученные на предыдущем шаге.
Далее первый слой нейронов на стадии практического использования больше не задействуется.
1.9. Для каждой итерации q рассчитываются новые значения состояний и выходов нейронов второго слоя.
Новые выходные значения определяются в результате применения линейной пороговой активационной функции (2) к соответствующим состояниям нейронов.
1.10. Цикл в пункте 1.8 повторяется до стабилизации выходного вектора в соответствии с условием.

В идеальном случае после стабилизации должен получиться выходной вектор с одним положительным и всеми остальными нулевыми элементами. Индекс единственного положительного элемента непосредственно указывает на класс неизвестного входного образа.

Вывод
В ходе выполнения лабораторной работы я познакомился с алгоритмом Хемминга. Я успешно реализовал модель нейронной сети данного алгоритма. 
Задал исходный набор эталонных образов, представленных в виде бинарных векторов. Каждому из них в соответствие поставил свой класс. Для поданного на входы сети неизвестного образа произвёл сопоставление со всеми известными эталонными образами и отнесение к соответствующему классу.
![image](https://github.com/dmitriypsk/Hamming_Neural_Network/assets/145012611/7aa2d45d-e511-41f7-89f2-c1f280c31c5a)
