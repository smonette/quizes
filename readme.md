#Javascript Quiz - Sept 15


##Questions

Make a `Person` constructor with attributes: `name:string`, `height:string`, `age:number`, `sleeping:boolean`.

```
var Person = function(name, height, age) {
	this.name = name;
	this.height = height;
	this.age = age;
	this.sleeping = true;
}

```

Add prototype methods to `person`: `eat`, `sleep`, and `wakeUp`. (The `sleep` and `wakeUp` methods should toggle `sleeping` to `true/false`, and `eat` should return an eating noise.)

```
Person.prototype.eat = function(){
	console.log("Om nom nom");
}
Person.prototype.sleep = function(){
	if(this.sleeping === false) {
		this.sleeping = true;
	} else {
		alert(this.name + " is already sleeping.")
	}
}
Person.prototype.wakeup = function(){
	if(this.sleeping === true) {
		this.sleeping = false;
	} else {
		alert(this.name + " is already awake.")
	}
}
```


Make a `Student` prototype that inherits from `person` and has the additional attribute of `studying:boolean`.

```
var Student = function(name, height, age){
	this.name = name;
	this.height = height;
	this.age = age;
	this.studying = true;
}
Student.prototype = new Person();
Student.prototype.constructor = Student;

```


Add methods to `Student` called `study`, and `stopStudy` to toggle `studying`

```
Student.prototype.study = function(){
	if(this.studying === false) {
		this.studying = true;
	} else {
		alert(this.name + " is already studying.")
	}
}
Student.prototype.stopStudy = function(){
	if(this.studying === true) {
		this.studying = false;
	} else {
		alert(this.name + " already stopped studying.")
	}
}

```

Override the `sleep` method on `student` to only run `sleep` if `studying` is `false`.

```
Student.prototype.sleep = function(){
	if ((this.studying === false) && (this.sleeping === false)){
		this.sleeping = true;
	} else {
		alert("Can't sleep, must study!")
	}
}

```
