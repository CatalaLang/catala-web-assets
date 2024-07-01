# catala-web-assets

Web assets generated from Catala programs about the French law:

- [The housing benefits](https://github.com/CatalaLang/catala-examples/tree/master/aides_logement)
- [The family benefits](https://github.com/CatalaLang/catala-examples/tree/master/allocations_familiales)

## To use

Add the package to your project:

```
yarn add catala-web-assets
```

Import the wanted file from the `assets` folder:

```js
require("catala-web-assets/assets/<file_name>");
```

### In local dev

In order to test and update the assets without having to publish a new package
version you can:

```
# In this repo
yarn link

# In the website repo
yarn link catala-web-assets
```

## Generating assets

The `assets` folder is generated from the Catala compiler. To generate these
assets, please refer to the [dedicated section of the Catala compiler
`INSTALL.md`](https://github.com/CatalaLang/catala/blob/master/INSTALL.md#generating-website-assets).

## Websites using this assets

- https://catala-lang.org ([source](https://github.com/CatalaLang/catala-website))
- https://code.gouv.fr/demos/catala ([source](https://github.com/CatalaLang/catala-dsfr))

> [!IMPORTANT]
> If the generated schemas is intended to be used with
> [`@codegouvfr/rjsf-dsfr`](https://github.com/codegouvfr/rjsf-dsfr), please
> refer to the [Notes on writing
> schemas](https://github.com/codegouvfr/rjsf-dsfr?tab=readme-ov-file#notes-on-writing-schemas)
> section.
