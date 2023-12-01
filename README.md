# catala-web-assets

Web assets generated from Catala programs about the French law:
* [The housing benefits](https://github.com/CatalaLang/catala/tree/master/examples/aides_logement)
* [The family benefits](https://github.com/CatalaLang/catala/tree/master/examples/allocations_familiales)

## To use

Add the package to your project:

```
yarn add catala-web-assets
```

Import the wanted file from the `assets` folder:

```js
require("catala-web-assets/assets/<file_name>")
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

* https://catala-lang.org ([source](https://github.com/CatalaLang/catala-website))
* https://code.gouv.fr/demos/catala ([source](https://github.com/CatalaLang/catala-dsfr))

## Note on the redaction of schemas

### Title

The titles must not be defined inside `"kind"` properties of the object
definition but just before the `"$ref"` of the calling parent:

```json
"categorieEquivalenceLoyerD84216": {
  "title": "Catégorie de personnes résidant en logement-foyer",
  "$ref": "#/definitions/categorie_equivalence_loyer_allocation_logement_foyer"
}
```

### Dsfr dedicated UI options

To be used with the Dsfr, there dedicated options for the UI schemas:

#### `ui:tabLabel` and `ui:hideTitle`

`ui:hideTitle` is needed to be specified for item of type `object` inside a
item of type `array` to hide the unique title of the array's items.

`ui:hideTitle` allows to defines tab's label. It needs to be specified at the
root of the item of type `array`.

Example:

```json
"personnesACharge": {
    "ui:tabLabel": "Personne",
    "items": {
        "ui:hideTitle": true,
...
```
