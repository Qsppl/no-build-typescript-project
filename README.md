## How to use:

- Server
  - You can use this working environment in an HTTP server like NGinx/Apache by simply placing the project in the webroot of your server.
  - You can also use your IDE's LiveServer instead of an HTTP server (this behavior is enabled by default for VSCode).
- You must run the command
```Console
npm install
```
- All is ready.

## How it works?

> How does code linking work?

The project root is the same as the HTTP server root, so you can use 'ES6 import' to link the code.
The IDE will find matching files in the file system and display Intelephence/Typescript/JSDoc hints.
The browser will be able to receive files from these paths and display your site correctly without any linking of code and assembling it into bundles.

You can also move your source code to `/src`, `/web`, etc, but to do this you will need to change the basePath in .tsconfig so that the IDE will correctly read the new paths.

> How preprocessors work without Vite/webpack?

Typescript & ESLint & Prettier are executed by your IDE, with the built files (my-module.js) placed in the same place as the source code files (my-module.ts), so no path resolution is required.
Note that the built my-module.**js** file and the source code file my-module.**ts** have different file extensions.
However, the browser imports `.
ts` file will cause an error.
In order not to rewrite the paths, we initially write the paths to `.js` files, but the IDE understands that we mean the corresponding file with the `.ts` extension.
```TS
// my-second-module.ts
import { some } from "my-module.js"
```

## Example:
Here's how stackblitz opened this repository: https://stackblitz.com/~/github.com/Qsppl/no-build-typescript-project

No additional actions were required, it just works:

![stackblitz com_~_github com_Qsppl_no-build-typescript-project (1)](https://github.com/Qsppl/no-build-typescript-project/assets/22717464/00e88187-289b-40e3-b623-a8145eb129db)

Your project should also just work without any settings.
