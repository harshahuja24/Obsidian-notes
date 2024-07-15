## Learning Reactive Form
in ts file we need to bind someting so we create a new apana form control 
OBSERVABLE: STREAM OF DATA 
ngModel is heave and hence reactive form we use apna khud ka form control banaya which internally uses observable. **validator:'required'**

Template driven would make changes keep it in a place and the exchange the data but in Reactive forms mei it does directly and that is why we use reactive forms and in templateDriven the ngModel is heavy. Most of the logic is written in ts

in ngModel the workflow is html -- Data Buffer(Json Converted and Form Control Instance ) -- Ts
while in FormControl everything is been done in ts and is directly hitted to html and vice versa.
For one or two inputs we use mostly tenplate driven forms because reactive mei we need to write a lot of code while if the form is big we use reactive to get the data and reduce the work load 

## Creating our own FormControl and Group 
```
  

  registerForm = new FormGroup({

    username: new FormControl('',[Validators.required, Validators.minLength(5)]),

    email: new FormControl('',[Validators.required, Validators.email]),

    password: new FormControl(),

    address: new FormControl(),

    gender: new FormControl(),

    branch: new FormControl()

  

  })
```

in the above we are just creating an object of formgroup and in that we have formcontrol validators which is our step for creating a reactive based form. 


## ngOnInit

```
ngOnInit(){

    console.log("Hello in ngOninit")

    this.registerForm.valueChanges.subscribe((value:any)=>{

      console.log(this.registerForm)

      console.log(value)
    })
  }
```
as we can see that we are subscribing the content which shows us that it is an observable and ngOninit only runs one time it is something that is called while our component is loaded the ngOnInit is being loaded first then!
## SET VALUES VS PATCH VALUES 

set requires all the keys else error while patch wont as much whatever you provide it will give. 

```
  // this.registerForm.setValue({

    //   username:"xyz@123456",

    //   email:"xyz@gmail.com",

    //   password:"",

    //   address:"101, Defailsysbssb",

    //   gender:"female",

    //   branch:"AIDS"

    // })
```

### Patch Values 
```
  // this.registerForm.patchValue({

    //   username:"abcd@123",

    //   email:"Fasct@123"

    // })
```



