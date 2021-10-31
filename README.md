# sevenSegment
A simple approach to building a seven segmented display without complicated canvas routines or font flicker. It supports characters `0 1 2 3 4 5 6 7 8 9 : .` and `space`.

This code is a quick and dirty class I built to solve a problem in one of my own apps. I thought it might help someone else :-)

## Useage
Reference `segment.css` and `segment.js` in your html. See the demo for example code.

Create a new seven segment object with just a few lines of code. Be sure the segment variable is available to the entire scope of your application so you can update the time.

```javascript

/* params
	 container: the id of your container (default: body)
	 map: the layout map using 8's and colons
	 val: the inital value (be sure all values match the map)
*/
var segment = new SevenSegment({
	container: '#display', 
	map: '88:88',	
	val: '00:00'
});
```
Use the `valChange` method to update the display.


```javascript
var x = 0
setInterval(() => {

	/* valChange is updated every second  
	BE SURE the value you pass matches the 
	map you defined 
	
	e.g. 88:88 would be a value like 12:02 */
	segment.valChange('12:0' + x);
	if (x == 9) {
		x = 0;
	} else {
		x++;
	}
}, 1000);
```

