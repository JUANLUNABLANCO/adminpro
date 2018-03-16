# Adminpro

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.6.3.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).


@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
## Instalations required
  NAME  			        INSTALACION				               VERSION COMAND	    1/1/2017	12/12/2017	ACTUALIZACION
	_____________________________________________________________________________________________________________________________________

  NODE.JS     		      -- WEB					                    >node -v	          V4.3.2    V8.9.3
  --> NPM         		  -- node.js se encarga					      >npm -v		          V2.14.12  V5.5.1
	TYPESCRIPT		        >npm install -g typescript		      >tsc -v				      V2.6.2 -- v2.4.2 ??
	VISUAL STUDIO CODE	  -- WEB
	ANGULAR CLI		        >npm install -g @angular/cli        >ng -v		          V1.6.3				  > npm cache clean		
                                                                                                > npm install -g @angular/cli@latest
                                                                                                >npm install -g @angular/angular.cli    
                                                                                                -- not installed --             
                                                                                                // are you sure of that    
        
        ANGULAR                 -- angular-cli se encarga --                                            V5.2.8
															otra forma> npm uninstall -g @angular/cli	>npm cache verify
				CREAR UN NUEVO PROYECTO CON CLI:	>ng new name-proyect	
                                                                @angular/cli:                           1.6.3
                                                                @angular-devkit/built-optimizer         0.0.42
                                                                @angular-devkit/core                    0.0.29
                                                                @angular-devkit/semanthics              0.0.52
                                                                @ngtools/json-schema                    1.1.0
                                                                @ngtools/webpack                        1.9.3
                                                                @schematics/angular                     0.1.17
                                                                typescript:                             2.4.2 -- 2.6.2 ??
                                                                webpack:                                3.10.0	

	BOOSTRAP 3              -- explaining down --
	BOOTSTRAP4              -- explaining down --
	NGX-BOOTSTRAP           -- explaining down --


@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
--------------------------------------------------------------------------------
    TYPESCRIPT      2.6.2               //TYPESCRIPT EN EL SISTEMA
--------------------------------------------------------------------------------
Tras intentar activar un pluggin de terceros en netbeans, para typescript e intentar
lo mismo con atom y no conseguir ninguno de los dos he decidido desistalar atom
e instalar  VISUAL STUDIO CODE de microsoft

snippets for VSC:
    1. Angular2 typescript emmet
    2. Angular5 Snippets
    3. Angular languaje service
    4. angular v5 snippets
    5. Angular2 inline
    6. Bootstrap 4 & Font Awesomw snippets
    7. HTML CSS Support
    8. javascript (ES6) code snippets
    9. JS-CSS-HTML Formatter
    10. JSHint
    11. Prettier-Code Formatter
    12. Terminal
    13. TSLint
    14. Typescript Hero
    15. Typesrcypt Importer

--------------------------------------------------------------------------------
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
BOOSTRAP 
para instalar boostrap con angular hay varias formas.
################################################################################
1. Using Bootstrap 3

>npm install --save boostrap@3 jquery	//lo instalará a nivel local en nuestro proyecto de angular4

	by adding the file paths to the styles and scripts array in file .angular-cli.json:

	"styles": [
    		"styles.css",
    		"../node_modules/bootstrap/dist/css/bootstrap.min.css"
  	],
  	"scripts": [
    		"../node_modules/jquery/dist/jquery.min.js",
    		"../node_modules/bootstrap/dist/js/bootstrap.min.js"
  	],


################################################################################
2. Using Ng-Bootstrap

>npm install bootstrap@4.0.0-alpha.6
>npm install --save @ng-boostrap/ng-boostrap
        by adding the file paths to the styles and scripts array in file .angular-cli.json:

	"styles": [
    		"styles.css",
    		"../node_modules/bootstrap/dist/css/bootstrap.min.css"
  	],
  	"scripts": [
    		"../node_modules/jquery/dist/jquery.min.js",
    		"../node_modules/bootstrap/dist/js/bootstrap.min.js"
  	],

---app.module.ts 
 
import {NgbModule} from '@ng-bootstrap/ng-bootstrap';

@NgModule({
  declarations: [AppComponent, ...],
  imports: [NgbModule.forRoot(), ...],
  bootstrap: [AppComponent]
})
export class AppModule {
}
################################################################################
3. Using ngx.bootstrap con bootstrap 3 o bootstrap 4
>npm install --save ngx-bootstrap //y además dos dependencias que necesita
>npm install --save @angula-devkit@...
>npm install --save ajv@^6.0.0 

además debemos enlazarlo en el archivo index.html
  <!-- bootstrap 3 -->
  <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet">
  <!-- bootstrap 4 -->
  <!-- <link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" rel="stylesheet"> -->
  <!-- theme templates for bootstrap 4 -->
  <!-- <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet"> -->

para usar los componentes de ngx-bootstrap en 
----------- app.module.ts
// RECOMMENDED (doesn't work with system.js)
import { AccordionModule } from 'ngx-bootstrap/accordion';
// or
import { AccordionModule } from 'ngx-bootstrap';

@NgModule({
  imports: [AccordionModule.forRoot(),...]
})
export class AppModule(){}

---------- app.component.html
<accordion>
  <accordion-group heading="Static Header, initially expanded">
    This content is straight in the template.
  </accordion-group>
  <accordion-group #group>
    <div accordion-heading class="clearfix">
      I can have markup, too!
      <span class="badge badge-secondary float-right pull-right">Some HTML here</span>
    </div>
    This is just some content to illustrate fancy headings.
  </accordion-group>
  <accordion-group heading="Group with isOpenChange event listener" (isOpenChange)="log($event)">
    <p>Some content</p>
  </accordion-group>
  <accordion-group heading="Another group">
    <p>Some content</p>
  </accordion-group>
</accordion>
--- VENTAJAS Y DESVENTAJAS
--- desventajas:
    1. Ensucia un poco el head del index.html por los enlaces
    2. Tiene unas dependencias un poquito inesperadas que no se instalan por su cuenta, 
    @angular-devkit@... y ajv@^6.0.0 y que podrían dar problemas en el futuro, por deprecated


--- ventajas
    1. Funciona tanto con bootstrap 3 como con 4 y con themes de Material, lo que es de agradecer
    2. se cargan los módulos independientes en cada componente, por ejemplo:
    accordion, alerts, buttons, etc
    3. tiene soporte con buena documentación y ejemplos. https://valor-software.com/ngx-bootstrap/

################################################################################
4. instalaremos angular material en vez de bootstrap
    //instalar los paquetes de angular cli
    >ng new NameProyect
    
    //instalar dependencias que no se instalan solas
    >npm install --save @angular-devkit/core@0.0.29 
    >npm install --save ajv@^6.0.0
    
    //instalar angualr material
    >npm install --save @angular/material @angular/cdk
    >npm install --save @angular/animations

    // a esta altura debes configurar el angular-cli.json css
    "../node_modules/@angular/material/prebuilt-themes/indigo-pink.css"
    o hacer un import del archivo en style.css
    @import '~@angular/material/prebuilt-themes/indigo-pink.css';

    //además debes importar los módulos que vayas necesitando de angular material en el app.module.ts
    import { MatToolbarModule } from '@angular/material/toolbar';
    import { MatCardModule } from '@angular/material/card';
    
    @NgModule({
      ...
      imports: [
        ...
        MatToolbarModule,
        MatCardModule
      ]...
    //y por ultimo usarlos en el html
    <mat-toolbar color="primary">
        <span>Material Component</span>
    </mat-toolbar>
    <mat-card>...</mat-card>
