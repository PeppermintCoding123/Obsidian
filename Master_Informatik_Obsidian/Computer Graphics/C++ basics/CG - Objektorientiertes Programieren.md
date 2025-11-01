# Klassen
```c++
class Klassenname {
public:
	// Daten- und Methodendeklarationen
	// Zugreifbar von allen Objekten
protected:
	// Daten- und Methodendeklarationen
	// Wie private, jedoch dürfen auch alle Unterklassen zugreifen
private:
	// Daten- und Methodendeklarationen
	// Nur innerhalb der Klasse zugreifbar
}; // niemals den ; vergessen
```
Beispiel: Complex.cpp
```c++
class Complex {
private:
	float m_real;
	float m_imag;
public:
	Complex(float r, float i) : m_real(r), m_imag(i) { }
	~Complex() { }
	void inc() { m_real += 1.0f; }
};```
- methoden in Klassen

# Methoden
- zugriff auf private daten in Klasse
- `void inc() { m_real += 1.0f; }`

## Konstruktor
```c++
class Complex {
private:
	float m_real;
	float m_imag;
public:
	Complex(float r, float i) { m_real = r; m_imag = i; } // Das ist der Konstructor
	~Complex() { }
	void inc() { m_real += 1.0f; }
};
```
- bei initialisierung
- Parameterübergabe
- Werte von nicht-initialisiserten Variable = random

Lieber 
`Complex(float r, float i) { m_real = r; m_imag = i; }`
statt
`Complex(float r , float i) : m_real(r), m_imag(i) { }`

## Destruktor
called directly before deleting object - free resources
`~Complex() { }`

## Accessor
methods that do **not** change properties of object
- need **const**
```c
float getReal() const {
	return m_real;
}
```
- Wichtig für getter & setter
## Mutators
change properties of object
```c
void setReal(float real) {
	m_real = real;
}
```

## Deklaration
$f: \mathbb{R}\rightarrow \mathbb{R}_0^+$
- in .h file
```c
class Complex {
private:
	float m_real;
	float m_imag;
public:
	Complex(float r, float i);
	~Complex();
	void inc(); // this is the declaration
};
```
## Definition
$f(x) = x^2$
- in .cpp file
- outside class declaration
```c
#include "Complex.h"
Complex::Complex(float r, float i) :
	m_real(r),
	m_imag(i)
	{ }

Complex::~Complex() { }
void Complex::inc() { // this is the definition
	m_real += 1.0f;
}
```

inline definition:
```c
class Complex {
private:
	float m_real;
	float m_imag;
public:
	Complex(float r, float i) {}
	~Complex() {}
	void inc() { m_real += 1.0f; } // this
};
```

## Macro
- `#ifndef ... #define ... #endif)`

## Instance
Stack:
```c++
#include "Complex.h"
void doSomething() {
	Complex a(1.0f, 2.0f); //create object
	a.setImag(1.0f);
} // end of a -> destructor
```

Heap:
```c++
#include "Complex.h"
void doSomething() {
	Complex *a = new Complex(1.0f, 2.0f); // new calls a constructor, malloc dose not
	a->setImag(1.0f);
	delete a; // calls a destructor, free dose not
}
```

## Call by value & Call by reference

```c++
#include <iostream>
using namespace std;
void swap_by_Value(int x, int y) {
	int temp = x;
	x = y;
	y = temp;
} // only in this section

void swap_by_Reference(int &x, int &y) {
	int temp = x;
	x = y;
	y = temp;
} // swap refferance numbers forever

// alternative
void swap_by_Reference(int *x, int *y) {
	int temp;
	temp = *x;
	*x = *y;
	*y = temp;
}
```

## Namespaces
```c++
namespace myTool1 {
	int mult(int a, int b) {
		int ret = 0;
		for (int i = 0; i < b; i++)
			ret += a;
	return ret;
	};
}

// other
namespace myTool2 {
	int mult(int a, int b) {
		return a * b;
	};
}

// use
int main() {
	int a = myTool1::mult(4, 3);
	int b = myTool2::mult(5, 2);
	return 0;
}
```
isostream & declare overall for all
```c++
#include<iostream>
using namespace std;

int main() {
	cout << "Hello World" << endl; // this instead of
	return 0;
}

std::cout << "Hello World" << std::endl; // basic appraoch

// isolated sectoins
#include<iostream>
#include<string>
 
usingusingstd::cout;
std::cerr;

int main() {
	std::string s = “Namespaces sind toll!“;
	cout << “Geht auch einzeln“;
	cerr << “Oder auch auf Standard-Error“;
}

```

## Vererbung
```c++
class X : public XSuperClass { ... };
```
![[Pasted image 20251016110847.png]]

## Virtuelle Methods - final
- explicite binding if dynamic

```c++
// definitions
class Counter {
	void incr() { value++; } // this is final, unsess declared virtual
};

class BinCounter : public Counter {
	void incr() { value += 2; }
};

// usage
Counter *c = new BinCounter(0); // Zulässig, da Counter Superklasse von BinCounter
c->incr(); // FALSCH, erhöht Zähler nur um 1, NICHT um 2
 
 
// Virtual = opposite of final
class Counter {
	virtual void incr(){ ... };
};

// abstract = pute virtual
virtual void incr() = 0;
```

## Überladen
```c++
int main(){
	int i = 5; // value is 5
	++i;
	// now value is 6
}
```
page 73 & further
## Templates
#TODO Die Aufgaben ausprobieren