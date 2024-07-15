## Small Part Of Reactive Angular
Async Operation to get data from backend we need 
Observalbe: jaha pe koi bhi write wala will emmit data and all the subscribers will subscrib to read the data. Observable is something that u used for emmiting data 
Observable is a stream of data that is used to emit data and is used by subscribers to read the data now lets take an example of a pipeline jaha i have multiple observers who have subscribed to my pipeline now if i change the data everywhere it gets updated so this is just a similar part we will learn this in depth futher and it is not at all related to React!!!
below are just words for intro of topic! 
**define**: emmiting the stream of data 2. async operation jikso subscribe usko data 
(subject or BehaviouralObject )

## Observable and its Ghamasan

pelhe we have a module HttpclientModule jiska injector we use to get the data in services since httpCLient is in a different module we need to import it and we created a method to get the data inside the dervice and waha we use .get('api-path') to get the data which returns observable jisko we again return from method but what happens is jis component mei we made service ka injector and the major difference btwn promise and observable is observable is lazy until and unless you dont subscribe you wont get the data while promise irrespective of it vo humko lake dega. 

## Template Form vs Reactive Form 
first plain html form then import forms module ja ang aaya which created directed then html mei we did a variable as #variablename  but while passing it was giving html tags but when we assign it ngForm it gives us json that ng gas given us:
Steps Below Should Be Followed
	1. Create HTML Form
	2. Import FormsModule
	3. Because of FormsModule, we got one directive attached to the form - ngForm
	4. We referenced the form tag with a variable #registerForm
	5. Passed this variable into ts using the submit function
	6. We were able to see HTML form element
	7. Then we passed directive in this variable as - #registerForm="ngForm"
	8. Then we were able to see json in ts