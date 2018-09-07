# GCGen  (Global Constrained optimization problem Generator)

Один из подходов к исследованию и сравнению методов многоэкстремальной оптимизации основан на решении с помощью данных методов серии задач, выбранных случайно из некоторого класса.
В генераторе GCGen предполагается, что задача условной оптимизации поставлена в виде

min{φ(y): y ∈ D, g<sub>i</sub>(y) ≤ 0, 1 ≤ i ≤ m}			
D = {y ∈ R<sup>N</sup>: a<sub>j</sub> ≤ y<sub>j</sub> ≤ b<sub>j</sub>, 1 ≤ j ≤ N}.
	
где функционал φ(y) (обозначаемый в дальнейшем также g<sub>(m+1)</sub>(y)) – N-мерная целевая функция, а g<sub>i</sub>(y), 1 ≤ i ≤ m, – функциональные ограничения.
При этом будем предполагать, что функционалы g<sub>i</sub>(y), 1 ≤ i ≤ m, удовлетворяют условию Липшица с априори неизвестными константами L<sub>i</sub>, т.е.

|g<sub>i</sub>(y<sub>1</sub>) - g<sub>i</sub>(y<sub>2</sub>)| ≤ L<sub>i</sub>‖y<sub>1</sub> - y<sub>2</sub>‖, 1 ≤ i ≤ m + 1.

В качестве целевой функции задачи условной оптимизации генератор GCGen может использовать только функционал, для которого известна точка глобального минимума.
Генератор поддерживает формирование задачи условной оптимизации со следующими настройками:
* возможность задавать объем допустимой области по отношению ко всей области изменения параметров (т.е. долю допустимой области в гиперпараллелепипеде D);
* возможность изменить целевую функцию так, чтобы глобальный минимум находился вне допустимой области;
* возможность сдвинуть точку условного глобального минимума на границу допустимой области;
* возможность задать число активных ограничений в точке условного глобального минимума.