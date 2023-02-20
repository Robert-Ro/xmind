# TypeScript Config

Specifies the root files and the compiler options required to the project. JavaScript projects can use a jsconfig.json file instead.


## CompileOptions

### allowJs

Allow JavaScript files to be imported inside your project, instead of just .ts and .tsx files.


- type: boolean
- default: false

### checkJs

Works in tandem with allowJs. When checkJs is enabled then errors are reported in JavaScript files. This is the equivalent of including // @ts-check at the top of all JavaScript files which are included in your project.


- type: boolean
- default: false

### composite

### declaration

Generate .d.ts files for every TypeScript or JavaScript file inside your project. These .d.ts files are type definition files which describe the external API of your module. With .d.ts files, tools like TypeScript can provide intellisense and accurate types for un-typed code.


- type: boolean
- default: false

### declarationMap

Generates a source map for .d.ts files which map back to the original .ts source file. This will allow editors such as VS Code to go to the original .ts file when using features like Go to Definition.
You should strongly consider turning this on if you’re using project references.



- type: boolean
- default: false

### downlevelIteration

Downleveling is TypeScript’s term for transpiling to an older version of JavaScript. This flag is to enable support for a more accurate implementation of how modern JavaScript iterates through new concepts in older JavaScript runtimes.

ECMAScript 6 added several new iteration primitives: the for / of loop (for (el of arr)), Array spread ([a, ...b]), argument spread (fn(...args)), and Symbol.iterator. --downlevelIteration allows for these iteration primitives to be used more accurately in ES5 environments if a Symbol.iterator implementation is present.



- type: boolean
- default: false

### importHelpers

For certain downleveling operations, TypeScript uses some helper code for operations like extending class, spreading arrays or objects, and async operations. By default, these helpers are inserted into files which use them. This can result in code duplication if the same helper is used in many different modules.
If the importHelpers flag is on, these helper functions are instead imported from the tslib module. You will need to ensure that the tslib module is able to be imported at runtime. This only affects modules; global script files will not attempt to import modules.



### incremental

Tells TypeScript to save information about the project graph from the last compilation to files stored on disk. This creates a series of .tsbuildinfo files in the same folder as your compilation output. They are not used by your JavaScript at runtime and can be safely deleted. You can read more about the flag in the 3.4 release notes.


### isolatedModules

While you can use TypeScript to produce JavaScript code from TypeScript code, it’s also common to use other transpilers such as Babel to do this. However, other transpilers only operate on a single file at a time, which means they can’t apply code transforms that depend on understanding the full type system. This restriction also applies to TypeScript’s ts.transpileModule API which is used by some build tools.
These limitations can cause runtime problems with some TypeScript features like const enums and namespaces. Setting the isolatedModules flag tells TypeScript to warn you if you write certain code that can’t be correctly interpreted by a single-file transpilation process.
It does not change the behavior of your code, or otherwise change the behavior of TypeScript’s checking and emitting process.



### jsx

Controls how JSX constructs are emitted in JavaScript files. This only affects output of JS files that started in .tsx files.
react: Emit .js files with JSX changed to the equivalent React.createElement calls
react-jsx: Emit .js files with the JSX changed to _jsx calls
react-jsxdev: Emit .js files with the JSX to _jsx calls
preserve: Emit .jsx files with the JSX unchanged
react-native: Emit .js files with the JSX unchanged


### lib

TypeScript includes a default set of type definitions for built-in JS APIs (like Math), as well as type definitions for things found in browser environments (like document). TypeScript also includes APIs for newer JS features matching the target you specify; for example the definition for Map is available if target is ES6 or newer.

You may want to change these for a few reasons:
Your program doesn’t run in a browser, so you don’t want the "dom" type definitions
Your runtime platform provides certain JavaScript API objects (maybe through polyfills), but doesn’t yet support the full syntax of a given ECMAScript version
You have polyfills or native implementations for some, but not all, of a higher level ECMAScript version
@reference: https://github.com/microsoft/TypeScript/tree/main/lib


### module

Sets the module system for the program. See the Modules reference page for more information. You very likely want "CommonJS" for node projects.
Changing module affects moduleResolution which also has a reference page.
If you are wondering about the difference between ES2015 and ES2020, ES2020 adds support for dynamic imports, and import.meta.
dynamics imports: Dynamic import() introduces a new function-like form of import that unlocks new capabilities compared to static import. 
import.meta: The import.meta object exposes context-specific metadata to a JavaScript module. It contains information about the module, like the module's URL.


### noEmit

Do not emit compiler output files like JavaScript source code, source-maps or declarations.
This makes room for another tool like Babel, or swc to handle converting the TypeScript file to a file which can run inside a JavaScript environment.
You can then use TypeScript as a tool for providing editor integration, and as a source code type-checker.



### outDir

If specified, .js (as well as .d.ts, .js.map, etc.) files will be emitted into this directory. The directory structure of the original source files is preserved; see rootDir if the computed root is not what you intended.
If not specified, .js files will be emitted in the same directory as the .ts files they were generated from:



### outFile

If specified, all global (non-module) files will be concatenated into the single output file specified.
If module is system or amd, all module files will also be concatenated into this file after all global content.
Note: outFile cannot be used unless module is None, System, or AMD. This option cannot be used to bundle CommonJS or ES6 modules.



### plugins

List of language service plugins to run inside the editor.
Language service plugins are a way to provide additional information to a user based on existing TypeScript files. They can enhance existing messages between TypeScript and an editor, or to provide their own error messages.



### removeComments

Strips all comments from TypeScript files when converting into JavaScript. Defaults to false.
For example, this is a TypeScript file which has a JSDoc comment:



### rootDir

Default: The longest common path of all non-declaration input files. If composite is set, the default is instead the directory containing the tsconfig.json file.
When TypeScript compiles files, it keeps the same directory structure in the output directory as exists in the input directory.
Importantly, rootDir does not affect which files become part of the compilation. It has no interaction with the include, exclude, or files tsconfig.json settings.
Note that TypeScript will never write an output file to a directory outside of outDir, and will never skip emitting a file. For this reason, rootDir also enforces that all files which need to be emitted are underneath the rootDir path.



### sourceMap

Enables the generation of sourcemap files. These files allow debuggers and other tools to display the original TypeScript source code when actually working with the emitted JavaScript files. Source map files are emitted as .js.map (or .jsx.map) files next to the corresponding .js output file.


### target

Modern browsers support all ES6 features, so ES6 is a good choice. You might choose to set a lower target if your code is deployed to older environments, or a higher target if your code is guaranteed to run in newer environments.

Work with Babel or just compile with babel


### tsBuildInfoFile

This setting lets you specify a file for storing incremental compilation information as a part of composite projects which enables faster building of larger TypeScript codebases. You can read more about composite projects in the handbook.
This option offers a way to configure the place where TypeScript keeps track of the files it stores on the disk to indicate a project’s build state — by default, they are in the same folder as your emitted JavaScript.



### alwaysStrict

### noImplicitAny

### noImplicitThis

### strict

### strictBindCallApply

### strictFunctionTypes

### strictNullChecks

### strictPropertyInitialization

### allowSyntheticDefaultImports

### allowUmdGlobalAccess

### baseUrl

Lets you set a base directory to resolve non-absolute module names.


### esModuleInterop

- recommend: true

### moduleResolution

Specify the module resolution strategy: 'node' (Node.js) or 'classic' (used in TypeScript before the release of 1.6). You probably won’t need to use classic in modern code.


### paths

A series of entries which re-map imports to lookup locations relative to the baseUrl, there is a larger coverage of paths in the handbook.


### preserveSymlinks

### rootDirs

Using rootDirs, you can inform the compiler that there are many “virtual” directories acting as a single root. This allows the compiler to resolve relative module imports within these “virtual” directories, as if they were merged in to one directory.


### typeRoots

By default all visible ”@types” packages are included in your compilation. Packages in node_modules/@types of any enclosing folder are considered visible. For example, that means packages within ./node_modules/@types/, ../node_modules/@types/, ../../node_modules/@types/, and so on.
If typeRoots is specified, only packages under typeRoots will be included.



### types

By default all visible ”@types” packages are included in your compilation. Packages in node_modules/@types of any enclosing folder are considered visible. For example, that means packages within ./node_modules/@types/, ../node_modules/@types/, ../../node_modules/@types/, and so on.
If types is specified, only packages listed will be included in the global scope.



### inlineSourceMap

### inlineSources

### mapRoot

### sourceRoot

### noFallthroughCasesInSwitch

### noImplicitOverride

### noImplicitReturns

### noPropertyAccessFromIndexSignature

### noUncheckedIndexedAccess

### noUnusedLocals

### oUnusedParameters

### emitDecoratorMetadata

### experimentalDecorators

### allowUnreachableCode

### allowUnusedLabels

### assumeChangesOnlyAffectDirectDependencies

### charset

### declarationDir

### diagnostics

### disableReferencedProjectLoad

### disableSizeLimit

### disableSolutionSearching

### disableSourceOfProjectReferenceRedirect

### emitBOM

### emitDeclarationOnly

### explainFiles

### extendedDiagnostics

### forceConsistentCasingInFileNames

### generateCpuProfile

### importsNotUsedAsValues

### jsxFactory

### jsxFragmentFactory

### jsxImportSource

### keyofStringsOnly

### listEmittedFiles

### listFiles

### maxNodeModuleJsDepth

### newLine

### noEmitHelpers

### noEmitOnError

### noErrorTruncation

### noImplicitUseStrict

### noLib

### noResolve

### noStrictGenericChecks

### out

### preserveConstEnums

### reactNamespace

### resolveJsonModule

### skipDefaultLibCheck

### skipLibCheck

### stripInternal

### suppressExcessPropertyErrors

### suppressImplicitAnyIndexErrors

### traceResolution

### useDefineForClassFields

### preserveWatchOutput

### pretty

## include

Specifies an array of filenames or patterns to include in the program. These filenames are resolved relative to the directory containing the tsconfig.json file.
include and exclude support wildcard characters to make glob patterns:
* matches zero or more characters (excluding directory separators)
? matches any one character (excluding directory separators)
**/ matches any directory nested to any level
If a glob pattern doesn’t include a file extension, then only files with supported extensions are included (e.g. .ts, .tsx, and .d.ts by default, with .js and .jsx if allowJs is set to true).


### type: string[]

## exclude

Specifies an array of filenames or patterns that should be skipped when resolving include.
Important: exclude only changes which files are included as a result of the include setting. A file specified by exclude can still become part of your codebase due to an import statement in your code, a types inclusion, a /// <reference directive, or being specified in the files list.
It is not a mechanism that prevents a file from being included in the codebase - it simply changes what the include setting finds.



### type: string[]

## files

Specifies an allowlist of files to include in the program. An error occurs if any of the files can’t be found.

This is useful when you only have a small number of files and don’t need to use a glob to reference many files. If you need that then use include.


### type: string[]

## compileOnSave

### type: boolean

## typeAcquistion

Type Acquisition is only important for JavaScript projects. In TypeScript projects you need to include the types in your projects explicitly. However, for JavaScript projects, the TypeScript tooling will download types for your modules in the background and outside of your node_modules folder.


## ts-node

options for lib ts-node
[ts-node](https://github.com/TypeStrong/ts-node)


### compiler

Specify a custom TypeScript compiler. default: 'typescript'


- type: strimg

### compilerHost

Use TypeScript's compiler host API instead of the language service API.


- type: boolean

### compilerOptions

JSON object to merge with TypeScript compilerOptions


- type: object

### emit

Emit output files into .ts-node directory.
default: false


- type; boolean

### files


Load "files" and "include" from tsconfig.json on startup.

Default is to override tsconfig.json "files" and "include" to only include the entrypoint script.



- type: boolean

### ignore


Paths which should not be compiled.
Each string in the array is converted to a regular expression via new RegExp() and tested against source paths prior to compilation.
Source paths are normalized to posix-style separators, relative to the directory containing tsconfig.json or to cwd if no tsconfig.json is loaded.
Default is to ignore all node_modules subdirectories.
defalut: ["(?:^|/)node_modules/"]


- type: string[]

### ignoreDiagnostics

Ignore TypeScript warnings by diagnostic code.



- type: (string | number)[]

### logError

Logs TypeScript errors to stderr instead of throwing exceptions.
default: false


- type: boolean

### preferTsExts

Re-order file extensions so that TypeScript imports are preferred.
For example, when both index.js and index.ts exist, enabling this option causes require('./index') to resolve to index.ts instead of index.js
default: false


- type: boolean

### pretty

Use pretty diagnostic formatter.
default: false




- type: boolean

### require

Modules to require, like node's --require flag.
If specified in tsconfig.json, the modules will be resolved relative to the tsconfig.json file.
If specified programmatically, each input string should be pre-resolved to an absolute path for best results.


- type: string[]

### skipIgnore

Skip ignore check, so that compilation will be attempted for all files with matching extensions.
default: false


- type: boolean

### transpileOnly

Use TypeScript's faster transpileModule.
default: false


- type: boolean

### transpiler

Specify a custom transpiler for use with transpileOnly



- type: string | [string, object]

## extends

The value of extends is a string which contains a path to another configuration file to inherit from. The path may use Node.js style resolution.
The configuration from the base file are loaded first, then overridden by those in the inheriting config file. All relative paths found in the configuration file will be resolved relative to the configuration file they originated in.
It’s worth noting that files, include and exclude from the inheriting config file overwrite those from the base config file, and that circularity between configuration files is not allowed.


Currently, the only top-level property that is excluded from inheritance is references.



## references

Project references are a way to structure your TypeScript programs into smaller pieces. Using Project References can greatly improve build and editor interaction times, enforce logical separation between components, and organize your code in new and improved ways.


## WatchOptions

