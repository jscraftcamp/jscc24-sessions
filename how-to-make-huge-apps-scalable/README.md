# How to make huge apps scalable?

When there are more and more devs on one project and codebase it is growing. Webpack bundling can take quite some time. Ran into out of memory. We are looking at Webpack Analyzer. We can use `--max-old-space-size=4096` to set memory.
We see in the Webpack Analyzer that one vendor package was bundled into two different huge JavaScript bundles. We talk about using Webpack (named) chunks to build an own chunk just for this vendor library. We don't think that this will be problem with Treeshaking.
We are always careful to not bundle any dev dependencies into the production build. But it can happen! For example importing a Mock into an app file, but it included jest or even faker. So checking the analytics stats is very helpful to detect these problems.
A pro tip is to use `(yarn) tsc --explainFiles -p tsconfig.json` . It can also be used to explain specific files.
Another ideas would be to rebuild only specific entry files in dev mode.
Also using TypeScript Dynamic Imports so libraries can by lazyloaded and could be a separate chunk.

- check if and why there are CSS files in node modules in bundled JavaScript files.
- check lodash imports, e.g. `lodash` to e.g. `lodash/get`. We also heard about `lodash-es`.
- check if you use the `type` keyword when importing types without ahving to import the whole library.
- Webpack optimization could be set to initial (would create one named javaScript file), or all (would create a lot of very small files). For "all" it can help to have a function on your server which loads all JS files in the HTML file.
- Use defer/async keywords on `script` tags. For `<script type="module"/>` `defer` is already the default and does not have to be added.

Best solution would be to switch to Vite ;)
