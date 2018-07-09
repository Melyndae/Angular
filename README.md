# Angular

## Qu'est ce que Angular ?
### Le Framework Javascript by Google

Angular un Framework "côté client"

Angular est un framework JavaScript Open Source développé par Google. Il utilise l’architecture MVM (Modèle Vue Modèle), proche du modèle MVC. Cela va permettre de structurer son code et bien séparer la vue (l’interface) des modèles (fonctionnement).

Il est considéré comme un langage « côté client », ceux-ci permettent de gérer l’interface utilisateur de chaque page (affichage, interactions…) de façon dynamique et viennent en complément aux langages côté serveur.

Les modules vont nous permettre de rajouter des fonctionnalités aux frameworks de base afin de pouvoir l’enrichir.

Il enrichit le HTML et le JavaScript en permettant de créer ses propres composants afin de les réutiliser dans d’autre projet.

Une autre de ses particularités est son architecture MVM qui permet de gérer plus simplement l’interface et de la rendre plus dynamique en écrivant un minimum de code.
Au revoir AngularJs et bonjour Angular

Google a basé Angular sur 4 principes fondamentaux :

- Augmenter les performances
- La possibilité de s’adapter plus efficacement sur mobile en utilisant les principes du material design
- Utiliser les nouveaux standards du web
- Utiliser le TypeScript afin d’améliorer la productivité

## Commencer rapidement un projet avec Angular Cli
Nous allons voir :

- Comment créer nos fichiers
- Créer un composant Angular
- Bootstrapper notre application
- Les différentes façons de builder

Avant de commencer, vous pourrez trouver la documentation d’Angular CLI ici : http://cli.angular.io

## Installation d’Angular CLI

Avant toute chose, vous devez avoir installé Node et npm.

Ensuite pour installer angular CLI, il suffit de taper la commande suivante dans votre invité de commandes :

    npm install -g @angular/cli

Et voilà vous avez installé Angular CLI.

## Démarrage de votre projet

Pour démarrer une nouvelle application, il suffit d’exécuter la commande suivante :

    ng new mon-projet-angular

Bien entendu, vous pouvez remplacer "mon-projet-angular" par votre nom de projet.

## La structure des dossiers

Après l’installation et la création de votre projet avec angular-cli, nous allons voir la structure des dossiers et fichiers dans l’architecture d’angular-cli.

```
// Tout ce qui va concerner les tests end to end
    e2e/
        app.e2e-spec.ts
        app.po.ts
        tsconfig.e2e.json

// les dépendances avec npm
    node_modules/

// l'endroit où les fichiers de build seront mis
    dist/

// Le dossier où vous allez modifier vos fichiers de code
//Là où va se trouver vos composants, services, etc..
    src/
        app/
            app.component.css|html|spec.ts|ts
            app.module.ts
        assets/
        environments/
            environment.prod.ts|ts
        favicon.ico
        index.html
        main.ts
        polyfills.ts
        styles.css
        test.ts
        tsconfig.app.json
        tsconfig.spec.json
        typings.d.ts

// la configuration globale de votre application
    .angular-cli.json  // Le fichier de configuration principal
    .editorconfig
    .gitignore
    karma.conf.js
    package.json
    protractor.conf.js
    README.md
    tsconfig.json
    tslint.json
```

Voilà, vous avez l’organisation générale de l’architecture ci-dessus.

Je vous conseille de bien comprendre la structure des fichiers et des dossiers dans angular-cli pour ne pas que vous vous retrouviez perdu. Le risque est aussi d’avoir une application non maintenable si vous négligez ce point. Pour ne pas tomber dans ce piège, vous pouvez bien entendu suivre le style guide d’Angular.

Vous allez quasiment passer tout votre temps dans le dossier src/app. Ce dossier contient presque tous les fichiers dont vous avez besoin pour coder votre application. Les fichiers contenus dans ce dossier sont ensuite compilés dans le dossier dist.  Vous pouvez aussi installer des dependances avec le gestionnaire de package de node : npm. Ces dépendances seront installées dans le dossier node_modules.

Les versions et le nom de chaque module sont sauvegardés dans un fichier package.json pour permettre à d’autres personnes d’installer les mêmes dépendances que vous (si vous partagez votre projet sur git par exemple).

Voici le fichier package.json que vous devriez à peu près avoir après avoir créé votre projet avec la commande ci-dessus :

```
{
  "name": "pterrat-angular-cli-tuto",
  "version": "0.0.0",
  "license": "MIT",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e"
  },
  "private": true,
  "dependencies": {
    "@angular/animations": "^5.0.0",
    "@angular/common": "^5.0.0",
    "@angular/compiler": "^5.0.0",
    "@angular/core": "^5.0.0",
    "@angular/forms": "^5.0.0",
    "@angular/http": "^5.0.0",
    "@angular/platform-browser": "^5.0.0",
    "@angular/platform-browser-dynamic": "^5.0.0",
    "@angular/router": "^5.0.0",
    "core-js": "^2.4.1",
    "rxjs": "^5.5.2",
    "zone.js": "^0.8.14"
  },
  "devDependencies": {
    "@angular/cli": "1.5.2",
    "@angular/compiler-cli": "^5.0.0",
    "@angular/language-service": "^5.0.0",
    "@types/jasmine": "~2.5.53",
    "@types/jasminewd2": "~2.0.2",
    "@types/node": "~6.0.60",
    "codelyzer": "~3.2.0",
    "jasmine-core": "~2.6.2",
    "jasmine-spec-reporter": "~4.1.0",
    "karma": "~1.7.0",
    "karma-chrome-launcher": "~2.1.1",
    "karma-cli": "~1.0.1",
    "karma-coverage-istanbul-reporter": "^1.2.1",
    "karma-jasmine": "~1.1.0",
    "karma-jasmine-html-reporter": "^0.2.2",
    "protractor": "~5.1.2",
    "ts-node": "~3.2.0",
    "tslint": "~5.7.0",
    "typescript": "~2.4.2"
  }
}
```

Rassurez-vous, toutes ces dépendances sont automatiquement ajoutées et incluses dans le fichier src/index.html. 

Si vous regardez dans ce fichier, vous allez remarquer des balises <app-root></app-root>. Ces balises vont servir à injecter votre application.

## Builder notre application
Bon, il est temps de run notre application. Rien de plus simple avec Angular-cli, il suffit d’executer la commande suivante :

    ng serve

Angular CLI va build l’application avec webpack. Il est possible pour vous de voir le résultat sur http://localhost:4200, ou de l'ouvrir directement avec la commande 

    ng serve -open

Que dire d’autre sur ng serve d'Angular CLI ?

- Le build de votre application se fait avec webpack et plus avec SystemJs comme avant
- A chaque fois que vous sauvegardez un de vos fichiers, ng serve va recompiler automatiquement pour vous
- Il va automatiquement router pour vous
- Vous pourrez ouvrir votre application dans votre navigateur à http://localhost:4200
- Très simple d’utilisation et à comprendre
- Vous pouvez voir la taille de vos bundles pour votre application

Nous allons voir maintenant comment générer des “choses” pour votre application de façon simple.

## Générer des "choses" pour votre application
Il est possible de générer plusieurs parties pour votre application.

Pour cela, il faut utiliser la commande ng generate. Avec cette commande il est possible de créer :

- Un composant
- Une directive
- Une route
- Un pipe
- Un service

On peut dire que Angular-cli va nous simplifier clairement la vie au niveau de la création de composants, pipe, … Et oui, c’est fini les créations à la main.

Nous allons voir cela avec un exemple concret.

## Comment créer un composant avec Angular-CLI

    ng generate component hello-world

ou plus simplement par :

    ng g component hello-world

(Vous pouvez remplacer "hello-world" par le nom de votre composant.)
Voilà, vous avez créer un composant Hello-world.

La commande a créé un dossier hello-world, les fichiers associés à ce composant :

- hello-world.component.html (pour le template)
- hello-world.component.css (pour le fichier style)
- hello-world.component.ts (pour le code métier du composant)
- hello-world.component.spec.ts (pour le fichier de test propre au composant)

Remarque : Quand vous utilisez la commande ng generate component, pensez au nom de votre composant et pas au nom de la classe. Par exemple, si vous utilisez la commande ng generate component HelloWorldComponent, vous allez créer un composant HelloWorldComponentComponent.

## Générer un nouveau module

Il est possible d’ajouter des modules. Ils servent à encapsuler des fonctionnalités similaires dans votre application.

Il est intéressant de séparer en plusieurs modules les fonctionnalités de votre application pour vous y retrouver facilement. Il est nécessaire de pouvoir appeler les différentes sections de l’application en les appelant par une route spécifique.

Pour générer un module, on reste dans la même idée que pour générer un composant :

    ng generate module projet --routing

ng generate module permet d’ajouter un module et le flag routing précédé de ng generate module, permet de l’associer à une route.

Nous avons créé un module ProjetModule qui est automatiquement inclus dans AppModule :

```
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';

import { ProjetRoutingModule } from './projet-routing.module';

@NgModule({
  imports: [
    CommonModule,
    ProjetRoutingModule
  ],
  declarations: []
})
export class ProjetModule { }
```

Il y a aussi un fichier pour permettre le routing qui a été créé :

```
import { NgModule } from '@angular/core';
import { Routes, RouterModule } from '@angular/router';

const routes: Routes = [];

@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule]
})
export class ProjetRoutingModule { }
```

## Créer un composant dans un module spécifique

Nous venons de créer un module, mais un module sans pouvoir créer un composant dedans ne sert à rien.

Nous allons voir maintenant comment créer un composant CreateProjet dans notre ProjetModule.

    ng g component projet/create-project

Nous avons maintenant un composant CreateProjetComponent dans notre module ProjetModule. Angular-cli nous a tout modifié et par conséquent, nous a bien simplifié la vie.

## Générer d'autre chose

Il est aussi possible de générer :

    Component : ng g component mycomponent
    Directive : ng g directive mydirective
    Pipe : ng g pipe mypipe
    Service : ng g service myservice
    Class : ng g class myclass
    Guard : ng g guard myguard
    Interface : ng g interface myinterface
    Enum : ng g enum myenum
    Module : ng g module mymodule

Comme vous pouvez le voir, il y a beaucoup de possibilités.

## Les différentes possibilités de build votre application

Nous allons voir les différentes possibilités de build.

Pour build en production, il suffit de lancer la commande suivante :

    ng build

Les bundles vont être générer dans le dossier dist. Il suffit d’ouvrir index.html dans votre navigateur et l’application va marcher.

### Build en production

Pour optimiser le build en production, il est possible de lancer la commande de build avec le flag build afin de diminuer la taille des bundles.

    ng build --prod

### Build en AOT

Vous pouvez ajouter le flag AOT pour diminuer de beaucoup la taille des bundles générés à partir du build.

    ng build --prod --aot

# Voilà ! Ce cours est terminé !