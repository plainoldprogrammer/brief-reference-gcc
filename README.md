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
