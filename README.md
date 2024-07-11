# OpenComputers Lua Assembler Library

The OpenComputers Lua Assembler library (`Assembler`) provides a dynamic framework for executing commands with varying numbers of arguments within the OpenComputers mod environment. This module facilitates managing values, sectors, and hardware components programmatically.

## Features

- **Values Management**: Create, move, and manipulate values within the Lua environment.
- **Sector Operations**: Assign and retrieve values from predefined sectors (`ax`, `ex`, `as`, `es`).
- **Arithmetic Operations**: Perform addition and subtraction operations between values.
- **Component Integration**: Initialize and interact with hardware components using predefined functions.
- **Dynamic Function Execution**: Execute functions with a variable number of arguments.

## Installation

To use the Assembler library in your OpenComputers project, follow these steps:

1. **Download**: Clone the repository into your OpenComputers project directory:
   ```sh
   wget 
   ```

2. **Include**: Import the `Assembler.lua` module in your Lua script:
   ```lua
   local Asmv = require("asmv")
   ```

## Usage

### Example

Here is an example demonstrating how to use the Assembler library:

```lua
local Assembler = require("Assembler")

local code = [
   createvalue myVal 10
   move myVal anotherVal
   add myVal 5 resultVal
   runsectors
]

Assembler.RunCodeWithoutSandbox(code)
```

### Command Format

Each command in the code should follow this format:

```functionName arg1 arg2 ...```

- ```functionName```: The name of the function to execute.
- ```arg1```, `arg2```, ...: Arguments passed to the function.

### API Reference

#### Functions

- **createvalue(valName, valValue)**: Creates a new value with the specified name and initial value.
- **move(oldvalName, newvalName)**: Moves a value from `oldvalName` to `newvalName`.
- **movetosector(sectorName, val)**: Moves a value to a specified sector (`ax`, `ex`, `as`, `es`).
- **getfromsector(sectorname, valuename)**: Retrieves a value from a specified sector.
- **add(valuename, addtovalue, outvaluename)**: Adds `addtovalue` to `valuename` and stores the result in `outvaluename`.
- **minus(valuename, minusfromvalue, outvaluename)**: Subtracts `minusfromvalue` from `valuename` and stores the result in `outvaluename`.
- **runsectors()**: Executes operations related to sectors.
- **initcomponent(compoentnname)**: Initializes a component by its name for future use.
- **componentfunction1arg(componentval, arg1)**: Calls a function on a component with one argument.
- **componentfunction2arg(componentval, arg1, arg2)**: Calls a function on a component with two arguments.
- **deintcomponent(compoentnname)**: Removes a component from the system.

#### Error Handling

- Functions handle errors gracefully, providing informative messages about incorrect arguments, missing functions, and invalid code formats.

## Contributing

Contributions are welcome! Fork the repository and submit pull requests for any enhancements or bug fixes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Inspiration and initial concept from [Provide Attribution if Applicable]
