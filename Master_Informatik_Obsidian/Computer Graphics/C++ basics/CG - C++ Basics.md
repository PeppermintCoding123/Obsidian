```c++
#include <iostream>
#include <cstdlib>
int main(int argc, char **argv) {
std::cout << “Hello World” << std::endl;
return EXIT_SUCCESS;
}
```

# Print
```c++
std::cout << Text << std::endl;
```
# Pointer
```c++
int *a; // Deklarieren
int b = 4;
int *a = &b; // Speicheradresse
std::cout << *a << std::endl; // Inhalt, nicht preicheradresse
```

## Null
```c++
int *a = nullptr;
```
Zum Kompilieren (g++) -std=c++11

# Referenzen
```c++
int a = 5, b = 3;
int &c = a; // c zeigt auf a
c = b; // Wert von a wird auf 3 geschrieben
int &d; // Compiler-Fehler! (uninitialisierte Referenz)
```
- immer auf festes Objekt zeigen
- sofort initialisiert
- harmloser :)

# Arrays
```c
#include <iostream>
int main() {
int b[3] = {1, 2, 3};
int *a = b;
std::cout << a[0] << “ “ << a[1] << “ “ << a[2] << std::endl;
std::cout << b << “\n”; // Version 1

std::cout << *a << “ “ << *(a + 1) << “ “ << *(a + 2) << “\n”; // gleiche ergebnis wie oben

std::cout << *a << “ ”;
a++;
std::cout << *a << “ ”;
a++;
std::cout << *a << “ ”; // Version 3
}
```
- nur pointer

# Speicherverwaltung (Stack)
```c
#include <iostream>
int main() {
	{
		int b[3]; //Hier wird Speicher am Stack angelegt
	}//Hier endet der Scope -> Speicher wird freigegeben
	
	int a = 4;
	if (a == 4) {
		int b[10]; //Hier wird Speicher am Stack angelegt
	} //Hier endet der Scope -> Speicher wird freigegeben
}
```

# Speicherverwaltung (Heap)
```c++
#include <iostream>
int main() {
	int *b = new int[100]; // Speicher anlegen
	delete[] b; // Speicher freigeben
	
	// dynamisch:
	int size;
	std::cin >> size;
	int *b = new int[size]; // Groesse erst zur Laufzeit bekannt!
	delete[] b;
	
 }
```
<span style="color:rgb(255, 0, 0)">Delete</span> ist super wichtig !!! -> sonst Memory Leak

new & delete, nicht malloc & free.

### Mehrdimensionale Arrays auf Heap
```c++
#include <iostream>
int main() {
	int **b = new int*[10]; // Legt ein Array von Pointern an
	for (int i = 0; i < 10; i++) {
		b[i] = new int[5];
	}
	// Jetzt liegt ein 10 x 5 Array im Speicher
	
	for (int i = 0; i < 10; i++) {
		delete[] b[i];
	}
	delete[] b;
```
Matrix auslesen: - (int \*matrix) ist 1-D aufgebaut 
```c++
// gibt Matrix(i, j) zurück
int getEntry(int *matrix, int width, int height, int i, int j);

int main() {
	int width = 5, height = 10;
	int *matrix = new int[width * height];
	
	...// do some stuff
	
	int value = getEntry(matrix, width, height, 2, 3);
	delete[] matrix;
}

int getEntry(int *matrix, int width, int height, int i, int j) {
	int idx = i * width + j;
	// Test, ob idx im gültigen Bereich (sonst Zugriffsfehler)
	return matrix[idx];
	
}
```

[[CG - Objektorientiertes Programieren]]