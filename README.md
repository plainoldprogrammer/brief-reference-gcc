# Brief reference GCC
Brief reference of the GNU Compiler Collection.

---

#### Some compiler options
```
-g			turn on debugging (so GDB gives more friendly output)
-Wall			turns on most warnings
-O or -O2		turn on optimizations
-o <name>		name of the output file
-c			output an object file (.o)
-I<include path>	specify an include directory
-L<library path>	specify a lib directory
-l<library>		link with library lib<library>.a
```

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

NOTE: Must provide the .dll file for linking and runtime.
```

#### Compile and link with allegro library (release)
```
> g++ -Wall -fexceptions -O2 -IC:\Users\Arturo\libs\allegro-5.0.10-mingw-4.7.0\include -c main.cpp -o main.o

> g++ -o snake.exe main.o  -s allegro-5.0.10-monolith-mt.dll

NOTE: Must provide the .dll file for linking and runtime.
```

#### Compile a OpenGL application using SFML (debug)
```
> g++ -Wall -fexceptions -std=c++14 -g -IC:\Users\Arturo\libs\SFML-2.5.1\include -c main.cpp -o main.o

> g++ -LC:\Users\Arturo\libs\SFML-2.5.1\lib -o program.exe main.o C:\Windows\System32\opengl32.dll sfml-graphics-d-2.dll sfml-audio-d-2.dll sfml-network-d-2.dll sfml-window-d-2.dll sfml-system-d-2.dll

NOTE 1: You must provide the following SFML files for linking:

			sfml-graphics-d-2.dll 
			sfml-audio-d-2.dll 
			sfml-network-d-2.dll 
			sfml-window-d-2.dll 
			sfml-system-d-2.dll

NOTE 2: Ensure that your system provide the OpenGL dll file at "C:\Windows\System32\opengl32.dll".

NOTE 3: Ensure the compiler compatibility.

NOTE 4: Ensure the compiler architecture compatibiliity with the lib.
```

#### Compile a OpenGL application using SFML (release)
```
> g++ -Wall -fexceptions -std=c++14 -g -IC:\Users\Arturo\libs\SFML-2.5.1\include -c main.cpp -o main.o

> g++ -LC:\Users\Arturo\libs\SFML-2.5.1\lib -o program.exe main.o C:\Windows\System32\opengl32.dll sfml-graphics-2.dll sfml-audio-2.dll sfml-network-2.dll sfml-window-2.dll sfml-system-2.dll

NOTE 1: You must provide the following SFML files for linking:

			sfml-graphics-2.dll
			sfml-audio-2.dll
			sfml-network-2.dll
			sfml-window-2.dll
			sfml-system-2.dll

NOTE 2:	Ensure that your system provide the OpenGL dll file at "C:\Windows\System32\opengl32.dll".

NOTE 3: Ensure the compiler compatibility.

NOTE 4: Ensure the compiler architecture compatibiliity with the lib.
```

#### Compile and link separately an OpenGL program
```
// Compile
> g++ -Wall -fexceptions -std=c++14 -g -IC:\Users\Arturo\libs\SFML-2.5.1\include -c main.cpp -o main.o

// Link
> g++ -LC:\Users\Arturo\libs\SFML-2.5.1\lib -o program.exe main.o C:\Windows\System32\opengl32.dll sfml-graphics-d-2.dll sfml-audio-d-2.dll sfml-network-d-2.dll sfml-window-d-2.dll sfml-system-d-2.dll -lopengl32

NOTE: Must prove the .dll files in the same directory of the source file at linking time.
```

#### Compile and link in the same step an OpenGL program
```
// Compile and Link
> g++ -IC:\Users\Arturo\libs\SFML-2.5.1\include -LC:\Users\Arturo\libs\SFML-2.5.1\lib -o program.exe main.cpp C:\Windows\System32\opengl32.dll sfml-graphics-d-2.dll sfml-audio-d-2.dll sfml-network-d-2.dll sfml-window-d-2.dll sfml-system-d-2.dll -lopengl32

NOTE: Must prove the .dll files in the same directory of the source file at linking time.
```

#### Compile and link statically an OpenGL program
````
> g++ -o program.exe main.cpp -DSFML_STATIC -IC:\Users\Arturo\libs\SFML-2.5.1\include -s -LC:\Users\Arturo\libs\SFML-2.5.1\lib c:\windows\system32\opengl32.dll  -lsfml-graphics-s-d -lfreetype -lsfml-window-s-d -lopengl32 -lgdi32 -lsfml-system-s-d -lw

NOTE: The -DSFML_STATIC is the most important flag here.
````
