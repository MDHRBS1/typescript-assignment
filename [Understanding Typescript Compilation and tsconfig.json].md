Understanding Typescript Compilation and tsconfig.json
Introduction:
Typescript adds types to javascript. Since browsers and Node.js usually excute javascript, Typescript cose is commonly compiled before it runs.

Explanation:
The Typescript compiler, called tsc, converts Typescript files (.ts) into javascript file (.js). During compilation, it checks the code for type errors according to the projects settings.

Example:
ts code 
let username; string = "programming hero";
console.log(username);

The compiler removes the type annotation and produces javascript similar to this
js code 
let username = "programming hero";
console.log(username);

If we assign a number to a variable declared as string, the compilar reports atype error. This helps developers find mistackes before running the program.The tsconfig.json file controls how the compiler works. It can specify the source folder, output folder,javascript version,module system and type checking rules.
"Json"
{
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist",
    "module": "esnext",
    "target": "esnext",
    "types": [],
    "strict": true,
    "skipLibCheck": true
  }
}
here, rootDir identifies the source directory, while outDir specifies where compiled javascript files are saved.The strict option enables stronger checking.

Conclusion:
The tsc compiler checks and transforms typecript into javascript. The tsconfig.json file stores project wide compiler settings, helping developers compile code consistenly.
