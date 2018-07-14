# OOP
Задания для данной программы:

Задание №1.
Спроектировать и реализовать шаблонный класс Container со следующими возможностями:
    - добавить новый элемент в начало/конец;
    - удалить первый/последний элемент;
    - получить значение первого/последнего элемента;
    - перебрать все элементы (не обязательно делать итератор);
    - узнать кол-во элементов;
    - проверить на пустоту;
    - очистить.

Класс должен быть эффективным и универсальным (должен подходить для хранения экземпляров любых типов и использования где угодно).
Для тех, кто в танке: не надо реализовывать Container с помощью какого-либо готового класса контейнера.

Задание №2.
Создать абстрактный класс Printable – базовый класс для всех сущностей, информацию о которых можно представить (распечатать) в виде строки (std::string).
Создать класс Named – наследник Printable – базовый класс для всех сущностей, которые имеют имя. Строка с именем без default-значения передаётся в единственный конструктор.
Создать абстрактный класс Shape – наследник Printable – базовый класс для фигур на декартовой плоскости.

Спроектировать и реализовать иерархию классов конкретных именованных (т.е. наследников Named) фигур:
   Point - точка,
   Circle - окружность,
   Rect - прямоугольник со сторонами, параллельными OX и OY (с помощью двух точек),
   Square - прямоугольник с одинаковыми сторонами,
   Polyline - ломаная; должна быть реализована с помощью Container< Point >, наполняться с помощью метода AddPoint( Point const & point ),
   Polygon - произвольный многоугольник.

С помощью статического метода Shape::GetCount() реализовать возможность узнать, сколько существует экземпляров Shape (т.е. любых фигур) в данный момент.
У каждой фигуры в качестве текстовой информации должна печататься содержательная информация, например, у точки есть координаты, у окружности ещё есть радиус и площадь, у ломаной - длина и т.п.
Необходимо реализовать также и вывод информации о каждом объекте в стандартный поток вывода std::ostream с помощью оператора std::ostream & operator << ( std::ostream & ioStream, ... );

Реализовать фабрику фигур, которая умеет создавать конкретную фигуру заданного типа со случайными параметрами.

Задание №3.
Составить и отладить программу:
  - создать Container фигур, наполнить его в цикле конкретными фигурами (не менее 20 штук) случайного типа с помощью фабрики фигур.
  - вывести в std::cout общее кол-во фигур с помощью Shape::GetCount();
  - напечатать в std::cout сведения обо всех фигурах;
  - очистить память (удалить все фигуры);
  - вывести в std::cout общее кол-во фигур с помощью Shape::GetCount() – если оказалось не 0, разобраться, почему, и исправить;
  - завершить работу программы.

Предусмотреть обработку исключительных ситуаций с помощью исключений С++, например: взятие элемента из пустого контейнера, создание "вывернутого" прямоугольника, и пр.
Обратить особое внимание на правильное использование спецификатора const при описании методов классов в соответствии с их семантикой.

Прошу:
  - классы Named и Printable описать в файле Base.h;
  - все классы фигур описать и реализовать в одном файле Shapes.h;
  - фабрику фигур описать в отдельном файле;
  - третье задание реализовать в файле Main.cpp.
