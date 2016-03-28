# JavaScript Snippets for Sublime

![Demo](https://cloud.githubusercontent.com/assets/13405318/14079717/9e54ccd0-f4f7-11e5-8a57-928883aeb973.gif)

## Install

To install through [Package Control](https://packagecontrol.io/),
search for **EON JS Snippets**. If you still don't have Package Control in Sublime Text, [go get it](https://packagecontrol.io/installation).
It's pure awesomeness.

If you prefer to install it manually, you can download the package and put it inside your `Packages` directory. It should work but will not update automatically.

## Timing Object

### [Timing] Timing.RegisterEvent('ONCE

```javascript
Timing.RegisterEvent('ONCE', time, null, function() {
	
	// do something once at time.
});
```

### [Timing] Timing.RegisterEvent('OVER

```javascript
Timing.RegisterEvent('OVER', time, null, function() {
	
	// do something every frame over time.
});
```

### [Timing] Timing.RegisterEvent('OVER_EVERY

```javascript
Timing.RegisterEvent('OVER_EVERY', time, every, null, function() {
	
	// do something every x seconds over time.
});
```

### [Timing] Timing.RegisterEvent('EVERY

```javascript
Timing.RegisterEvent('EVERY', time, null, function() {
	
	// do something every x seconds.
});
```

### [Timing] Timing.RegisterEvent('FRAME

```javascript
Timing.RegisterEvent('FRAME', null, function() {
	
	// do something every frame.
});
```

## Global Actions 

### [GA.setField] GA.setField

```javascript
GA.setField('node', 'field', value);
```

### [GA.getField] GA.getField

```javascript
GA.getField('node', 'field');
```

### [GA.getNode] GA.getNode

```javascript
GA.getNode('node');
```

### [GA.setProperty] GA.setProperty

```javascript
GA.setProperty('property', value, object);
```

## GetTarget Object

### [GetTarget] GetTarget

```javascript
var MainClick = GetTarget('node');

function On_Click() {

	// call the .target method and assign it to a variable
  	var pTarget = MainClick.target();

  	// use .parent to access the nth parent and .name to access the name of the node 
  	switch(pTarget.parent(1).name) {

    case 'match 1':
      // do something
    break;

    case 'match 2':
      // do something
    break;

    case 'match 3':
      // do something
    break;

    default:
      // default case
    break;
  }
}
```

## Wandifier Object

### [Wandifier] Wandifier

```javascript
var wand = Wandifier('node', countDown, wandFunc, true);

function wandFunc(target) {

	// log out current targets name
    console.log(target);


    switch(target.name) {

    	case 'match 1':
	      // do something
	    break;

	    case 'match 2':
	      // do something
	    break;

	    case 'match 3':
	      // do something
	    break;

	    default:
	      // default case
	    break;

    }
}
```

### [Wandifier EP] Wandifier Extended Parameters

```javascript
var wand = Wandifier('node', countDown, wandFunc, true, 'Reticle', scaleTo, scaleFrom);

function wandFunc(target) {

	// log out current targets name
    console.log(target);


    switch(target.name) {

    	case 'match 1':
	      // do something
	    break;

	    case 'match 2':
	      // do something
	    break;

	    case 'match 3':
	      // do something
	    break;

	    default:
	      // default case
	    break;

    }
}
```

### [countDown] .countDown

```javascript

// To view value
wand.countDown;

// To change value
wand.countDown = 1.5;

```

### [intersected] .intersected

```javascript

//check if wand is intersecting
wand.intersected

```

### [exclude] .exclude

```javascript
// exclude single shape
wand.exclude('Box1_Shape');

// or multiple shapes
wand.exclude(['Box1_Shape','Box2_Shape']);

```

### [reticleExclude] .reticleExclude

```javascript
// exclude single shape
wand.reticleExclude('Box1_Shape');

// or multiple shapes
wand.reticleExclude(['Box1_Shape','Box2_Shape']);

```

### [removeExclude] .removeExclude

```javascript
// remove single shape
wand.removeExclude('Box1_Shape');

// or multiple
wand.removeExclude(['Box1_Shape','Box2_Shape']);

// or all
wand.removeExclude('ALL');

```

### [removeReticleExclude] .removeReticleExclude

```javascript
// remove single shape
wand.removeReticleExclude('Box1_Shape');

// or multiple
wand.removeReticleExclude(['Box1_Shape','Box2_Shape']);

// or all
wand.removeReticleExclude('ALL');

```

### [reset] .reset

```javascript
// removes all exclusions and resets wandifier
wand.reset;

```

## Update 

### [Update.add] Update.add

```javascript
Update.add(function() {

	// something to update every frame
});
```

### [Update.clear] Update.clear

```javascript
Update.clear();
```

## Console

### [console.log] console.log

```javascript
console.log('message');
```

### [console.list] console.list

```javascript
console.list(object);
```

## Alert

### [alert] alert

```javascript
alert('message', 'title');
```




## License

[MIT License]
The MIT License (MIT)
Copyright (c) 2016 Jaymie Timperley <jaymie.timperley@eonreality.com>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.