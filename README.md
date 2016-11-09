# Alert7.js
The pure JavaScript plugin. Create the iOS style alerts simply.

![preview-alert7](http://i.imgur.com/1o0uBGL.jpg)

## Usage

### Include file of Alert7.js 

Include **alert7.js** file.

```
<script src="alert7.js"></script>
```

Or minify file with **alert7.min.js**.

```
<script src="alert7.min.js"></script>
```

There has two ways to execute Alert7.js.

### Create static Alert7 

Just use ```Alert7.alert``` method with title attribute. In the moment, There will appear a basic alert with a default button. And return an Alert7-Object. Click button what without handler will just close the alert.

```
Alert7.alert("This is Title");
```

![preview-alert7-a](http://i.imgur.com/VLRxiGx.jpg)

Add content text attribute and change the button letter with third attribute.

```
Alert7.alert("This is Title", "Put some text contents in here", "Got it");
```

Or incloud button handler in the next attribute. Alert will disappear when any button handler completed.

```
Alert7.alert("This is Title", "Put some text contents in here", "Got it", function () {});
```

![preview-alert7-b](http://i.imgur.com/lPIlFNP.jpg)

Append any amount of action buttons. 

```
Alert7.alert("This is Title", "Put some text contents in here", 
	"BUTTON 1", function () {}, 
	"BUTTON 2", function () {}, 
	"BUTTON 3"
);
```

![preview-alert7-c](http://i.imgur.com/8t1WrEV.jpg)

To launch a simple confirm with using ```Alert7.confirm``` method. And return an Alert7-Object too.

```
Alert7.confirm("This is Title", "Put some text contents in here", 
	"BUTTON 1", function () {}, 
	"BUTTON 2", function () {}
);
```

![preview-alert7-e](http://i.imgur.com/UmDl64c.jpg)

### New Alert7-object

Use ```new``` to create an Alert7-Object.

```
var a7Alert = new Alert7();
```

Set title of the Alert7-Object.

```
a7Alert.title = "This is Title";
```

```
a7Alert.setTitle("This is Title");
```

Set text messages of the Alert7-Object.

```
a7Alert.message = "Put some text contents in here";
```

```
a7Alert.setMessage("Put some text contents in here");
```

Add action button to the Alert7-Object.

```
a7Alert.addAction("Got it");
```

```
a7Alert.actions.push({
	title: "Got it"
});
```

With handler.

```
a7Alert.addAction("Got it", function () {});
```

```
a7Alert.actions.push({
	title: "Got it",
	handler: function () {}
});
```

Or set multiple actions with a command with Array.

```
a7Alert.actions = [{
	title: "BUTTON A",
	handler: function () {}
}, {
	title: "BUTTON B",
	handler: function () {}
}, {
	title: "BUTTON C"
}];
```

Present the Alert7-Object.

```
a7Alert.present();
```

![preview-alert7-c](http://i.imgur.com/8t1WrEV.jpg)

Change type for confriming with Alert7 type enumerations. (Enumerations with [Consts](#consts) section)

```
a7Alert.type = Alert7.TYPE_CONFIRM;
```

```
a7Alert.setType(Alert7.TYPE_CONFIRM);
```

Present it. Confirm Alert7 only has two actions at most.

![preview-alert7-d](http://i.imgur.com/hFBx4CY.jpg)

All of action button will close the alert. But it can be broken by called ```Alert7.break``` method in handler.

```
function () {
	Alert7.break();
}
``` 

## Methods

### Alert7.alert

Appear an alert of Alert7 and return Alert7-Object.

```
_a7Obj = Alert7.alert( _titleStr, _messageStr,
	_btn1Str, _btn1Handler,
	_btn2Str, _btn2Handler,
	...	
)
```
_parameter: **\_titleStr:String, \_messageStr:String, \_btn1Str:String, \_btn1Handler:Function...**  / return: **\_a7Obj:Alert7Object**_

---

### Alert7.confirm

Appear an confirm of Alert7 and return Alert7-Object.

```
_a7Obj = Alert7.confirm( _titleStr, _messageStr,
	_btn1Str, _btn1Handler,
	_btn2Str, _btn2Handler
)
```
_parameter: **\_titleStr:String, \_messageStr:String, \_btn1Str:String, \_btn1Handler:Function...**  / return: **\_a7Obj:Alert7Object**_

---

### Alert7.break

Prevent closing alert when an action button is clicked. It can only use at handler **Function**.

```
Alert7.break()
```

---

### setTitle

Set title of Alert7-Object.

```
_a7Obj.setTitle( _titleStr )
```

_parameter: **\_a7Obj:Alert7Object, \_titleStr:String**_

---

### setMessage

Set message of Alert7-Object.

```
_a7Obj.setMessage( _messageStr )
```

_parameter: **\_a7Obj:Alert7Object, \_messageStr:String**_

---

### setType

Set type of Alert7-Object with type enumerations.

```
_a7Obj.setType( _typeEnum )
```

_parameter: **\_a7Obj:Alert7Object, \_typeEnum:Number**_ (Enumerations with [Consts](#consts) section)

---

### addAction

Append an action button for Alert7-Object and what will be handled.

```
_a7Obj.addAction( _text, _handler )
```

_parameter: **\_a7Obj:Alert7Object, \_text:String, \_handler:Function**_

---

### present

Present and show the alert of Alert7-object.

```
_a7Obj.present()
```

_parameter: **\_a7Obj:Alert7Object**_

---

### dismiss

Disappear the alert of Alert7-object.

```
_a7Obj.dismiss()
```

_parameter: **\_a7Obj:Alert7Object**_

---

## Values

### title

Title of the Alert7-Object.

_type: **String**_

---

### message

Message of the Alert7-Object.

_type: **String**_

---

### type

Type of the Alert7-Object with type enumerations.

_type: **Number**_ (Enumerations with [Consts](#consts) section)

---

### actions

JSON list of action data of the Alert7-Object.

_type: **Array**_

---

## Consts

### Alert7.TYPE_DEFAULT
 
Type default enumerations.

_type: **Number**_

---

### Alert7.TYPE_CONFIRM
 
Type confirm enumerations.

_type: **Number**_

---

## Examples

* [Basic](http://wildtyto.github.io/Alert7.js/example/)

## Todo

* Some methods to change style.
* Incloud inputs.
* Incloud template HTML.

## License
Released under the <a href="http://www.opensource.org/licenses/MIT">MIT license</a>.