# JavaScript Snippets for Sublime

![Demo](https://cloud.githubusercontent.com/assets/13405318/14079717/9e54ccd0-f4f7-11e5-8a57-928883aeb973.gif)

## Install

To install through [Package Control](https://packagecontrol.io/),
search for **EON JS Snippets**. If you still don"t have Package Control in Sublime Text, [go get it](https://packagecontrol.io/installation).
It"s pure awesomeness.

If you prefer to install it manually, you can download the package and put it inside your `Packages` directory. It should work but will not update automatically.

## Timing Object

### Timing.RegisterEvent("```ONCE```

```javascript
Timing.registerEvent("ONCE", time, null, function() {
	
	// do something once at time.
});
```

### Timing.registerEvent("```OVER```

```javascript
Timing.RegisterEvent("OVER", time, null, function() {
	
	// do something every frame over time.
});
```

### Timing.registerEvent("```OVER_EVERY```

```javascript
Timing.RegisterEvent("OVER_EVERY", time, every, null, function() {
	
	// do something every x seconds over time.
});
```

### Timing.registerEvent("```EVERY```

```javascript
Timing.RegisterEvent("EVERY", time, null, function() {
	
	// do something every x seconds.
});
```

### Timing.registerEvent("```FRAME```

```javascript
Timing.RegisterEvent("FRAME", null, function() {
	
	// do something every frame.
});
```

## Global Actions 

### GA.```setField```

```javascript
GA.setField("node", "field", value);
```

### GA.```getField```

```javascript
GA.getField("node", "field");
```

### GA.```getNode```

```javascript
GA.getNode("node");
```

### GA.```setProperty```

```javascript
GA.setProperty("property", value, object);
```

### GA.```find```

```javascript
GA.find("name", root, depth);
```

### GA.```findByProgID```

```javascript
GA.findByProgID("id", root, depth);
```

### GA.```addField```

```javascript
GA.addField("field");
```

## Transform

### Transform.```position```

```javascript
Transform.position("node", [position], time);
```

### Transform.```orientation```

```javascript
Transform.orientation("node", [orientation], time);
```

### Transform.```scale```

```javascript
Transform.scale("node", [scale], time);
```

### Transform.```other```

```javascript
Transform.other("node", "field", value, time);
```

### Transform.```rotate```

```javascript
Transform.rotate("node", [axis], laptime, state);
```

### Transform.```position``` *with callback*

```javascript
Transform.position("node", [position], time, function() {
    // do something
});
```

### Transform.```orientation``` *with callback*

```javascript
Transform.orientation("node", [orientation], time, function() {
    // do something
});
```

### Transform.```scale``` *with callback*

```javascript
Transform.scale("node", [scale], time, function() {
    // do something
});
```

### Transform.```other``` *with callback*

```javascript
Transform.other("node", "field", value, time, function() {
    // do something
});
```

### ```.pause```

```javascript
var TRANSFORM_EVENT = Transform.other("node", "field", value, time, function() {
    // do something
});

TRANSFORM_EVENT.pause();
```

### ```.resume```

```javascript
var TRANSFORM_EVENT = Transform.other("node", "field", value, time, function() {
    // do something
});

TRANSFORM_EVENT.resume();
```

### ```.cancel```

```javascript
var TRANSFORM_EVENT = Transform.other("node", "field", value, time, function() {
    // do something
});

TRANSFORM_EVENT.cancel();
```

## Node Object

### .```name```

```javascript
var box = GA.getNode("Box1");

eon.Trace(box.name);
// Box1
```

### .```ref```

```javascript
var box = GA.getNode("Box1");

eon.Trace(box.ref);
// returns a reference to the current node.
```

### .```path```

```javascript
var box = GA.getNode("Box1");

box.path
// Simulation!Scene!_PUT-YOUR-SCENE-HERE_!Box1
```

### .```count```

```javascript
var box = GA.getNode("Box1");

box.count;
// 2
```

### .```start```

```javascript
var box = GA.getNode("Box1");

box.start;
```

### .```stop```

```javascript
var box = GA.getNode("Box1");

box.stop;
```

### .```getField```

```javascript
var box = GA.getNode("Box1");

box.getField("Position").value;

//parameters
.getField(field, debug, source);

.getField("SetRun", "DEBUG", "ClickSensor function");
```

### .```setField```

```javascript
var box = GA.getNode("Box1");

box.setField("Position",[5,5,5]);

//parameters
.setField(field, setvalue, debug, source);

.setField("SetRun", true, "DEBUG", "ClickSensor function");
```

### .```getFieldById```

```javascript
var box = GA.getNode("Box1");

box.getFieldById(7).value;
// returns the value of the nodes 7th field (position in this case)
```

### .```setFieldById```

```javascript
var box = GA.getNode("Box1");

box.setFieldById(7, [9,9,9]);
// sets the value of the nodes 7th field (position in this case) to 9,9,9
```

### .```parent```

```javascript
// using eon methods
var box     = eon.FindNode("Box1");
var parent4 = box.GetParentNode().GetParentNode().GetParentNode().GetParentNode();


// using library
var box = GA.getNode("Box1");

box.parent(4);
// returns the nodes 4th parent

box.parent();
// if no argument is given the first parent will be returned.
```

### .```parentName```

```javascript
// using eon methods
var box     = eon.FindNode("Box1");
var parent4 = box.GetParentNode().GetParentNode().GetParentNode().GetParentNode();
var name    = eon.GetNodeName(parent4);


// using library
var box = GA.getNode("Box1");

// acessing name after accesing nth parent
box.parent(4).name;

// accessing nth parent and returning name directly
box.parentName(4);
```

### .```parentRef```

```javascript
// using eon methods
var box     = eon.FindNode("Box1");
var parent4 = box.GetParentNode().GetParentNode().GetParentNode().GetParentNode();


// using library
var box = GA.getNode("Box1");

// acessing ref after accesing nth parent
box.parent(4).ref;

// accessing nth parent and returning ref directly
box.parentRef(4);
```

### .```child```

```javascript
// using eon methods
var box     = eon.FindNode("Box1");
var treeCh  = box.GetFieldByName("TreeChildren");
var child1  = treeCh.GetMFElement(0);


// using library
var box = GA.getNode("Box1");

box.child(1);
// returns the nodes 1st child.

box.child();
// if no argument is given the first child will be returned.
```

### .```childName```

```javascript
// using eon methods
var box     = eon.FindNode("Box1");
var treeCh  = box.GetFieldByName("TreeChildren");
var child1  = treeCh.GetMFElement(0);
var name    = eon.GetNodeName(child1);


// using library
var box = GA.getNode("Box1");

// acessing name after accesing nth child
box.child(2).name;

// accessing nth child and returning name directly
box.childName(2);
```

### .```childRef```

```javascript
// using eon methods
var box     = eon.FindNode("Box1");
var treeCh  = box.GetFieldByName("TreeChildren");
var child1  = treeCh.GetMFElement(0);


// using library
var box = GA.getNode("Box1");

// acessing ref after accesing nth parent
box.child(4).ref;

// accessing nth parent and returning ref directly
box.childRef(4);
```

### .```fieldCount```

```javascript
var box = GA.getNode("Box1");

box.fieldCount;
// returns 23, the number of field the box1 node has.
```

### .```find```

```javascript
var box = GA.getNode("Box1");

box.find("shape");

box.find("name", depth);
// Returns a collection of node-objects.
```

### .```show```

```javascript
var box = GA.getNode("Box1");

box.show;
// shows the box
```

### .```hide```

```javascript
var box = GA.getNode("Box1");

box.hide;
// shows the box
```

### .```position```

```javascript
var box = GA.getNode("Box1");
// starts with a position of [15,0,0]

box.position;
// 15,0,0
// returns the value of the current nodes position

box.position.x;
// 15
// returns the value of the current nodes x position

box.position = [43,2,19];
// changes position

box.position;
// 43,2,19

box.position.x = 4;
// changes the value of the x axis only
```

### .```orientation```

```javascript
var box = GA.getNode("Box1");
// starts with a orientation of [3,6,9]

box.orientation;
// 3,6,9
// returns the value of the current nodes orientation

box.orientation.y;
// 6
// returns the value of the current nodes y orientation

box.orientation = [7,14,21];
// changes orientation

box.orientation;
// 7,14,21
```

### .```scale```

```javascript
var box = GA.getNode("Box1");
// starts with a scale of [1,1,1]

box.scale;
// 1,1,1
// returns the value of the current nodes scale

box.scale.z;
// 1
// returns the value of the current nodes z scale

box.scale = [2,2,2];
// changes scale

box.scale;
// 2,2,2
```

### .```hidden```

```javascript
var box = GA.getNode("Box1");

box.hidden;
// returns false

box.hidden = true;
// hides the box frame
```

### .```worldPosition```

```javascript
var box = GA.getNode("Box1");
// starts with a worldPosition of [15,0,0]

box.worldPosition;
// 15,0,0
// returns the value of the current nodes worldPosition

box.worldPosition.x;
// 15
// returns the value of the current nodes x worldPosition

box.worldPosition = [43,2,19];
// changes worldPosition

box.worldPosition;
// 43,2,19
```

### .```worldOrientation```

```javascript
var box = GA.getNode("Box1");
// starts with a worldOrientation of [3,6,9]

box.worldOrientation;
// 3,6,9
// returns the value of the current nodes worldOrientation

box.worldOrientation.y;
// 6
// returns the value of the current nodes y worldOrientation

box.worldOrientation = [7,14,21];
// changes worldOrientation

box.worldOrientation;
// 7,14,21
```

### .```worldScale```

```javascript
var box = GA.getNode("Box1");
// starts with a worldScale of [1,1,1]

box.worldScale;
// 1,1,1
// returns the value of the current nodes worldScale

box.worldScale.z;
// 1
// returns the value of the current nodes z worldScale

box.worldScale = [2,2,2];
// changes worldScale

box.worldScale;
// 2,2,2
```

### .```ambientColor```

```javascript
var box = GA.getNode("Box1");

box.ambientColor = [0.8,0.5,0.3];
// as the box1 node is a frame and does not have an ambientColor field,
// nothing will happen, you will get a log stating the node does not have field (n)


box.child().child(1).ambientColor = [Math.random(),Math.random(),Math.random()];
// This has now accessed the first child which is a shape node,
// and then its 2nd child which is a shaderMaterial
// then it ambientColor field and applied a random value.

test.child().child(1).ambientColor;
// this will log out the current value of the field or null if the node does not have an ambientColor field.

/*  Notes : 
a nodes children always start counting from zero so it"s second child would be 1.
If materials/geometry on shape nodes are often referenced, they will not show up under treechildren.
However the above code should still work.
*/
```

### .```diffuseColor```

```javascript
var box = GA.getNode("Box1");

box.diffuseColor = [0.8,0.5,0.3];
// as the box1 node is a frame and does not have an diffuseColor field,
// nothing will happen, you will get a log stating the node does not have field (n)


box.child().child(1).diffuseColor = [Math.random(),Math.random(),Math.random()];
// This has now accessed the first child which is a shape node,
// and then its 2nd child which is a shaderMaterial
// then it diffuseColor field and applied a random value.

test.child().child(1).diffuseColor;
// this will log out the current value of the field or null if the node does not have an diffuseColor field.

/*  Notes : 
a nodes children always start counting from zero so it"s second child would be 1.
If materials/geometry on shape nodes are often referenced, they will not show up under treechildren.
However the above code should still work.
*/
```

### .```specularColor```

```javascript
var box = GA.getNode("Box1");

box.specularColor = [0.8,0.5,0.3];
// as the box1 node is a frame and does not have an specularColor field,
// nothing will happen, you will get a log stating the node does not have field (n)


box.child().child(1).specularColor = [Math.random(),Math.random(),Math.random()];
// This has now accessed the first child which is a shape node,
// and then its 2nd child which is a shaderMaterial
// then it specularColor field and applied a random value.

test.child().child(1).specularColor;
// this will log out the current value of the field or null if the node does not have an specularColor field.

/*  Notes : 
a nodes children always start counting from zero so it"s second child would be 1.
If materials/geometry on shape nodes are often referenced, they will not show up under treechildren.
However the above code should still work.
*/
```

### .```opacity```

```javascript
var box = GA.getNode("Box1");

box.opacity = 0.3;
// as the box1 node is a frame and does not have an opacity field,
// nothing will happen, you will get a log stating the node does not have field (n)


box.child().child(1).opacity = 0.4;
// This has now accessed the first child which is a shape node,
// and then its 2nd child which is a shaderMaterial
// then it opacity field and applied a random value.

test.child().child(1).opacity;
// this will log out the current value of the field or null if the node does not have an opacity field.

/*  Notes : 
a nodes children always start counting from zero so it"s second child would be 1.
If materials/geometry on shape nodes are often referenced, they will not show up under treechildren.
However the above code should still work.
*/
```

## GetTarget Object

### ```GetTarget```

```javascript
var MainClick = GetTarget("node");

function On_Click() {

	// call the .target method and assign it to a variable
  	var pTarget = MainClick.target();

  	// use .parent to access the nth parent and .name to access the name of the node 
  	switch(pTarget.parent(1).name) {

    case "match 1":
      // do something
    break;

    case "match 2":
      // do something
    break;

    case "match 3":
      // do something
    break;

    default:
      // default case
    break;
  }
}
```

## Wandifier Object

### ```Wandifier```

```javascript
var wand = Wandifier("node", countDown, wandFunc, true);

function wandFunc(target) {

	// log out current targets name
    console.log(target);


    switch(target.name) {

    	case "match 1":
	      // do something
	    break;

	    case "match 2":
	      // do something
	    break;

	    case "match 3":
	      // do something
	    break;

	    default:
	      // default case
	    break;

    }
}
```

### ```Wandifier Extended Parameters```

```javascript
var wand = Wandifier("node", countDown, wandFunc, true, "Reticle", scaleTo, scaleFrom);

function wandFunc(target) {

	// log out current targets name
    console.log(target);


    switch(target.name) {

    	case "match 1":
	      // do something
	    break;

	    case "match 2":
	      // do something
	    break;

	    case "match 3":
	      // do something
	    break;

	    default:
	      // default case
	    break;

    }
}
```

### ```.countDown```

```javascript

// To view value
wand.countDown;

// To change value
wand.countDown = 1.5;

```

### ```.intersected```

```javascript

//check if wand is intersecting
wand.intersected

```

### ```.exclude```

```javascript
// exclude single shape
wand.exclude("Box1_Shape");

// or multiple shapes
wand.exclude(["Box1_Shape","Box2_Shape"]);

```

### ```.reticleExclude```

```javascript
// exclude single shape
wand.reticleExclude("Box1_Shape");

// or multiple shapes
wand.reticleExclude(["Box1_Shape","Box2_Shape"]);

```

### ```.removeExclude```

```javascript
// remove single shape
wand.removeExclude("Box1_Shape");

// or multiple
wand.removeExclude(["Box1_Shape","Box2_Shape"]);

// or all
wand.removeExclude("ALL");

```

### ```.removeReticleExclude```

```javascript
// remove single shape
wand.removeReticleExclude("Box1_Shape");

// or multiple
wand.removeReticleExclude(["Box1_Shape","Box2_Shape"]);

// or all
wand.removeReticleExclude("ALL");

```

### ```.reset```

```javascript
// removes all exclusions and resets wandifier
wand.reset;

```

### ```.continuous```

```javascript
// Allows you to continuous click targets.
wand.continuous = true;

```

### ```.selectAndClick```

```javascript
Turn on the selectAndClick Mode.
wand.selectAndClick(true,Click);

```

### ```.ease```

```javascript
Select ease type to apply to reticle animation.
wand.ease = "easeoutback";

```

## Update 

### Update.```add```

```javascript
Update.add(function() {

	// something to update every frame
});
```

### Update.```clear```

```javascript
Update.clear();
```

## Console

### console.```log```

```javascript
console.log("message");
```

### console.```list```

```javascript
console.list(object);
```

## Alert

### ```alert```

```javascript
alert("message", "title");
```

## AudioController Object

### ```AudioController```

```javascript
var Audio = AudioController("AudioGroup");
```

## AnimationController Object

### ```AnimationController```

```javascript
var Animation = AnimationController("AnimationGroup");
```


## License

[MIT License]
The MIT License (MIT)
Copyright (c) 2016 Jaymie Timperley <jaymie.timperley@eonreality.com>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.