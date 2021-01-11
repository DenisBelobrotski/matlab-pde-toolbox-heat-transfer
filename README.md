Задача: В среде PDE Toolbox построить математическую модель стационарного распределения температуры в плоской пластине круговой формы диаметром 1 м  с квадратным  отверстием  0.25х0.25 м  в центре . Коэффициент теплопроводности (heat capacity coefficient) (коэффициент C в PDE в матлабе, по умолчанию = 1) пластины в системе координат с центром в точке симметрии  имеет следующую зависимость С=10*(x2+y2) [ Вт/(K∙m)].  Температура на верхней горизонтальной стороне отверстия  t1=40Со  на нижней  t0=0Со  . На боковых сторонах отверстия и внешней стороне круга  заданы условия термоизоляции (нулевой тепловой поток) (heat flow). Пластина равномерно нагревается тепловым излучением (heat source, коэффициент F в PDE, по умолчанию = 0), плотность которого  600 Вт/м2.  Изобразить температуру и направления тепловых потоков в пластине. Какова максимальная температура нагрева пластины по результатам численного моделирования. Теплообменом на плоскостях пластины пренебречь

[онлайн гайд по PDE, стр. 2-16](https://www.yumpu.com/en/document/read/12103823/partial-differential-equation-toolbox-users-guide)

[коэффициенты pde](https://www.mathworks.com/help/pde/ug/specify-coefficients-in-pdemodeler-app.html)

Чтобы найти максимальную температуру, можно сделать Solve->Export solution, а потом с решением делать что угодно, найти max, например.

maxValue = max(u, [], 'all');
где u - решение PDE, экспортированное из PDE Toolbox.

Для экспорта решения в csv можно сделать `writematrix(u,'solution.csv')` для v.2019+ или `csvwrite('solution.csv', u)` для v.2018-. Далее, чтобы Excel нормально распарсил файл, нужно заменить `,` на `;`.

[Heat equation](https://en.wikipedia.org/wiki/Heat_equation)

[Задача Неймана (Neumann boundary condition)](https://en.wikipedia.org/wiki/Neumann_boundary_condition)

[Задача Дирихле (Dirichlet boundary condition)](https://en.wikipedia.org/wiki/Dirichlet_boundary_condition)

[Elliptic partial differential equation](https://en.wikipedia.org/wiki/Elliptic_partial_differential_equation)
* стационарные процессы, описываемые параболическими и гиперболическими уравнениями
* уравнение Пуассона
* уравнение Лапласса

[Parabolic partial differential equation](https://en.wikipedia.org/wiki/Parabolic_partial_differential_equation)
* конвекция
* диффузия
* теплопроводность

[Hyperbolic partial differential equation](https://en.wikipedia.org/wiki/Hyperbolic_partial_differential_equation)
* волновые уравнения
* уравнение Максвелла, электромагнитные поля

условие Дирихле - температура на границе
* h = 1, r = temperature

условие Неймана - тепловой поток
* q - 0, g - heat transfer coefficient
* q - surrounding temperature, g - surrounding temperature * heat transfer coefficient

[Relative tolerance](https://www.mathworks.com/help/simulink/gui/relative-tolerance.html)

[Absolute tolerance](https://www.mathworks.com/help/simulink/gui/absolute-tolerance.html)
