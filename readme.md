#Javascript Prototypes
*Lesson Plan - Nichol Alexander - Aug. 19*   

##Step 1 (5 min)

###Objective

By the end of the lesson, students will be able to use javascript prototypes to add functionality to an object and use prototypal inheritance to create a new object with inherited traits.

###Introduce Topic
*What is about to happen, why, and how?*  
*How will you engage students and capture their interest?*  


**We are going to learn about Javascript Prototypes and how Javascript allows objects to exhibit inheritance behavior.**

###Agenda: 
* 5 min intro, overview
* 5 min pair work
* 5 min recap.

This is one of the most commonly misunderstood things about Javascript, something a lot of people never even think about or deal with in Javascript and without understanding this, you will be missing a critical part of the language and what it can do.  Being comfortable and knowledgable about this is going to help you stand out and kill your javascript projects!

There are a few key things to know about prototypes:    

1. You can use prototypes to add functionality to objects.
2. You can use prototypal inheritance to allow objects to share logical and grouped behavior.
3. Prototypal inheritance and constructors can be used to manage the namespaces of your applications.

LETS DO THIS!

<!--Review:
* What do we know about Inheritance?  
* What is inheritance?  
* How does Ruby handles inheritance?  
* Is JavaScript object oriented language?  -->

###Explain Skill
*How will you explain and demonstrate?*  
*Which potential misunderstandings do you anticipate?*  
*How will you check understanding?*  

Make something new = Person.new vs. new Person

###Make a new object
```
var Person = function (firstName, lastName){
  this.firstName = firstName;
  this.lastName = lastName;
}
```

###Define behavior of object
```
Person.prototype.talk = function (words){
  console.log(words)
}
```
###Create, inherit, construct

```
function President(firstName, lastName, party) {
  Person.call(this, firstName, lastName);
  this.party = party;
}

President.prototype = Object.create(Person.prototype);

President.prototype.constructor = President;
```

###Give President some behavior
```
President.prototype.raiseTaxes = function(){
  console.log("I will not!")
}
```

###Use it!
```
a = new Person("Laura", "Smith");
b = new President("Richard", "Nixon", "GOP")
a.talk("Hello");
b.talk("Hello");
a.party
b.party
a.raiseTaxes();
b.raiseTaxes();
```





##Step 2 (5 min)
*Student-directed pair*

Divide into groups.  Define a new kind of person, aka President,
with an added attribute and some different behavior.

##Step 3 (5 min)
*Assess, debrief, correct*

wrap up and recap
link to future lessons - organize name spaces

