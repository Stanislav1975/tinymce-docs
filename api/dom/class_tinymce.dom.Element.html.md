---
layout: default
title: tinymce.dom.Element
---

|  |  |
| --- | --- |
| Namespace | tinymce.dom |
| Class | Element |

Element class, this enables element blocking in IE. Element blocking is a method to block out select blockes that gets visible though DIVs on IE 6 it uses a iframe for this blocking. This class also shortens the length of some DOM API calls since it's bound to an element.      

**Example**  

## Public Methods

| Method | Defined By |
| --- | --- |
| [Element](#element)(id:String, settings:Object) : Constructs a new Element instance. | Element |
| [getSize](#getsize)():Object : Returns the size of the element by a object with w and h fields. | Element |
| [getXY](#getxy)():Object : Returns the absolute X, Y cordinate of the element. | Element |
| [moveBy](#moveby)(x:Number, y:Number):void : Moves the element relative to the current position. | Element |
| [moveTo](#moveto)(x:Number, y:Number):void : Moves the element to a specific absolute position. | Element |
| [on](#on)(n:String, f:function, s:Object):function : Adds a event handler to the element. | Element |
| [resizeBy](#resizeby)(w:Number, h:Numner):void : Resizes the element relative to the current sizeto a specific size. | Element |
| [resizeTo](#resizeto)(w:Number, h:Numner):void : Resizes the element to a specific size. | Element |
| [update](#update)(k:String):void : Updates the element blocker in IE6 based on the style information of the element. | Element |

## Method details

### Element 

***public function Element(id:String, settings:Object)***  
Constructs a new Element instance. Consult the Wiki for more details on this class.      

**Parameters**  

| Param | Detail |
| --- | --- |
| id:String | Element ID to bind/execute methods on. |
| settings:Object | Optional settings name/value collection. |

### getSize 

***public function getSize():Object***  
Returns the size of the element by a object with w and h fields.      

**Returns**  
Object - Object with element size with a w and h field.

### getXY 

***public function getXY():Object***  
Returns the absolute X, Y cordinate of the element.      

**Returns**  
Object - Objext with x, y cordinate fields.

### moveBy 

***public function moveBy(x:Number, y:Number):void***  
Moves the element relative to the current position.      

**Parameters**  

| Param | Detail |
| --- | --- |
| x:Number | Relative X cordinate of element position. |
| y:Number | Relative Y cordinate of element position. |

### moveTo 

***public function moveTo(x:Number, y:Number):void***  
Moves the element to a specific absolute position.      

**Parameters**  

| Param | Detail |
| --- | --- |
| x:Number | X cordinate of element position. |
| y:Number | Y cordinate of element position. |

### on 

***public function on(n:String, f:function, s:Object):function***  
Adds a event handler to the element.      

**Parameters**  

| Param | Detail |
| --- | --- |
| n:String | Event name like for example "click". |
| f:function | Function to execute on the specified event. |
| s:Object | Optional scope to execute function on. |

**Returns**  
function - Event handler function the same as the input function.

### resizeBy 

***public function resizeBy(w:Number, h:Numner):void***  
Resizes the element relative to the current sizeto a specific size.      

**Parameters**  

| Param | Detail |
| --- | --- |
| w:Number | Relative width of element. |
| h:Numner | Relative height of element. |

### resizeTo 

***public function resizeTo(w:Number, h:Numner):void***  
Resizes the element to a specific size.      

**Parameters**  

| Param | Detail |
| --- | --- |
| w:Number | New width of element. |
| h:Numner | New height of element. |

### update 

***public function update(k:String):void***  
Updates the element blocker in IE6 based on the style information of the element.      

**Parameters**  

| Param | Detail |
| --- | --- |
| k:String | Optional function key. Used internally. |