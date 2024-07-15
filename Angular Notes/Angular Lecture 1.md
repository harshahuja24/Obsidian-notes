### Introduction To Node Package Manager and Angular
npm = Node package manager 
node modules mei we keep all that stuff that we have to pre download library islye those are kept in the node modules
library = dependency 
when we talk about npm we speak about package.json
node_modules ka folder should be added in .gitignore because the depenency i used should be in my package.json and if others want to use it they would have to do install the requirements 
node_module will have all dependencies 
now leena would not give kareena this folder becuase its already in gitignore. to kareena ke pass vo node_modules ka folder nhi jayega 
package.json has all dependency now to install we use npm i that is  ( npm install )
it reads package.json and whatever are your dev dependency ie during development it installs in node modules 
Angular version - 17
angularjs tha pelhe then came angular 
React is a library Angular is a FrameWork 
package.json is our thing that we are doing changes and packagelock.json is kinda staging area 
for eg i need a payments library:  npm i payments
### Structure of Angular 
#### What is a Module 
My angular app is divided into small small containers these are called as Angular Modules 
Modules are continers 
now how do we divide these modules for example of a e-commerce website 
we have Auth Module or User Module which would have all the login and signup forms next could be products ka crud module products ka curd operations Application would be divided Logically into Modules
Each Person Should be divided into different Modules so no confilicts can happen 
#### What is a Component
Our Screen is Divided into various components and like footer,  cards, heading and stuff
Like for eg if we talk about login so login ka component/ screen would be in a module now even registration that would also be in same module ie of **AUTH** in this way my screen is divided into smaller chunks and these chunks are called as components and they are all part of one module componets are a part of module 
whats a stand alone component is the component that are not a part of any module 
React also works on components hence its a component based arch 
#### What are Services 
backend se Data lana ke kaam and sharing that data to various components and modules is done by Services Amodule and Bmodule now they have to share some data that is done by services 

#### What are Dependency Injection
Services are injected via Dependency injection its used in react and all will study indepth in future 

#### Linking and The Layers 
It automatically is linked to Html Css and Ts like we used to link them abhi vo nhi hai 
It has app.component.html and app.component.css and app.component.ts which are interlinked to run it we go in component ka html and terminal pe we write ng serve that runs the thing and for extra ie for testing we also have a spec file that is used for testing  

#### One Way / Two Way Data Binding ( Data Inter-Polation)
##### One Way Data Binding ( data From Ts to html )
pelhe we declare the variable in ts and inside export class we declare now to display that we use {{}}
and just write the variable name now since angular is a framework we have to follow the convetion example agar Form banaya and waha se it goes from html to type Script and from ts ka variable hai waha se html jana is also one way data binding 
##### Two Way Data Binding 
to be done 

### Working Flow of Angular
#### Angular.Json
Before Running anything i need a config file ? so for running the config we run angular.json 
now angular.json file has the paths of our three main files ts css and html that is to be rendered first. after ng serve it goes to angular.json now in 'options' theres a main.ts file that tells to start from there 

pelhe after we do ng serve itgoes to -> angular.js from there it will search -> main.ts ( jisse usko pata chale kaha se start karna hai ) -> yaha se it readies its platform jaha uska server and all run hoga to start on screen. -> yaha se it tells the bootstrap ( chalu karna, dhakka dena , load karna ) kisko? ie our AppModule. -> yaha se vo passhoga apne component ko AppComponent. -> aabhi humko html dikhta hai islye appcomponent mei vo html ko render karta hai now html path kaise aayega ie from our Angular.json mei options mei index mei path hai so waha se leke aayega 
 **and islye whatever we were doing in app.component that was being shown in html file**

so my bahar wala index.html has `<app-root></app-root>` and this is why angular is 
SPA ( Single page Application) and hence it renders only in single page because it gives a feel of a faster application therefore React and Angular Both are used a lot 
### Modules 
now everything is gonna be ng because ng is angular ngmodule defines metadata we use decorator like @NgModule that tells about the further code. inside the decorator we have declarations. which tells within the give module which all components we have like in @Ngmodule we have Appcomponent 
Now is imports jismei we import stuff ie of one module i need to another it has browserModule ie to show on screen it needs that module  it also needs AppRoutingModule 

#### More About Modules 

Imports Exports and Declarations imp!
**Creating a module** ng(angular) g(generate) m(module) module_name
and after doing that you will automatically get the products ka module in src-app-product-(its module)
now after this the most imp is to Register it if you dont it may or maynot work so for registering go in app.module.ts usmie inside imports just write ProductsModule and ho jayega. now aabtak you dont have any component except app.component so islye the decleration: [] is empty
it would apne aap import the basic module ie CommonModule jo apne aap aata hai for basic stuff like if else.
**Creating a Component** ng g c foo 
the command would create a new component and update the module ka decleration block so if you want a component inside a specific module the command would be 
**Creating a Component inside a specific module** ng g c module_name/component_name 
in our product case we have ng g c products/list 

### Components 
 components have 4 files 
 - HTML
 - CSS
 - SPEC
 - TS
 now in html no head body required sirf body ke aandar jo likhna hai voi aayega directly html code aayega eventually and indirectly it will run the index.html file itself neither of the html file only content required 
 and the Css which have scss lscc and you can choose whatevery styling you want 
 spec is a texting file 
 ts file a place where component ka class banega again decorated with a decorated with @Component which has its meta data inside it now just because of its meta data all the 4 files are Linked 
 
```
@Component({

  selector: 'app-product-list',

  templateUrl: './product-list.component.html',

  styleUrls: ['./product-list.component.css']

})
```
template url which tels which template is to be rendered ie when this file is being run to template mei kaunsa html render karna hai that url has to be here its also a relative url 
Style Url is an array  which means u can add multiple style urls now just because of the meta data provided your decorator is smart enough to load all the links and your component just because of @Component which is internally logic written by the framework itself now whats a selector lets see 
now for this forget about products module focus on app module 
in app module we have app component now defaultly humko app.component ka page dikhta hai now to use the components of others which are a part of the same module ie app module only we use the help of its selector and which the help of that we paste that in the html tag format which loads all the other components you want to provide along with that all the direct written html tags also work the example of thus is 

```
<p> Hello </p>
<app-foo></app-foo>
<app-test></app-test> 

```
one component mei you can render multiple chote chote component can create a component of navbar and a component of footer these both module will belong in which module? ie a shared module because its the same to everywhere ie we can render ek component ke aandar aur bhi dusere components 
Agar Same Modules nhi hai to Import Export Aayega 
Components are Exported Modules are Imported 
### Learned About Structural Directives 

assume an array of products now lets see how we use it rather than innerHtml tells kitna bar repeate hogga? tells the structure of the element 
```
<p>product-list works!</p>

  

<table>

    <tr *ngFor="let product of productData">

        <td>{{product.productId}}</td>

        <td>{{product.productName}}</td>

        <td>{{product.productCategory}}</td>

        <td>{{product.productPrice}}</td>

        <td>{{product.productRating}}</td>

    </tr>

</table>
```
the html where we do this! 
more about directives 
```
<p>product-list works!</p>

<table>

    <tr *ngFor="let product of productData">

        <td>{{product.productId}}</td>

        <td>{{product.productName}}</td>

        <td>{{product.productCategory}}</td>

        <td>{{product.productPrice}}</td>

        <td>{{product.productRating}}</td>

        <td><button (click)="selectProduct(product)">View More</button></td>

    </tr>

</table>

  

<div *ngIf="selectedProduct">

        <p>{{selectedProduct.productId}}</p>

        <p>{{selectedProduct.productName}}</p>

        <p>{{selectedProduct.productCategory}}</p>

        <p>{{selectedProduct.productPrice}}</p>

        <p>{{selectedProduct.productRating}}</p>

  

</div>

THE TS PART IDHAR SE HAI 
selectedProduct:any;

  

    selectProduct(product:any){

  

      this.selectedProduct = product

      console.log(this.selectedProduct)

  

    }
```