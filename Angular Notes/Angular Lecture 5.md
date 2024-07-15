
Creating a service ng g s modulename/service-name 
now the static data is coming from ts but we will shift that to service jo mere liye layega static data now data can be from backend but since we learning frontend we will get the data from services 
## Injecting the Data 
now i have a class employeeListComponent this class needs a service html -app-employee-list-obejctbana need service ka obj kaise hoga injector se employeelistcomp ke 

SO lets see what injection is now in our employee module we have employee-list as our component thike now what service does is it creates an object of it and object banake pool mei dal dega now from there any component calles the object and the function written in the service waha se data layega to the component calling this is injection,
ngoninit ngdestory

ALWAYS REMEMBER COMPONENT EXPORT MODULE IMPORT 
```
employeeData:any;

  constructor(private employeeService:EmployeeService){ //IN THIS ISNE EMPLOYEESERVICE KA MEMBER VARIABLE BANA DIYA JUST BECAUSE U USED ACCESS SPECIFIER 

    this.employeeData = this.employeeService.getEmployeeData()

  }
```

## Routing 
while creating a app it asks you for a rounting module yes or na and we put yes so it gives us app.routing.module in which we get a RoutingModule which actually handles all the path and stuff of all the pages we add our path and component in the array and it registers it there ie creates an object of it there and then we export the RouteModule ke whenever others have to use they use the RouteModule to get to the req location 

html app ke usmei we write <router-outlet></router-outlet>```
 <router-outlet></router-outlet>
 which loads all the required component in the html of app ```

 **WILD CARD ROUTE**
in my localhost if i put /employee or /stocks it was taking me there agar koi non exist cheez dalde to it will route you to the wild card wala page ie in shared module 
in the Route Module ka Array ORDER MATTERS so agar wild card wala dal diya pelhe no going back ho jayega 