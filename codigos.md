# Códigos con Diagramas de Clases

## Universidad de Colima
## FIME
## ICI
## Programación Orientada a Objetos
## Adrian Vladimir Ochoa Ramirez
## 2B
## Codigo hecho en Markdown Monster y luego copiado a github.

### Diagramas de clase #1:

![](1.jpg)

### Codigo #1:

#### main:
```dart
void main(List<String> args) {
  var e1 = Estudiante();
  e1.nombre = "Juan"; //instancia
  e1.aNacimiento = 1990;
  e1.reporte();

  e1.nombre = "Pedro";
  e1.aNacimiento = 1991;
  e1.reporte();
}

class Estudiante {
  String? nombre = "";
  int? aNacimiento;

  void reporte() {
    print("Nombre: ${nombre}");
    print("Edad: ${2023 - aNacimiento!}");
  }
}
```

### Diagramas de clase #2:

![](2.jpg)

### Codigo #2:

#### main:
```dart
import 'Animal.dart';

void main(List<String> args) {
  Animal perro = Animal("Jorge", "Pasame la tarea");
  perro.reporte(perro);
  Animal gata = Animal("Emi", "pobre");
  perro.reporte(gata);
  Animal pato = Animal("Benavides", "Juego lol");
  perro.reporte(pato);
}

```
#### clase Animal:

```dart
class Animal {
  String? name;
  String? sonido;

  Animal(String name, String sonido) {
    this.name = name;
    this.sonido = sonido;
  }

  void reporte(Animal a) {
    print("Nombre: ${a.name}");
    print("Sonido: ${a.sonido}");
  }
}
```

### Diagramas de clase #3:

![](3.jpg)

### Codigo #3:

#### main:
```dart
import 'Dias.dart';

void main(List<String> args) {
  Dias d1 = new Dias("Miércoles", 31, "Mayo");
  d1.calcula(2023);
}
```
#### class Días:
```dart
class Dias {
  String? dia;
  int? numeroDia;
  String? mes;
  Dias(String dia, int numeroDia, String mes) {
    this.dia = dia;
    this.numeroDia = numeroDia;
    this.mes = mes;
  }

  void calcula(int mesActual) {
    print("Hoy es $dia $numeroDia del mes de $mes del $mesActual");
  }
}
```

### Diagramas de clase #4:

![](4.jpg)

### Codigo #4:

#### main:
```dart
import 'Figura.dart';

void main(List<String> args) {
  Figura rectangulo1 = new Figura.rectangulo(3, 12);
  Figura cuadrado1 = new Figura.cuadrado(4);
  print("El area del rectangulo es: ${rectangulo1.areaRectangulo()}");
  print("El perimetro del rectangulo es: ${rectangulo1.perimetroRectangulo()}");
  print("El area del cuadrado es: ${cuadrado1.areaCuadrado()}");
  print("El perimetro del cuadrado es: ${cuadrado1.perimetroCuadrado()}");
}

```

#### clase Figura:
```dart
class Figura {
  int? base;
  int? altura;

  Figura.rectangulo(this.base, this.altura);

  Figura.cuadrado(int base) {
    this.base = base;
  }
  int areaRectangulo() {
    if (altura == null || base == null) {
      print("No sepuede ejecutar");
      return 0;
    }
    return base! * altura!;
  }

  int areaCuadrado() {
    int res = 0;
    if (base == null) {
      print("No se puede ejcutar");
      return 0;
    }
    return res;
  }

  int perimetroRectangulo() {
    return (base! * altura!) * 2;
  }

  int perimetroCuadrado() {
    return (base! * 4);
  }
}
```

### Diagramas de clase #5:

![](6.jpg)

### Codigo #5:

#### main:
```dart
import 'Vehiculo.dart';

void main(List<String> args) {
  Vehiculo v1 = Vehiculo('TOYOTA', 2023, 'ROJO', 'AUTOMATICO');
  Vehiculo v2 = Vehiculo('BOCHO', 1900, 'BLANCO', 'ESTANDAR');
  /* v1.carro();
  v2.carro(); */
  List<Vehiculo> vehiculos = [v1, v2];
  //for(var carros in vehiculos);
  vehiculos.forEach((carro) => carro.carro());
}
```

#### clase Vehiculo:
```dart
class Vehiculo {
  String? _marca;
  int? _modelo;
  String? _color;
  String? _transmicion;

  Vehiculo(this._marca, this._modelo, this._color, this._transmicion);

  void carro() {
    print(
        ' marca: ${_marca} \n color:${_color} \n transmicion: ${_transmicion} \n modelo:${_modelo} \n');
  }

  void set marca(String marca) => this._marca = marca;
  void set modelo(int modelo) => this._modelo = modelo;
  void set color(String color) => this._color = color;
  void set transmicion(String transmicion) => this._transmicion = transmicion;

  String get marca => this.marca;
  int get modelo => this.modelo;
  String get color => this.color;
  String get transmicion => this.transmicion;
}
```

### Diagramas de clase #6:

![](5.jpg)

### Codigo #6:

#### main:
```dart
import 'Shape.dart';

void main(List<String> args) {
  Shape f1 = Shape(10, 8);
  print(f1.getArea());

  f1.base = 2;
  f1.altura = 2;

  print(f1.getArea());
  print('''   el area es: ${f1.base}  
    y la altura es: ${f1.altura}
    ''');
}
```

#### clase Shape:
```dart
class Shape {
  int? _base;
  int? _altura;

  Shape(this._base, this._altura);

  int getArea() {
    return _calculadoraArea();
  }

  int _calculadoraArea() {
    return _base! * _altura!;
  }

  void set base(int? base) => _base = base;
  void set altura(int? altura) => _altura = altura;

  int? get base => _base;
  int? get altura => _altura;
}
```

### Diagramas de clase #7:

![](7.jpg)

### Codigo #7:

#### main:
```dart
import 'Animal.dart';

void main(List<String> args) {
  Animal a1 = Animal('vaca', 10);
  a1.instancia();
  Animal.instanciaStatic();
  print('-' * 20);
  Animal a2 = Animal('CERDO', 20);
  a2.instancia();
  Animal.instanciaStatic();
  Animal a3 = Animal('vaca', 10);
  a3.instancia();
  Animal.instanciaStatic();
  print('-' * 20);
  List<Animal> animales = [a1, a2, a3];
  int suma = 0;
  animales.forEach((element) {
    suma += element.cantidad;
  });
  print('total de animales: $suma');
}
```

#### clase Animal:
```dart
class Animal {
  String tipoAnimal;
  int cantidad;
  static int cantidadS = 0;

  Animal(this.tipoAnimal, this.cantidad) {
    cantidadS++;
  }
  void instancia() {
    print('el animal es: $tipoAnimal');
    print('la cantidad es: $cantidad');
  }

  static void instanciaStatic() {
    print('la cantidad es:$cantidadS');
  }
}

```

### Diagramas de clase #8:

![](8.jpg)

### Codigo #8:

#### main:
```dart
import 'caballo.dart';
import 'pato.dart';
import 'animal.dart';
import 'vaca.dart';

void main(List<String> args) {
  Animal a1 = Animal('animal', 100);
  a1.showPropiedades();
  print('-' * 20);
  a1.quantity = 1000;
  a1.showPropiedades();
  print('°' * 20);
  Pato pato1 = Pato('pekines', 10, 'curvo');
  pato1.showPropiedades();
  print('-' * 20);
  pato1.quantity = 100;
  pato1.showPropiedades();
  print('°' * 20);
  Vaca vaca1 = Vaca('suiza', 20, 'negro');
  vaca1.showPropiedades();
  print('-' * 20);
  vaca1.quantity = 100;
  vaca1.showPropiedades();
  print('°' * 20);
  Caballo caballo1 = Caballo('frision', 30, 'larga');
  caballo1.showPropiedades();
  print('-' * 20);
  caballo1.quantity = 100;
  caballo1.showPropiedades();
}

```

#### clase Padre Animal:
```dart
class Animal {
  String? _breed;
  int? _quantity;
  Animal(this._breed, this._quantity);

  String? get breed => _breed;
  int? get quantity => _quantity;
  set breed(String? breed) => _breed = breed;
  set quantity(int? quantity) => _quantity = quantity;

  void showPropiedades() {
    print('breed: $_breed');
    print('quantity: $_quantity');
  }
}

```

#### clase Vaca:
```dart
import 'animal.dart';

class Vaca extends Animal {
  String? _color_manchas;
  Vaca(super._breed, super._quantity, this._color_manchas);

  @override
  void showPropiedades() {
    super.showPropiedades();
    print('colr manchas: $_color_manchas');
  }
}
```

#### clase Caballo:
```dart
import 'animal.dart';

class Caballo extends Animal {
  String? _melena;
  Caballo(super._breed, super._quantity, this._melena);

  @override
  void showPropiedades() {
    super.showPropiedades();

    print('melena: $_melena');
  }
}

```

#### clase Pato:
```dart
import 'animal.dart';

class Pato extends Animal {
  String? _tipoPico;
  Pato(super._breed, super._quantity, this._tipoPico);

  @override
  void showPropiedades() {
    super.showPropiedades();
    print('tipoPico: $_tipoPico');
  }
}
```

### Diagramas de clase #9:

![](9.jpg)

### Codigo #9:

#### main:
```dart

void main(List<String> args) {
  Vehiculo v1 = Vehiculo('rojo', 100);
  v1.showVehicle();
  print('maxima velocidad: ${v1.maxVelocidad()}');

  Carro c1 = Carro('azul', 200, 'toyota');
  c1.showVehicle();
  print('-------');
  print('maxima velocidad : ${c1.maxVelocidad}');
  
  Carro carroTipo = Carro.tipo('azul', 200, 'toyota', 'sedan');
  carroTipo.showTipo();
  print('maxima velocidad: ${carroTipo.maxVelocidad()}');
  print('----------------');
  carroTipo.showTipo2();
  print('maxima velocidad: ${carroTipo.maxVelocidad()}');
}

class Vehiculo{
  String? _color;
  int? _velocidad;
  Vehiculo(this._color,this._velocidad){
    print('constructor padre vehiculo');
  }
  set color(String? color) => this._color = color;
  set velocidad(int? velocidad) => this._velocidad = velocidad;
  
  String? get color => _color;
  int? get velocidad => _velocidad;
  
  int maxVelocidad() => _velocidad! * 2;

  void showVehicle(){
    print('color: $_color');
    print('velocidad: $_velocidad');
  }
}

class Carro extends Vehiculo{
  String? _marca;
  String? _tipo;

  Carro(super._color, super._velocidad, this._marca){
    print('constructor hijo carro');
  }

  Carro.tipo(super._color, super._velocidad, this._marca, this._tipo){
    print('constructor nombrado tipo hijo carro');
  }
  @override
  void showVehicle(){
    super.showVehicle();
    print('marca: $_marca');
  }

  void showTipo(){
    super.showVehicle();
    print('marca: $_marca');
    print('tipo: $_tipo');
  }

  void showTipo2(){
    this.showVehicle();
    print('tipo: $_tipo');
      }
  }
```

#### clase Abstract:
```dart
void main(List<String> args) {
  final Carro jeep = Carro('rojo', 100, 'jeep', 'suv');
  jeep.showVehiculo();
  jeep.maxVelocidad();

  final Motocicleta yamaha = Motocicleta('rosita', 160, 'r6');
  yamaha.showVehiculo();
  yamaha.maxVelocidad();
}
abstract class Vehiculo{
  String? _color;
  int? _velocidad;

  Vehiculo(this._color, this._velocidad){
    print('constructor padre vehiculo');
  }
    set color(String? color) => this._color = color;
  set velocidad(int? velocidad) => this._velocidad = velocidad;
  
  String? get color => _color;
  int? get velocidad => _velocidad;

  int maxVelocidad() => _velocidad! * 2;

  void showVehiculo(){
    print('color: $_color');
    print('velocidad: $_velocidad');
  }
}

class Carro extends Vehiculo{
  String? _marca;
  String? _tipo;

  Carro(super._color, super._velocidad, this._marca, this._tipo){
    print('constructor hijo carro');
  }
  @override
  void showVehiculo(){
    super.showVehiculo();
    print('marca: $_marca');
    print('tipo: $_tipo');
  }
}

class Motocicleta extends Vehiculo{
  String? _marca;
  
  Motocicleta(super._color, super._velocidad, this._marca){
    print('constructor hijo Motocicleta');
  }

  @override
  void showVehiculo() {
    super.showVehiculo();
    print('marca: $_marca');
  }
}
```

### Diagramas de clase #10:

![](10.jpg)

### Codigo #10:

#### main (mixins):
```dart
void main(List<String> args) {
  Dolphin flippy = Dolphin();
  flippy.swim();
}
class Animal{
  Animal(){
  print('ANIMAL CONSTRUCTOR');
  }
}
class Mammal extends Animal{
  Mammal(){
    print('mammal constructor');
  }
}

class Bird extends Animal{
  Bird(){
    print('bird constructor');
  }
}

class Fish extends Animal{
  Fish(){
    print('fish constructor');
  }
}

abstract class Swimmer{
  void swim(){
    print('swimming');
  }
}

class Dolphin extends Mammal with Swimmer{
  Dolphin(){
    print('Dolphin constructor');
  }
}
```
