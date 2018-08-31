# TypeScript in Atom for Adobe CEP

## With **[Types-for-Adobe](https://github.com/pravdomil/Types-for-Adobe)** and **[Atom-Typescript](https://atom.io/packages/atom-typescript)**

![demo](https://thumbs.gfycat.com/ThoughtfulImpressiveGrasshopper-size_restricted.gif)

![](https://thumbs.gfycat.com/MilkyMessyAcaciarat-size_restricted.gif)

## Set up [Atom-Typescript](https://atom.io/packages/atom-typescript)

``` bash
# install Atom-TypeScript in Atom via Settings > Install > Atom-TypeScript

# or start here and follow directions from link above
apm install atom-typescript
```

## From-Scratch

[Pravdomil's YouTube tutorial](https://www.youtube.com/watch?v=h-c7A8pQzx8&feature=youtu.be&t=1m6s)

``` bash
# Create and enter directory
mkdir newTypeScript
cd newTypeScript

# Create package.json
npm init -y

# Get node_modules for Types-for-Adobe
npm install pravdomil/types-for-adobe
```

## Create a tsconfig for target app DOM
``` json
// pravdomil
{
  "compilerOptions": {
    "module": "commonjs",
    "noLib": true,
    "types": [
      // Folder reference for app from node_modules/types-for-adobe/...
      "types-for-adobe/illustrator/2015.3"
    ]
  },
  "exclude": [
    "node_modules"
  ]
}
```
``` json
// from Adobe-CEP/Samples
{
    "compilerOptions": {
        "allowJs": true,            // Allows JavaScript files to be compiled.
        "lib": [                    // Specifying "lib" overwrites defaults (stops import of HTML DOM stuff).
            "es5"
        ],
        "strict": true,             // Shorthand for the following four options:
        // "noImplicitAny": true,
        // "noImplicitThis": true,
        // "alwaysStrict": true,
        // "strictNullChecks": true,
        "target": "es3"             // In case TypeScript is used, this will compile to ECMAScript 3 (ExtendScript!) compatible code.
    }
}
```

## Test in local TypeScript file

``` TypeScript
// test.ts
app.selection
```
