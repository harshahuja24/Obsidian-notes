## Template Driven Form and its Ness
in template driven form we need to add these paticular attributes 
```
  <label for="username" class="form-label">Username</label>

          <input type="text" class="form-control" id="username" name="username" ngModel>
```
focus on the name attribute in the input section we have to provide it with name so that when ngForm packs my stuff in json it will use the name as the key for the json and there is a necessity to add ngModel to get the data and for ngForm to know that 

## Setting Defaults From Ts to Html and back 
if we see our Ts  and html 
```
          <select class="form-select" id="branch" name="branch"  [(ngModel)]="defaultSelectedValue">
          
```
	the above if we have #[ ] which  single that means only my stuff will be updated in ts but if we do banana in a box ie [()] we get bi-directional changes being made in both html and ts lets see the ts 
```
  defaultSelectedValue = 'CMPN'

  submitForm(register:any){

    console.log(this.defaultSelectedValue)

      console.log(register)

  }
```

this is where default value sets it self in html as well as ts just by using banana thing and we can get data being transfered now lets see a new thing 

## Using ngModel to Move The Data from html <-> Ts
```
<div class="container">

    <div class="row justify-content-center">

      <div class="col-md-8">

        <form class="card" #registerForm="ngForm" (ngSubmit)="submitForm(registerForm)">

          <label for="username" class="form-label">Username</label>

          <input type="text" class="form-control" id="username" name="username" [(ngModel)]="form.username">

          <label for="email" class="form-label">Email</label>

          <input type="email" class="form-control" id="email" name="email" [(ngModel)]="form.email">

          <label for="address" class="form-label">Address</label>

          <textarea class="form-control" id="address" name="address" rows="3" [(ngModel)]="form.address"></textarea>

          <label class="form-label">Gender</label>

          <div class="form-check">

            <input class="form-check-input" type="radio" name="gender" id="male" value="male" [(ngModel)]="form.gender" >

            <label class="form-check-label" for="male">Male</label>

          </div>

          <div class="form-check">

            <input class="form-check-input" type="radio" name="gender" id="female" value="female" [(ngModel)]="form.gender">

            <label class="form-check-label" for="female">Female</label>

          </div>

          <label for="branch" class="form-label">Branch</label>

          <select class="form-select" id="branch" name="branch"  [(ngModel)]="form.branch">

            <option value="cmpn">Cmpn</option>

            <option value="inft">Inft</option>

            <option value="aids">Aids</option>

            <option value="extc">Extc</option>

          </select>

          <div class="text-center">

            <button type="submit" class="btn btn-primary">Submit</button>

          </div>

        </form>

**        {{form | json}}**

      </div>

    </div>

  </div>
```

in the above code u can see we use the [(ngModel)] to transfere the data and set default Data and it can change both ways we also can remove the #registerForm  while passing it to the form tag we also learned about various classes 

```
 form={

    address:"test",

    username:"",

    email:"",

    branch:"",

    gender:""

  }

  // defaultSelectedValue = 'CMPN'

  submitForm(register:any){

  

    console.log(this.form)

    console.log(register)

    // console.log(this.defaultSelectedValue)

    //   console.log(register)

  }
```
*We learned about ngDirty, ngPristine, ngtouched, ngUntouched * with help of these we also make sure that our form has been touched ie clicked the input and went away the ngUntouched becomes ngTouched which are used to check valid entry in form and with that we can notify the user to enter proper details ngPristine and ngDirty is when we write something in the input but user pressed backspace and made the input dirty and also ngValid

## Conditional Style for Username 

```
          <p style="color: red;" *ngIf="registerForm.controls['username']?.touched && registerForm.controls['username']?.invalid">Enter Valid username</p>
```

the above is the example where we use condition of *ngIf 
to get the conditional Style and the input has been given a username of #username variable name 

Hw 
register, login, todo!
