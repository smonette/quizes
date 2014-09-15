#Javascript Quiz - Sept 15


##Questions

1. Make a `Person` constructor with attributes: `name:string`, `height:string`, `age:number`, `sleeping:boolean`.

```
var Person = function(name, height, age, sleeping) {
	this.name = name;
	this.height = height;
	this.age = age;
	this.sleeping = sleeping;
}

```

2. Add prototype methods to `person`: `eat`, `sleep`, and `wakeUp`. (The `sleep` and `wakeUp` methods should toggle `sleeping` to `true/false`, and `eat` should return an eating noise.)

```
Person.prototype.eat = function(){
	console.log("Om nom nom");
}
Person.prototype.sleep = function(){
	sleeping = true;
}
Person.prototype.wakeup = function(){
	sleeping = false;
}
```


3. Make a `Student` prototype that inherits from `person` and has the additional attribute of `studying:boolean`.

```
var Student = function(studying){
	this.studying = studying;
}
Student.prototype = new Person();

```


4. Add methods to `Student` called `study`, and `stopStudy` to toggle `studying`

```
Student.prototype.study = function(){
	studying = true;
}
Student.prototype.stopStudy = function(){
	studying = false;
}

```

5. Override the `sleep` method on `student` to only run `sleep` if `studying` is `false`.

```
Student.prototype.sleep = function(){
	if (studying === false){
		sleeping = true;
	} else {
		alert("Can't sleep, must study!")
	}
}

```
