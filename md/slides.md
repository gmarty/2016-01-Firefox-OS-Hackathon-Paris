# Add-ons Firefox OS
## Firefox OS France User Group<br>Hackathon Janvier 2016

---

[@g_marty](https://twitter.com/g_marty) - Guillaume Marty

Je suis <img src="img/French.svg" style="height: .8em; vertical-align: middle;" alt="Francais" title="Francais"> et j'habite en <img src="img/UK.svg" style="height: .8em; vertical-align: middle;" alt="Angleterre" title="Angleterre">

Je travaille sur <img src="img/Firefox-OS.svg" style="height: 1.7em; vertical-align: middle; margin-bottom: 21px;" alt="Firefox OS" title="Firefox OS">

---

## C'est quoi ?

Note:
On pouvait déja éditer le code auparavant: démo.
Les add-ons permettent de persister ces changements.
Exclusivité, unique dans le monde du mobile.

---

## A quoi ça sert ?

Note:
Micro fonctionnalité.
Correction de bugs, ajout de fonctionnalité sur des sites web.
Pas de limite a la customisation de mon téléphone.

---

## WebExtensions

Note:
Projet touchant a terme toutes les version de Firefox.
Nouveau modele d'extensions basé sur les extensions supportées par Chrome et Opera.
Mozilla croit au principe d'interroperabilité.

---

## Anatomie d'une extension

![WebExtension](img/webextension.svg)

---

## manifest.json

```json
{
  "manifest_version": 1,
  "name": "Add-on Sample",
  "description": "Firefox OS add-on example",
  "version": "1.0",
  "author": "Guillaume Marty",
  "content_scripts": [
    {
      "matches": ["app://system.gaiamobile.org/index.html"],
      "css": ["css/style.css"],
      "js": ["js/index.js"]
    }
  ],
  "icons": { "128": "/icons/128.png" }
}
```

---

## update.webapp

```json
{
  "name": "Add-on Sample",
  "description": "Firefox OS add-on example",
  "developer": {
   "name": "Guillaume Marty"
  },
  "package_path": "extension.zip",
  "icons": { "128": "/icons/128.png" }
}
```

Note:
icons de update.webapp peut changer.

---

## Spécificités

* <div>`window` is est proxié</div> <!-- .element: class="fragment" data-fragment-index="1" -->
* <div>Le `DOM` peut être chargé ou pas</div> <!-- .element: class="fragment" data-fragment-index="2" -->
* <div>Éviter les injections multiples</div> <!-- .element: class="fragment" data-fragment-index="3" -->
* <div>Évènement `onenabledstatechange`</div> <!-- .element: class="fragment" data-fragment-index="4" -->
* <div>Hérite des permissions de l'hote</div> <!-- .element: class="fragment" data-fragment-index="5" -->

Note:
On peut lire les prop de window mais les prop créés par l'add-on ne sont visibles
par l'app.
Verifier le cas ou le DOM a deja ete charge pour executer l'add-on.
onenabledstatechange pour initialiser ou nettoyer une extension. Dispo dans certaines
conditions uniquement.
Une extension ne peut pas modifier les permissions du contexte dans lequel elle
est éxécutée.

---

## Attention

|Produit|Version|Date|
|---------------|---|----------------------|
|Firefox OS     |2.5|2015/08/27 ou + récent|
|Firefox Desktop|44 |2015/09/30 ou + récent|

---

## Attention

* Incompatible avec simulators du WebIDE
* Utiliser le mulet

---

## Marketplace

<img src="img/marketplace.png" alt="Marketplace" style="width:400px;">

Note:
Integré dans le Marketplace, accessible via un menu dans le pied de page.
Environ 25-30 extensions déja disponibles.

---

## Le futur

* Plus de fonctionnalités, moins de bugs
* Support d'APIs des WebExtensions de Chrome

Note:
Compatbilité avec les versions de Firefox.

---

## Documentation

---

[developer.mozilla.org/en-US/Firefox_OS/Add-ons](https://developer.mozilla.org/en-US/Firefox_OS/Add-ons)

<img src="img/mdn.png" alt="MDN" style="width:400px;">

---

[developer.chrome.com/extensions](https://developer.chrome.com/extensions)

<img src="img/google-chrome-extensions.png" alt="Google Chrome Developers" style="width:400px;">

---

Add-on template

[github.com/mdn/simple-addon](https://github.com/mdn/simple-addon)

---

## Forums

* [Dev FxOS forum](https://groups.google.com/forum/#!forum/mozilla.dev.fxos)
* [Discourse](https://discourse.mozilla-community.org/c/add-ons/)
* IRC (#fxos on freenode)

---

## Merci
