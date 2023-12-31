# Простой поиск пиков

***Задание с 2 на 3***

У вас есть спектр, полученный по результатом спектрометрии некоторого объекта. Данные записаны в файл spectrum.dat (первый столбец -- частоты, второй -- амплитуда сигнала).
Вам необходимо определить пики, что поможет определить состав исследуемого объекта.
Учтите, что у спектра есть некоторая подложка. Для её определения при проведения эксперимента был записана область, в которой гарантированно нет сигнала.

* Точка является пиком, если она является локальным максимумом (Правая, forward, и левая, backward, [конечные разности](https://en.wikipedia.org/wiki/Finite_difference) разных знаков).
* Пики различимы, если значение в минимуме между ними меньше k% (варьируемая величина, далее valley_max_val) от значение наименьшего из двух пиков.

## **Задачи:**

1) При помощи средств языка Python и всех доступных в нём библиотек:
   1) Построить график сигнал (амплитуда со спектрометра против частоты),
   2) Определить уровень подложки (далее threshold).
2) При помощи средств языка C++ написать функцию, которая возвращает вектор пар всех найденных пиков. У этой функции должен быть следующая сигнатура.

```cpp
std::vector<std::pair<double, double>> FindPeaks(std::vector<double> xs, std::vector<double> ys, double valley_max_val, double threshold);
```

C++ функция должна быть в отдельном хедере.
