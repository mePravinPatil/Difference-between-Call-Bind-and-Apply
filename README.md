# Difference-between-Call-Bind-and-Apply
Call( ): 
	1. The call() method invokes a function with a given 'this' value and arguments provided one by one. This means that we can call any function, and explicitly specify what 'this' should reference within the calling function.
	2. call() calls the function with (this or custom object) as the first parameter then function parameters if exist are passed one by one and returns the value of execution.
	Example : 
		//Demo with javascript .call()
			var obj = {name:"John"};
			var greeting = function(a,b,c){
    			return "welcome "+this.name+" to "+a+" "+b+" in "+c;
			};

			console.log(greeting.call(obj,"Newtown","KOLKATA","WB"));
			// returns output as welcome John to Newtown KOLKATA in WB

Apply( ): 
	1. Invokes the function and allows you to pass in arguments as an array.
	2. apply() is the same as call() except that it takes the parameters as any array
	Example : 
		//Demo with javascript .apply()
			var obj = {name:"John"};
			var greeting = function(a,b,c){
    			return "welcome "+this.name+" to "+a+" "+b+" in "+c;
			};
			// array of arguments to the actual function
			var args = ["Newtown","KOLKATA","WB"];  
			console.log("Output using .apply() below ")
			console.log(greeting.apply(obj,args));
			/* Will output 
 			welcome John to Newtown KOLKATA in WB */

Bind(): 
	1. Returns a new function, allowing you to pass in an array and any number of arguments.
	2.  it creates a new function with a given this value, and returns that function without executing it.
	Example :
		//Use .bind() javascript
			var obj = {name:"John"};
			var greeting = function(a,b,c){
   			 return "welcome "+this.name+" to "+a+" "+b+" in "+c;
			};
			//creates a bound function that has same body and parameters 
			var bound = greeting.bind(obj);   // this will return a function bound()
			// calling bound()
			console.log("Output using .bind() below ");
			console.log(bound("Newtown","KOLKATA","WB")); //call the bound function
			/* will output
			welcome John to Newtown KOLKATA in WB */
