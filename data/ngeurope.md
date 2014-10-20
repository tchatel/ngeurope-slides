!SLIDE ============================

![](angularjs-logo.png)
### Formation ngEurope
## formulaires et directives


    git clone https://github.com/tchatel/ngeurope.git
    git checkout 00
    node web-server.js 8000

<div class="left small">
slides en ligne : http://tchatel.github.io/ngeurope-slides/
ou à télécharger en local :
</div>

    git clone https://github.com/tchatel/ngeurope-slides.git
    node web-server.js 9000



!SLIDE left ============================

<div style="float: left; margin: 20px;"><img src="data/thierry/photo-thierry-chatel.png"/></div>
<div>
  <div style="float: right; margin-right: 15px;"><img src="data/thierry/GDE-2014-Angular JS.svg" width="170px"></div>
  <br/><br/>
  <h2>Thierry CHATEL</h2>
  <p class="big"><em>Consultant et formateur indépendant</em></p>
</div>
<br clear="left"/>
<div class="right">
  <img src="data/thierry/methotic.png" width="650px">
  <br/>
  <div class="left" style="float: left; line-height: 2em;">
    <img src="data/icons/mail.png"        style="vertical-align: middle"/> tchatel@methotic.com <br/>
    <img src="data/icons/google-plus.png" style="vertical-align: middle"/> +ThierryChatel <br/>
    <img src="data/icons/twitter.png"     style="vertical-align: middle"/> @ThierryChatel
  </div>
  <br/>
  <img src="data/thierry/crealead.jpg" width="220px">
</div>


!SLIDE left ============================

<div style="float: left; margin: 20px"><img style="width: 218px" src="data/mael/photo-mael-vincent.jpg"/></div>
<div>
  <div style="float: right; margin-right: 15px;"><img src="data/mael/google-cloud-logo.png" width="350px"></div>
  <br/><br/>
  <h2>Maël VINCENT</h2>
  <p class="big"><em>Ingénieur / Chef de projet</em></p>
</div>
<div class="right">
  <img src="data/mael/lumapps-logo.png" height="140px">
  <br/>
  <div class="left" style="float: left; line-height: 2em;">
    <img src="data/icons/mail.png"        style="vertical-align: middle"/> mael@lumapps.com <br/>
    <img src="data/icons/google-plus.png" style="vertical-align: middle"/> +MaëlVINCENT <br/>
    <img src="data/icons/twitter.png"     style="vertical-align: middle"/> @mvkirk
  </div>
  <br/>
  <img src="data/mael/appengine-qualified.png" width="380px">
</div>


!SLIDE left ============================

<div style="float: left; margin: 20px;"><img src="data/mathieu/photo-mathieu-tricoire.png"/></div>
<div>
  <br/><br/>
  <h2>Mathieu TRICOIRE</h2>
  <p class="big"><em>Développeur indépendant</em></p>
</div>
<br clear="left"/>
<div class="right" style="margin-top: 100px">
  <div class="left" style="float: left; line-height: 2em;">
    <img src="data/icons/mail.png"        style="vertical-align: middle"/> mathieu@tricoi.re <br/>
    <img src="data/icons/google-plus.png" style="vertical-align: middle"/> +MathieuTRICOIRE <br/>
    <img src="data/icons/twitter.png"     style="vertical-align: middle"/> @tricky21
  </div>
  <br/>
  <img src="data/thierry/crealead.jpg" width="220px">
</div>


!SLIDE blongearet ============================

<div style="float: left; margin: 20px;">
  <img src="data/bennnou/bennnou.jpg" width="250px"/>
</div>
<div>
  <br/><br/>
  <h2>Benjamin Longearet</h2>
  <p class="big"><em>Enthousiaste Dev Front</em></p>
</div>
<br clear="left"/>
<div class="right" style="margin-top: 100px">
  <div class="left" style="float: left; line-height: 2em;">
    <img src="data/icons/mail.png"        style="vertical-align: middle"/> bl@teads.tv <br/>
    <img src="data/icons/twitter.png"     style="vertical-align: middle"/> @blongearet <br/>
    <img src="data/icons/github.png" style="vertical-align: middle"/> firehist
  </div>
  <br/>
  <img src="data/bennnou/Logo_teads_blackx2.png" width="220px">
  <img src="data/bennnou/rocket.svg" style="position: absolute;width: 170px;-webkit-transform: rotate(30deg);-ms-transform: rorate(30deg);transform: rotate(30deg);right: 17rem;bottom: -5rem;">
</div>


!SLIDE left ============================

<div style="float: left; margin: 20px;">
  <img src="data/julien/julien.jpg" width="250px"/>
</div>
<div>
  <br/><br/>
  <h2>Julien Bouquillon</h2>
  <p class="big"><em>Développeur full-stack</em></p>
</div>
<br clear="left"/>
<div class="right" style="margin-top: 100px">
  <div class="left" style="float: left; line-height: 2em;">
    <img src="data/icons/mail.png"        style="vertical-align: middle"/> julien@revolunet.com <br/>
    <img src="data/icons/twitter.png"     style="vertical-align: middle"/> @revolunet <br/>
    <img src="data/icons/github.png" style="vertical-align: middle"/> revolunet
  </div>
  <br/>
  <img src="data/julien/revolunet.jpg" width="220px">
</div>



!SLIDE smallcode ========================

## Directives AngularJS

```
angular.module('MyModuleName', [])
    // JS: Camel-case, HTML: Lower-case dash-delimited
    .directive('MyDirectiveName', function () {
        return {
            restrict: 'AE', // A: Attribute, E: Element
            scope: { // true: child scope, {}: isolated scope
                // @: one-way text, =: two-way binding, &: action
                desc: '='
            },
            template: '<div>{{ desc }}</div>',
            templateUrl: 'path/my-template-url.html',
            replace: false, // If true, the template remplaces the element itself
            transclude: true, // Use transclude
            require: ['ngModel'], // Require other directive
            controller: function ($scope) { // Directive controller
            },
            link: function (scope, element, attrs, controllers) {
            }
        };
    }) //.directive(...)
```

<div class="smaller">
[Guide](http://goo.gl/BICl1C) - [Doc](http://goo.gl/yIgUv2)
</div>


!SLIDE ========================

## Création d'une directive <span class="small">(version réduite)<span>


    .directive('nomEnCamelCase', function () {

        return {
            restrict: 'AE',  // A: Attribute, E: Element
            scope: false,
            link: function (scope, element, attrs, ctrl) {

                // ... code ...

            }
        };

    })


!SLIDE ========================

## Scope isolé

<img src="data/scope-isole.svg" width="900px"/>

<div class="smaller">
[Guide](http://goo.gl/BICl1C) - [Doc](http://goo.gl/yIgUv2)
</div>



!SLIDE ========================

## Scope isolé


    scope: {
        // Binding bidirectionnel avec la valeur d'une
        // expression AngularJS
        value: '=',

        // Binding monodirectionnel depuis un attribut texte
        // pouvant contenir des expressions AngularJS entre {{...}}
        text: '@',

        // Fonction permettant de déclencher une action
        //  (indiquée dans une expression AngularJS)
        action: '&',
    }

<div class="left small">
Le nom de la propriété correspond au nom de l'attribut HTML, <br/>
transformé en “_Camel Case_”.<br/><br/>
Le scope isolé n'hérite pas des données du scope externe.
</div>

!SLIDE ========================

## Template

    template: '... template AngularJS avec directives ...',

    // ou :

    templateUrl: 'relativePath/fileName.html'
<br/>

    // Insère le template dans l'élément courant
    // en écrasant son ancien contenu
    replace: false,

    // Remplace l'élément courant par le template
    // (avec un seul élément racine)
    replace: true,


!SLIDE ========================

## Template & transclude

<br/>
<div class="left small">
Pour récupérer l'ancien contenu de l'élément, et l'insérer à un certain endroit du template de la directive :
</div>


    transclude: true
    // ou :
    transclude: 'element' // Récupère l'élément et son ancien contenu
<br/>

<div class="left small">
Dans le template :
</div>

    <div ng-transclude><!-- l'ancien contenu sera inséré ici --></div>


!SLIDE smallcode ========================

## Formulaires

        <form name="form" class="css-form" novalidate ng-submit="update(user)">
            Name:
            <input type="text" ng-model="user.name" name="uName" required/>
            <br />
            E-mail:
            <input type="email" ng-model="user.email" name="uEmail" required/>
            <br />
            <div ng-show="form.uEmail.$dirty && form.uEmail.$invalid">
                Invalid:
                <span ng-show="form.uEmail.$error.required">Tell us your email.</span>
                <span ng-show="form.uEmail.$error.email">This is not a valid email.</span>
            </div>
            <input type="submit" ng-disabled="form.$invalid || form.$pristine" value="SAVE"/>
        </form>

<div class="left small">
Attribut `novalidate` sur le formulaire pour désactiver la validation du navigateur web.<br/><br/>
Donner un nom (attribut `name`) au formulaire et au champ de saisie, pour récupérer l'objet **[ngModelController](https://docs.angularjs.org/api/ng/type/ngModel.NgModelController)**
par `<nom_du_formulaire>.<nom_du_champ>`<br/>
</div>







!SLIDE ========================

## L'application (1/3)

<img src="data/app-1-principe.svg" width="800px"/>

!SLIDE ========================

## L'application (2/3)

<img src="data/app-2-form.svg" width="800px"/>

!SLIDE ========================

## L'application (3/3)

<img src="data/app-3-field.svg" width="800px"/>


!SLIDE bullets ========================

# 00<span class="small">(1/2)</span>: fichiers fournis

* sur GitHub : https://github.com/tchatel/ngeurope.git
    * et choisir la branche 00

            git clone https://github.com/tchatel/ngeurope.git
            git checkout 00

    * chaque branche de 00 à 19 correspond au résultat d'une étape

* démarrer Node.js avec le fichier `web-server.js` fourni
    * à faire dans le répertoire racine

            node web-server.js 8000

    * et afficher l'URL http://localhost:8000/app/index.html

<div class="small right">_Suite au dos (de l'écran)_</div>


!SLIDE bullets ========================

# 00<span class="small">(2/2)</span>: fichiers fournis


* les fichiers au départ :
    * **`css/app.css`** : styles CSS fournis, qu'il faudra compléter
    * **`data/desc.json`** : la description du formulaire envoyée par le serveur
    * **`js/app.js`** : module principal de l'application, avec un contrôleur et un service chargeant la description du formulaire
    * **`js/autoform.js`** : module pour les directives à créer
    * **`js/autoform_test.js`** : quelques tests unitaires des directives, utilisés à l'étape 06
    * **`templates/`** : répertoire où seront créés les templates des directives
    * **`index.html`** : template principal de l'application




!SLIDE bullets ========================

# 01: directive **autoform**

* Créer la directive **autoform**, dans le module **autoform** fourni
    * utilisable comme élément
* avec un **scope isolé**
    * pour récupérer la description du formulaire (attribut **desc**) et l'objet à alimenter (attribut **model**)
* avec un **template** : `templates/autoform.html`
    * `<div>` avec `class="autoform-header"`
        * y afficher l’ancien contenu de l’élément `<autoform>` (**transclude**)
    * `<form>` avec `novalidate`
    * `<div>` répété pour chaque champ
        * afficher pour l'instant simplement le libellé du champ (propriété 'label')


!SLIDE bullets ========================

# 02: directive **autoformfield**

* Créer la directive **autoformfield**, dans le module **autoform**
    * en enchaînant un second appel à la méthode `directive()`,<br/>
      à la suite du précédent
    * utilisable comme élément
* avec un **scope isolé**
    * où l’on récupère la description du champ (attribut **desc**), et l’objet à alimenter (attribut **model**)
* avec un **template**
    * affichant juste pour l'instant le libellé du champ
* Utiliser cette directive dans le template de **autoform**
    * comme élément, en remplacement du `<div>` répété


!SLIDE bullets ========================

# 03: champs de saisie

* Utiliser la directive **ngSwitch**
    * pour conditionner le template en fonction du **type** de champ
* 3 templates différents, contenant :
    * une liste déroulante, si type="select"
        * <span class="small">`<label>...</label><div><select></select><!-- message d'erreur --></div>`</span>
    * une case à cocher, si type="checkbox"
        * <span class="small">`<label><input type="checkbox"/>...</label>`</span>
    * un champ de saisie, dans tous les autres cas
        * utiliser la valeur du type dans l'attribut type du champ `<input>`
        * <span class="small">`<label>...</label><div><input type="..."/><!-- message d'erreur --></div>`</span>

<div class="small">_La directive ngModel et la liste déroulante seront alimentées dans les 2 étapes suivantes._</div>


!SLIDE bullets ========================

# 04: ngModel

<div class="left">
_Les données saisies doivent alimenter directement les propriétées voulues de l'objet cible._
</div>


* Utiliser la directive ngModel (attribut ng-model) pour alimenter
    * la propriété dont le nom est dans **desc.property**
    * de l'objet récupéré dans le scope isolé à partir de l'attribut **model**
    * la valeur de l'attribut ng-model est une expression AngularJS
        * syntaxe similaire à du JS
        * elle ne doit pas contenir de <span ng-non-bindable>`{{...}}`</span>
    * réponse : <span class="quizz small">`ng-model="model[desc.property]"`</span>
      <br/><span class="smaller grey">_tapez 'q' pour voir la réponse_</span>



!SLIDE bullets ========================

# 05: liste déroulante

* Utiliser l'attribut **ng-options** pour alimenter la liste déroulante
    * d'après la propriété **list** de la description, qui est un objet JS et non un tableau
    * syntaxe : _select_ **as** _label_ **for (**_key_**, **_value_**) in** _object_
    * réponse : <span class="quizz small">`ng-options="code as label for (code, label) in desc.list"`</span>
      <br/><span class="smaller grey">_tapez 'q' pour voir la réponse_</span>


!SLIDE bullets smallcode ========================

# 06<span class="small">(1/2)</span>: tests unitaires

<div class="left">
_Les tests sont déjà écrits, vous allez simplement les lancer, et regarder comment ils fonctionnent._
</div>

* Karma
    * installation (avec `-g` en global, sans `-g` en local)

            npm install -g karma
            npm install -g karma-cli
            npm install -g karma-chrome-launcher
            npm install -g karma-firefox-launcher
            npm install -g karma-ie-launcher
            npm install -g karma-jasmine
            npm install -g karma-junit-reporter
            npm install -g karma-ng-html2js-preprocessor

<br/>
<div class="small right">_Suite au dos (de l'écran)_</div>


!SLIDE bullets smallcode ========================

# 06<span class="small">(2/2)</span>: tests unitaires

* Karma
    * lancement, si en global et dans le path :

            karma start karma.conf.js

        * sinon :

                node node_modules/karma-cli/bin/karma start karma.conf.js

    * Karma lance Chrome, et les résultats sont dans la fenêtre de commande

* Tests
    * dans le fichier `app/js/autoform_test.js`
    * on teste une directive en compilant un bout de template qui la contient,
      avec le service `$compile`





!SLIDE bullets ========================

# 07: validation

* Mettre une bordure rouge aux champs en erreur
    * pour l'instant seuls les champs avec un type email ou number seront en erreur si le format des données saisies est invalide
* Indiquer les champs obligatoires
    * s'ils ont une propriété `constraints.required` à `true`
    * rendre ces champs requis à l'aide de la directive **ngRequired**
        * et vérifier qu'ils ont maintenant une bordure rouge
    * afficher aussi une * à côté du libellé des champs obligatoires


!SLIDE bullets ========================

# 08<span class="small">(1/2)</span>: messages d'erreurs

* Utiliser la directive **ngMessages**
    * directive apparue en v*3, dans le module optionnel **ngMessages**
    * pour afficher le message d'erreur adéquat à côté des champs input ou select en erreur , avec une classe CSS `"error"`
* Valeur de l'attribut **`ng-messages`**
    * il faut lui passer une valeur du type <br/>`ng-messages="form.field.$error"` où :
        * `form` est le _name_ du formulaire
        * `field` est le _name_ du champ
        * MAIS : les attributs **_name_** ont des valeurs en dur, pas des expressions AngularJS - d'où des collisions
          dans les portions répétées du formulaire

<div class="small right">_Suite au dos (de l'écran)_</div>


!SLIDE bullets ========================

# 08<span class="small">(2/2)</span>: messages d'erreurs

* Valeur de l'attribut **`ng-messages`** dans un élément répété
    * mettre sur l'élément répété : `ng-form name="row"`
        * ou en un seul attribut : `ng-form="row"`
    * accéder à l'objet $error à partir de _row_
        * `ng-messages="row.field.$error"`
        * en nommant tous les champs _field_
* Fournir des messages d'erreur pour les clefs suivantes
    * `<select>` : required
    * `<input>` : number, email, required _(dans cet ordre)_
        * il faut que la clef _number_ soit avant la clef _required_, à cause d'une mauvaise indication donnée par les
          navigateurs web quand la saisie n'est pas numérique dans un champ `<input type="number">`


!SLIDE bullets ========================

# 09: messages différés

* Afficher les messages d'erreur :
    * (1) seulement après que le champ ait perdu le focus
        * via la directive **ngBlur**, en mettant une propriété _blur_ à _true_ dans la description du champ
    * (2) ou lorsque le champ est modifié (condition : `row.field.$dirty`)
* Utiliser ensuite la directive **ngModelOptions** (version *3)
    * pour faire la mise à jour après 500ms sans appui sur une touche
    * ou immédiatement sur l'événement _blur_
    * solution : <span class="quizz smallest">`ng-model-options="{ updateOn: 'default blur', debounce: {'default': 700, 'blur': 0} }"`</span>
* Bordure rouge seulement après perte du focus
    * en utilisant une classe CSS supplémentaire
        * solution : <span class="quizz smaller">`ng-class="{ blur: desc.blur }"`</span>
          <span class="smaller grey">_tapez 'q' pour la voir_</span>


!SLIDE bullets ========================

# 10: service pour la directive

* Passer à la directive **autoform** un attribut `service="formLoader"`
    * il contient le nom du service à utiliser pour charger la description du formulaire
    * enlever le service du contrôleur
        * qui ne publie donc plus la description dans le scope
    * injecter le service `$injector` d'AngularJS
        * en mettant un argument avec ce nom exact à la _factory_ de la directive <br/>
          (la fonction qui renvoie l'objet de configuration de la directive)
    * dans la fonction **link** de la directive :
        * utiliser `$injector.get()` pour récupérer le service spécifié
        * charger la description du formulaire et la publier dans le scope


!SLIDE bullets ========================

# 11<span class="small">(1/3)</span>: champ rating

<div class="left">
_On veut créer un type de champ spécial pour représenter ou saisir une note de 1 à 5, sous la forme d'une série d'étoiles._
</div>


* Créer une directive **rating**
    * utilisable comme élément ou attribut
    * avec un scope isolé (vide)
    * dans sa fonction _link_, publier dans le scope
        * un tableau : `values = [1, 2, 3, 4, 5]`
        * pour l’instant une valeur courante en dur : `currentValue = 3`

* Ajouter un nouveau _ngSwitchWhen_ pour le type 'rating', utilisant la directive **rating**

<div class="small right">_Suite au dos (de l'écran)_</div>

!SLIDE bullets ========================

# 11<span class="small">(2/3)</span>: champ rating

* Ajouter un template à la directive
    * avec un `<span>` répété pour toutes les valeurs du tableau `values`
    * qui affiche une étoile pleine ou vide selon le cas
        * étoile pleine : `<i class="icon-star"></i>`
        * étoile vide : `<i class="icon-star-empty"></i>`

* Vous pouvez aussi afficher directement la valeur currentValue après le `<span>` répété.

<br/>
<br/>
<div class="small right">_Suite au dos (de l'écran)_</div>

!SLIDE bullets ========================

# 11<span class="small">(3/3)</span>: champ rating

* La directive doit maintenant :
    * récupérer le contrôleur publié par la directive **ngModel**
        * _solution :_ <span class="smaller grey">_(tapez 'q' pour la voir)_</span><br/>
          <span class="quizz smaller">Ajouter à l'objet de définition de la directive la propriété :</span><br/>
          <span class="quizz smaller">&nbsp;&nbsp;`require: 'ngModel'`&nbsp;&nbsp;</span><br/>
          <span class="quizz smaller">Le contrôleur est reçu dans le quatrième argument de la fonction _link_.</span><br/>
    * dans sa fonction _link_, publier dans le scope une fonction **setValue** qui :
        * change la valeur `currentValue` du scope
        * appelle la fonction `$setViewValue` du contrôleur avec la nouvelle valeur
    * appeler cette fonction **setValue** quand l’utilisateur clique sur le `<span>` contenant une étoile vide ou pleine


!SLIDE bullets smallcode ========================

# 12: icônes d'édition du formulaire

* Attribut **editable**
    * à mettre sur la directive **autoform**, et récupéré dans le scope isolé
* Icônes
    * afficher avec le code ci-dessous 4 icônes pour chaque champ<br/>
      (à mettre dans le ngSwitch, avant les différentes alternatives)


    <div class="autoformfield-icons">
        <div>
            <a href="" tabIndex="-1"><i class="icon-circle-arrow-up"></i></a>
            <a href="" tabIndex="-1"><i class="icon-edit"></i></a>
        </div>
        <div>
            <a href="" tabIndex="-1"><i class="icon-circle-arrow-down"></i></a>
            <a href="" tabIndex="-1"><i class="icon-remove-circle"></i></a>
        </div>
    </div>


!SLIDE bullets ========================

# 13<span class="small">(1/2)</span>: contrôleur

* Créer un contrôleur dans la directive **autoform**
    * et le récupérer dans la fonction _link_ de la directive enfant **autoformfield**<br/>
      _Solution :_ <span class="quizz smaller">`require: '^autoform'`</span>
      <span class="smaller grey">_(tapez 'q' pour la voir)_</span>

* **isEditable**
    * dans l’instance du contrôleur (sur “`this`”), créer une fonction **isEditable** qui indique si le formulaire est éditable
    * dans la fonction _link_ de la directive **autoformfield**, créer sur le scope une fonction **isEditable** appelant celle du contrôleur
    * utiliser cette fonction pour conditionner la visibilité des icônes

<br/>
<div class="small right">_Suite au dos (de l'écran)_</div>

!SLIDE bullets ========================

# 13<span class="small">(2/2)</span>: contrôleur

* Mode du formulaire
    * mettre à côté du titre du formulaire deux icônes :
        * dont une seule est affichée à la fois
        * qui font basculer le formulaire en mode édition ou read-only

                <a href="" tabIndex="-1"><i class="icon-edit"></i></a>
                <a href="" tabIndex="-1"><i class="icon-eye-close"></i></a>

    * rendre visibles les icônes des champs seulement lorsque le formulaire est éditable


!SLIDE bullets ========================

# 14: déplacer un champ

* Créer sur le contrôleur
    * une fonction **moveUp**
        * qui prend la description d'un champ en paramètre
        * qui la permute dans le tableau avec celle du champ précédant (s'il y en a un)
    * une fonction **moveDown** sur le même principe
* Dans la fonction _link_ de **autoformfield**
    * publier dans le scope deux fonctions **moveUp** et **moveDown**
* Utiliser ces deux fonctions sur les icônes correspondantes


!SLIDE bullets ========================

# 15: supprimer un champ

* Supprimer un champ, de la même façon :
    * fonction **remove** sur le contrôleur
    * fonction **remove** publiée dans le scope de **autoformfield**


!SLIDE bullets ========================

# 16<span class="small">(1/2)</span>: modification d'un champ

* Créer 3 fonctions sur le contrôleur :
    * **startEdit** avec la description d’un champ en paramètre
    * **stopEdit** sans paramètre
    * **isEditing** avec la description d’un champ en paramètre
    * variable locale de la fonction contrôleur
        * contenant la description du champ en cours de modification (quand il y en a un)
        * utilisée par les 3 fonctions ci-dessus
    * un seul champ peut être modifié à la fois

* Créer les fonctions correspondantes dans le scope de **autoformfield**

<div class="small right">_Suite au dos (de l'écran)_</div>

!SLIDE bullets ========================

# 16<span class="small">(2/2)</span>: modification d'un champ

* Utiliser la fonction **startEdit** sur l’icône appropriée

* Template de modification d'un champ
    * conditionner le `<div>` racine du template du champ pour qu’il ne soit pas affiché en mode modification
    * ajouter un second `<div>` à la suite, avec la condition inverse et une classe CSS "`autoformfield-edit`", et contenant :
        * l’icône pour sortir du mode de modification du champ (à rendre fonctionnelle)
        * un `<div>` avec pour l'instant un texte en dur

                <div class="autoformfield-icons">
                    <a href="" tabIndex="-1"><i class="icon-eye-close"></i></a>
                </div>
                <div>EDIT</div>


!SLIDE bullets smallercode ========================

# 17: formulaire de modification

* A la place du “EDIT” en dur dans le `<div>` :
    * mettre les champs suitants :
        * champs texte pour les propriété **property** et **label** de la description
        * checkbox pour la propriété **constraints.required**
        * liste déroulante pour la propriété **type**
    * pour alimenter la liste, définir la propriété suivante dans le contrôleur
      et la publier dans le scope de **autoformfield**

                this.fieldTypes = [
                    {type: 'text',      label: "Champ texte"},
                    {type: 'select',    label: "Liste déroulante"},
                    {type: 'number',    label: "Champ nombre"},
                    {type: 'email',     label: "Champ email"},
                    {type: 'url',       label: "Champ URL"},
                    {type: 'checkbox',  label: "Case à cocher"}
                ];


!SLIDE bullets smallcode ========================

# 18: ajout d'un champ

* Mettre à la fin du formulaire une icône d’ajout d’un champ
    * affichée seulement lorsque le formulaire est éditable

            <div class="autoformfield-icons">
                <a href="" tabIndex="-1"><i class="icon-plus-sign"></i></a>
            </div>

* Fonction **add**
    * créée par la fonction contrôleur, mais dans le scope de **autoform**,<br/>
      pas sur l'instance du contrôleur
    * le nouveau champ ajouté est en mode édition


!SLIDE bullets smallcode ========================

# 19<span class="small">(1/2)</span>: champ JSON

<div class="left">
_On veut créer une directive permettant de saisir sous la forme d'un objet JSON les options d'une liste déroulante._
</div>

* En mode modification d’un champ de type **select**
    * afficher en dessous un champ input texte avec un attribut **json**,<br/>
      pour alimenter la propriété **list**

* Afficher à côté du champ JSON l’une des icônes suivantes, selon s’il est valide ou non :

        <i class="icon-ok"></i>
        <i class="icon-ban-circle"></i>

<div class="small right">_Suite au dos (de l'écran)_</div>

!SLIDE bullets smallcode ========================

# 19<span class="small">(2/2)</span>: champ JSON

* Créer la directive **json**
    * qui s’utilise comme attribut
    * qui a une priorité à 100
    * qui travaille dans le scope courant
    * qui récupère le contrôleur de la directive _ngModel_
    * et qui, dans sa fonction _link_, ajoute les fonctions adéquates aux propriétés **$validators**, **$parsers**
      et **$formatters** du contrôleur de _ngModel_
         * **$validators** est un objet JS indexé par les clefs de validation <br/>
           (définir une clef `'json'` avec la fonction de validation)
         * **$parsers** et **$formatters** sont des tableaux de fonctions


!SLIDE ========================

## fin
