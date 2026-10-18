# Community Modules & Component Architecture
 
Blueprint introduces a modular, component-based package architecture modeled after composable component patterns.
 
## Importing Community Modules
 
To import third-party or community libraries, use the path-based `@blueprint import modules/<libname>` annotation:
 
```blueprint
@blueprint import Blueprint
@blueprint import modules/mathlib
@blueprint import modules/shapes
```
 
## Package Layout
 
Every Blueprint library package lives under `modules/<libname>/` and follows this standard modular layout:
 
```text
modules/
└── shapes/
    ├── package.bls          # Package manifest (JSON metadata)
    ├── package.bl           # Main entry package file (exports & structs)
    └── functions/           # Individual component function files
        ├── calc_area.bl     # Component file for calc_area()
        └── draw_shape.bl    # Component file for draw_shape()
```
 
### 1. The Manifest (`package.bls`)
 
The `package.bls` file contains package metadata and a declaration of exported functions:
 
```json
{
  "name": "shapes",
  "version": "1.0.0",
  "author": "Community Dev",
  "functions": [
    "calc_area",
    "draw_shape"
  ]
}
```
 
### 2. The Main Package Entry (`package.bl`)
 
`package.bl` acts as the root entry point (similar to `index.js` in React/Node). It defines shared structures, initialization, or mappings:
 
```blueprint
defstruct ShapeInfo [
    sides: int,
    color: string
]

func DescribeShape(s: ShapeInfo): str [
    return "Shape with " + s.sides + " sides (" + s.color + ")"
]
```
 
### 3. Native Function Files (`functions/<function_name>.bl`)
 
Each function exported by the library can reside in its own native `.bl` file inside the `functions/` folder. For example, `functions/calc_area.bl`:
 
```blueprint
func calc_area(width: int, height: int): int [
    return width * height
]
```
 
And `functions/draw_shape.bl`:
 
```blueprint
@blueprint import AppToolkit

func draw_shape(x: int, y: int, size: int): void [
    draw_rect(x, y, size, size, 50, 150, 250)
]
```
 
## How the Compiler Resolves Packages
 
When compiling or running a project with `@blueprint import modules/<libname>`:
 1. The compiler locates `./modules/<libname>/`.
 2. Parses `package.bls` and `package.bl`, registering exposed structs and top-level functions.
 3. Automatically traverses and compiles each function file inside `functions/*.bl`.
 4. Combines the items seamlessly into your program's compilation unit with full type-safety and ARC memory management.
