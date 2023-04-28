# catala-web-assets

<details>
    <summary>Table of contents</summary>
    
<!-- vim-markdown-toc GitLab -->

* [To use](#to-use)
  * [In local dev](#in-local-dev)
* [Websites using this assets](#websites-using-this-assets)
* [Note on the redaction of schemas](#note-on-the-redaction-of-schemas)
  * [Title](#title)
  * [Dsfr dedicated tags](#dsfr-dedicated-tags)
    * [`ui:tabLabel` and `ui:hideTitle`](#uitablabel-and-uihidetitle)

<!-- vim-markdown-toc -->
</details>

---

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

## Websites using this assets

* https://catala-lang.org ([source](https://github.com/CatalaLang/catala-website))
* catala-explorer ([source](https://github.com/CatalaLang/catala-explorer))

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

### Dsfr dedicated tags

To be used with the Dsfr, there dedicated tag for the UI schemas:

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
