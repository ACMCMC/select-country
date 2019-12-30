<p align="center">
  <img alt="angular-material-extensions's logo"
   height="256px" width="256px" style="text-align: center;" 
   src="https://cdn.jsdelivr.net/gh/angular-material-extensions/select-country@master/assets/angular-material-extensions-logo.svg">
</p>

# @angular-material-extensions/select-country - Angular Material component that allow users to select a country or nationality with an autocomplete feature - Angular V8 supported incl. schematics

[![npm version](https://badge.fury.io/js/%40angular-material-extensions%2Fselect-country.svg)](https://badge.fury.io/js/%40angular-material-extensions%2Fselect-country)
[![npm demo](https://img.shields.io/badge/demo-online-ed1c46.svg)](https://angular-material-extensions.github.io/select-country)
[![docs: typedoc](https://img.shields.io/badge/docs-typedoc-4D0080.svg)](https://angular-material-extensions.github.io/select-country/doc/index.html)
[![Join the chat at https://gitter.im/angular-material-extensions/Lobby](https://badges.gitter.im/angular-material-extensions/Lobby.svg)](https://gitter.im/angular-material-extensions/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://travis-ci.org/angular-material-extensions/select-country.svg?branch=master)](https://travis-ci.org/angular-material-extensions/select-country)
[![codecov](https://codecov.io/gh/angular-material-extensions/select-country/branch/master/graph/badge.svg)](https://codecov.io/gh/angular-material-extensions/select-country)
[![dependency Status](https://david-dm.org/angular-material-extensions/select-country/status.svg)](https://david-dm.org/angular-material-extensions/select-country)
[![devDependency Status](https://david-dm.org/angular-material-extensions/select-country/dev-status.svg?branch=master)](https://david-dm.org/angular-material-extensions/select-country#info=devDependencies)
[![Greenkeeper Badge](https://badges.greenkeeper.io/angular-material-extensions/select-country.svg)](https://greenkeeper.io/)
[![license](https://img.shields.io/github/license/angular-material-extensions/select-country.svg?style=flat-square)](https://github.com/angular-material-extensions/select-country/blob/master/LICENSE)


<p align="center">
  <img alt="@angular-material-extensions/select-country demonstration" style="text-align: center;"
   src="https://raw.githubusercontent.com/angular-material-extensions/select-country/HEAD/assets/v0.2.0/select-country.gif">
</p>

<p align="center">
  <img alt="@angular-material-extensions/select-country demonstration" style="text-align: center;"
   src="https://raw.githubusercontent.com/angular-material-extensions/select-country/HEAD/assets/v0.2.0/select-country.png">
</p>

## Built by and for developers :heart:
Do you have any question or suggestion ? Please do not hesitate to contact us!
Alternatively, provide a PR | open an appropriate issue [here](https://github.com/angular-material-extensions/select-country/issues)

If you like this project, support [angular-material-extensions](https://github.com/angular-material-extensions) 
by starring :star: and sharing it :loudspeaker:

## Table of Contents
- [Demo](#demo)
- [Components](#components)
- [Dependencies](#dependencies)
- [Installation](#installation)
- [API](#api)
- [Usage](#usage)
- [Run Demo App Locally](#run-demo-app-locally)
- [Other Angular Libraries](#other-angular-libraries)
- [Support](#support)
- [License](#license)

<a name="demo"/>

## [Demo](https://angular-material-extensions.github.io/select-country)

View all the directives and components in action at [https://angular-material-extensions.github.io/select-country](https://angular-material-extensions.github.io/select-country)

<a name="components"/>

## Library's components
- `<mat-select-country>` used to display the main component


---

<a name="dependencies"/>

## Dependencies
* [Angular](https://angular.io) developed and tested with `8.x`

---

<a name="installation"/>

##  [Installation](https://angular-material-extensions.github.io/select-country/getting-started)

## 1. Install via *ng add*. (Recommended)

If Angular Material Design is not setup, just run `ng add @angular/material` [learn more](https://material.angular.io/guide/getting-started)

Now add the library via the `angular schematics`
```shell
ng add @angular-material-extensions/select-country
```

## 2. Install via *npm*. (Alternative) 

Install peer dependencies 
```shell
npm i svg-country-flags -s
```

then update your `angular.json` like below (svg-country-flags)

```json
"assets": [
              "src/favicon.ico",
              "src/assets",
              {
                "glob": "**/*",
                "input": "./node_modules/svg-country-flags/svg",
                "output": "src/assets/svg-country-flags/svg"
              }
            ],
```

Now install `@angular-material-extensions/select-country` via:
```shell
npm install --save @angular-material-extensions/select-country
```


### Import the library

If you installed the library via angular schematics, you can skip this step

Once installed you need to import the main module:
```js
import { MatSelectCountryModule } from '@angular-material-extensions/select-country';
```
The only remaining part is to list the imported module in your application module. The exact method will be slightly
different for the root (top-level) module for which you should end up with the code similar to (notice ` MatSelectCountryModule.forRoot()`):
```js
import { MatSelectCountryModule } from '@angular-material-extensions/select-country';

@NgModule({
  declarations: [AppComponent, ...],
  imports: [MatSelectCountryModule.forRoot(), ...],  
  bootstrap: [AppComponent]
})
export class AppModule {
}
```

Other modules in your application can simply import ` MatSelectCountryModule `:

```js
import { MatSelectCountryModule } from '@angular-material-extensions/select-country';

@NgModule({
  declarations: [OtherComponent, ...],
  imports: [MatSelectCountryModule, ...], 
})
export class OtherModule {
}
```

<a name="api"/>

## API

### `<mat-select-country>`  used to display the main component - [see the demo examples](https://angular-material-extensions.github.io/select-country/examples)

| option | bind  |  type  |   default    | description  |
|:-------------------|:--------:|:------:|:------------:|:-------------------------------------------------------------------------------------------------|    
| appearance      | `Input()`  | `MatFormFieldAppearance`    | - |  Possible appearance styles for `mat-form-field` | 'legacy' | 'standard' | 'fill' | 'outline'
| disabled      | `Input()`  | `boolean`    | - |  Whether the component is disabled
| disabled      | `Input()`  | `boolean`    | - |  Whether the component is read only
| onCountrySelected  | `Output()` | `EventEmitter<Country>`    | - | emits the selected country as object (see the interface below)


```typescript
interface Country {
  name: string;
  alpha2Code: string;
  alpha3Code: string;
  numericCode: string;
}
```


<a name="usage"/>

## [Usage](https://angular-material-extensions.github.io/select-country/getting-started)

add the `<mat-select-country>` element to your template:

```html
<mat-select-country>
</mat-select-country>
```

<p align="center">
  <img alt="@angular-material-extensions/select-country demonstration" style="text-align: center;"
   src="https://raw.githubusercontent.com/angular-material-extensions/select-country/HEAD/assets/v0.2.0/example_full.png">
</p>

<p align="center">
  <img alt="@angular-material-extensions/select-country demonstration" style="text-align: center;"
   src="https://raw.githubusercontent.com/angular-material-extensions/select-country/HEAD/assets/v0.2.0/example3.png">
</p>

<p align="center">
  <img alt="@angular-material-extensions/select-country demonstration" style="text-align: center;"
   src="https://raw.githubusercontent.com/angular-material-extensions/select-country/HEAD/assets/v0.2.0/example2.png">
</p>


<a name="run-demo-app-locally"/>

###  Run Demo App Locally


Build the library

```bash
$ npm run build:lib
```

Serve the demo app

```bash
$ npm start
```



## Other Angular Libraries
- [ngx-auth-firebaseui](https://github.com/AnthonyNahas/ngx-auth-firebaseui)
- [ngx-linkifyjs](https://github.com/AnthonyNahas/ngx-linkifyjs)
- [@firebaseui/ng-bootstrap](https://github.com/firebaseui/ng-bootstrap)
- [@angular-material-extensions/password-strength](https://github.com/angular-material-extensions/password-strength)
- [@angular-material-extensions/google-maps-autocomplete](https://github.com/angular-material-extensions/google-maps-autocomplete)
- [@angular-material-extensions/link-preview](https://github.com/angular-material-extensions/link-preview)
- [@angular-material-extensions/pages](https://github.com/angular-material-extensions/pages)
- [@angular-material-extensions/contacts](https://github.com/angular-material-extensions/contacts)
- [@angular-material-extensions/faq](https://github.com/angular-material-extensions/faq)
- [@angular-material-extensions/combination-generator](https://github.com/angular-material-extensions/combination-generator)

---

<a name="support"/>

## Support
+ Drop an email to: [Anthony Nahas](mailto:anthony.na@hotmail.de)
+ or open an appropriate [issue](https://github.com/angular-material-extensions/select-country/issues)
+ let us chat on [Gitter](https://gitter.im/angular-material-extensions/Lobby)
 
 Built by and for developers :heart: we will help you :punch:

---

![jetbrains logo](https://raw.githubusercontent.com/angular-material-extensions/select-country/HEAD/assets/jetbrains-variant-4_logos/jetbrains-variant-4.png)

This project is supported by [jetbrains](https://www.jetbrains.com/) with 1 ALL PRODUCTS PACK OS LICENSE incl. [webstorm](https://www.jetbrains.com/webstorm)

---

<a name="license"/>

## License

Copyright (c) 2019 [Anthony Nahas](https://github.com/AnthonyNahas). Licensed under the MIT License (MIT)
