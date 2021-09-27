# ImmutableJavaScriptObject
Learning JS


```javascript
/**
* @Description: Function does not allow argumented object to mutate, delete properties and add more properties
* @Parameter : Function accepts an argument of type 'object'
*/ 
const stabliseObject = (obj) => {
	if (obj.constructor.name !== 'Object') return "Passed argument should be an Object!";
	Object.freeze(obj);
}

/**
* @Description: Function does not allow argumented object add more properties but allow properties value modifications
* @Parameter : Function accepts an argument of type 'object'
*/ 
const immutableObject = (obj) => {
	if (obj.constructor.name !== 'Object') return "Passed argument should be an Object!";
	Object.seal(obj);
}

/**
* @Description: Function shows if the following key exists or not
* @Parameter : Function accepts an argument of type 'object' and type string
*/ 
const checkProperty = (obj,property) => {
	if (obj.constructor.name !== 'Object') return "Passed argument should be an Object!";
	if (obj.constructor.name !== 'String') return "Passed argument should be an Object!";
	console.log(obj.hasOwnProperty(property)? `${property}: key exists`:  `${property}: key does not exists`);
}

// Initializing a obj with name and age properties
let obj = {name:"Cal",age: 22};
console.log(obj); //  o/p { name: 'Cal', age: 22}

// Adding a new property 'class' in obj
obj.class = "Pokemon Electric Type";
console.log(obj); // o/p { name: 'Cal', age: 22, class: "Pokemon Electric Type"}

// Calling a immutableObject function to make object immutable
immutableObject(obj);
console.log(obj); // o/p { name: 'Cal', age: 22, class: "Pokemon Electric Type"}

// Modifying the name property of object
obj.name = "Pikachu";
console.log(obj); // o/p { name: 'Pikachu', age: 22, class: "Pokemon Electric Type"}

obj.attack = "Thunder Bolt";
console.log(obj); // o/p { name: 'Pikachu', age: 22, class: "Pokemon Electric Type"}

// Cheking if 'name' key exists in obj
checkProperty(obj,"name"); // o/p - name: key exists

// Cheking if 'attack' key exists in obj
checkProperty(obj,"attack"); // o/p - attack: key does not exists

// Trying to deete name property 
delete obj.name;
console.log(obj); // o/p { name: 'Pikachu', age: 22, class: "Pokemon Electric Type"}

stabliseObject(obj);
console.log(obj); // o/p { name: 'Pikachu', age: 22, class: "Pokemon Electric Type"}

// Modifying the name property of object
obj.name = "Charizard";
console.log(obj); // o/p { name: 'Pikachu', age: 22, class: "Pokemon Electric Type"}

// Trying to deete name property 
delete obj.name;
console.log(obj); // o/p { name: 'Pikachu', age: 22, class: "Pokemon Electric Type"}

console.log(obj); // o/p { name: 'Pikachu', age: 22, class: "Pokemon Electric Type"}
```
