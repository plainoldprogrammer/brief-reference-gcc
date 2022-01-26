# Brief reference GCC
Brief reference of the GNU Compiler Collection.

---

#### Compile to C++ 11
```
> g++ -std=c++11 main.cpp -o program
```

#### Save the preprocessor output file
```
> g++ -E main.cpp -o main.ii
````

#### Compile a library
```
> g++ -c library.cpp

NOTE 1: Need the .h file and the .cpp file.

NOTE 2: This will generate a library.o file.
```

#### Compile a program and link to an object file
```
> g++ -o program.exe main.cpp library.o

NOTE 1: Need the header file (.h) and the object file (.o) file.

NOTE 2: Dont need the .cpp file.
```

#### Compile a program and a library
```
> g++ -o program.exe main.cpp library.cpp
```

#### Compile a program and link to a library
```
> g++ -o program.exe main.cpp library.a

NOTE 1: Need the header file (.h) file and the library (.a).

NOTE 2: Dont need the .cpp file.
```

#### Create a library from an object file
```
> ar rcs library.a library.o

NOTE: The library that will be generated is the .a file.
```

#### Compile code with symbolic debugging information
```
> g++ -g main.cpp
```

#### Compile and link with allegro library (debug)
```
> g++ -Wall -fexceptions -g -IC:\Users\Arturo\libs\allegro-5.0.10-mingw-4.7.0\include -c main.cpp -o main.o

> g++ -o program.exe main.o allegro-5.0.10-monolith-mt-debug.dll

NOTE:	Must provide the .dll file for linking and runtime.
```
