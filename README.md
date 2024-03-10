# Entropy Calculator

This is a C++ project that calculates the entropy change of different elements in specified temparature difference.

## Project Structure

- `main.cpp`: The entry point of the application.
- `elements/`: This directory contains the definition of different elements.
- `headers/`: This directory contains the header files for the project.
- `bin/`: This directory contains the compiled binaries.
- `obj/`: This directory contains the object files generated during compilation.

## How to Build

### Code::Blocks

1. Open the `entropy-calculator.cbp` file in Code::Blocks.
2. Click on the "Build" button or select "Build" from the "Build" menu.

#### How to Run

After building the project, you can run the program by clicking on the "Run" button or selecting "Run" from the "Build" menu in Code::Blocks.

### Visual Studio Code

1. Open the project in Visual Studio Code.
2. Press `F5` to build the project.
3. It will create a `task.json` file in the `.vscode` directory.
4. Configure the `task.json` file to build the project like this one,

```cpp
{
    "tasks": [
        {
            "type": "cppbuild",
            "label": "C/C++: g++ build active file",
            "command": "/usr/bin/g++",
            "args": [
                "-fdiagnostics-color=always",
                "-g",
                "${file}",
                "./headers/allElements.cpp", // Add this line
                "-o",
                "${fileDirname}/${fileBasenameNoExtension}"
            ],
            "options": {
                "cwd": "${fileDirname}"
            },
            "problemMatcher": [
                "$gcc"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            },
            "detail": "Task generated by Debugger."
        }
    ],
    "version": "2.0.0"
}
```

And finally press `F5` again to build and run the project.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

### How to add a new element

1. Create a new file in the `elements/` directory with the name of the element (e.g. `water.h` for water element)
2. Define the element in the file. Declare a class with the name of the element which inherits from the `baseElement` class.
3. Write constructor and set the values of the properties of the element.

```cpp
// Example: water.h
#ifndef WATER_HPP_INCLUDED
#define WATER_HPP_INCLUDED
#include "../headers/baseElement.h"

class water : public baseElement
{
public:
    water()
    {
        setElementName("Water");
        setSpecificHeatLiquid(4184);
        setSpecificHeatSolid(2093);
        setSpecificHeatGas(2010);
        setLatentHeatOfFusion(334000);
        setLatentHeatOfVaporization(2260000);
        setMeltingPoint(273);
        setBoilingPoint(373);
    }
};
#endif // WATER_HPP_INCLUDED
```

4. Include the header file in the `allElements.cpp` file located in the `headers/` directory.

```cpp
// include new element's header file
#include "../elements/water.h"

// inside getElements() function, add the new element
// push the new element to the elements vector
elements.push_back(new water());
```

## Issues

If you find any issues with the project, please open an issue in the repository. [Click here to open an issue](https://github.com/sr-tamim/entropy-calculator/issues)

## License

[MIT](https://choosealicense.com/licenses/mit/)

## Author

[SR Tamim](https://sr-tamim.vercel.app)

[![sr-tamim's Profilator](https://profilator.deno.dev/sr-tamim?v=1.0.0.alpha.4)](https://github.com/sr-tamim)

## Contributors

[![sr-tamim's Profilator](https://profilator.deno.dev/sr-tamim?v=1.0.0.alpha.4)](https://github.com/sr-tamim)
[![SharafatKarim's Profilator](https://profilator.deno.dev/SharafatKarim?v=1.0.0.alpha.4)](https://github.com/SharafatKarim)
