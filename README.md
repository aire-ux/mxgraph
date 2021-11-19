# Aire-UX/MXGraph

[jgraph](https://github.com/jgraph/mxgraph) is no longer being maintained.  The Aire-UX project
relies on mxgraph, and this is its official fork. This project's goals are to:

1. Implement bug fixes
2. Support modern browser features as they appear
3. Provide TypeScript integration support [@aire-ux/mxgraph-typescript](https://github.com/aire-ux/typed-mxgraph)
4. Implement some new features as required

Additionally, this project will consider enterprise support contracts and bug-bounties.

## Installation

**NPM**
```
npm install @aire-ux/mxgraph
```

**Bower**
```
bower install @aire-ux/mxgraph
```


Once you have installed the project via your package-manager, you can consume it as follows:

```typescript

import '@aire-ux/mxgraph';

export type mxConfiguration = {
  mxLoadResources: boolean;
  mxForceIncludes: boolean;
  mxLoadStylesheets: boolean;
  mxResourceExtension: string;
  mxProductionMode: boolean;
  mxBasePath: string;
};

const factory = (cfg: Partial<mxConfiguration>) =>
  mxgraph({
    mxLoadResources: cfg.mxLoadResources || false,
    mxForceIncludes: cfg.mxForceIncludes || false,
    mxLoadStylesheets: cfg.mxLoadStylesheets || true,
    mxResourceExtension: cfg.mxResourceExtension || '.txt',
    mxProductionMode: cfg.mxProductionMode || true,
    mxBasePath: cfg.mxBasePath,
  });

export default factory;
```

```typescript

import factory from './mxgraph';

const mx = factory({
  mxBasePath: value,
});

const container = document.getElementById(`#my-container`);
const graph = new mx.mxGraph(container);
```


## TypeScript Definitions

Aire-UX maintains a fork of [typed-mxgraph](https://github.com/typed-mxgraph/typed-mxgraph) which may
be installed via `npm install @aire-ux/typed-mxgraph`.

It may be used as follows:

**tsconfig.json**
```json

{
  "compilerOptions": {
    "target": "es2018",
    "module": "esnext",
    "moduleResolution": "node",
    "noEmitOnError": true,
    "lib": ["es2017", "dom"],
    "strict": true,
    "esModuleInterop": true,
    "allowSyntheticDefaultImports": true,
    "experimentalDecorators": true,
    "strictPropertyInitialization": false,
    "importHelpers": true,
    "outDir": "dist",
    "sourceMap": true,
    "inlineSources": true,
    "rootDir": "./",
    "declaration": true,
    "incremental": true,
    "typeRoots": [
      "node_modules/@types"
    ]
  },
  "include": [
    "src/**/*.ts",
    "node_modules/@aire-ux/typed-mxgraph/**/*.d.ts" //include the typings
  ],
  "exclude": ["node_modules"]

}
```




Getting Started
===============

In the root folder there is an index.html file that contains links to all resources. You can view the documentation online on the [Github pages branch](https://jgraph.github.io/mxgraph/). The key resources are the JavaScript user manual, the JavaScript examples and the JavaScript API specificiation.

Support
=======

There is a [mxgraph tag on Stack Overflow](http://stackoverflow.com/questions/tagged/mxgraph). Please ensure your questions adhere to the [SO guidelines](http://stackoverflow.com/help/on-topic), otherwise it is likely to be closed.

