## Classes

<dl>
<dt><a href="#Core">Core</a></dt>
<dd></dd>
</dl>

## Members

<dl>
<dt><a href="#Core.channels
A namespace object to hold named channels.">Core.channels
A namespace object to hold named channels.</a></dt>
<dd></dd>
</dl>

<a name="Core"></a>

## Core
**Kind**: global class  

* [Core](#Core)
    * [new Core(options)](#new_Core_new)
    * [.typeOf(thing)](#Core.typeOf) ⇒ <code>string</code>
    * [.isUndefined(thing)](#Core.isUndefined) ⇒ <code>boolean</code>
    * [.isNull(thing)](#Core.isNull) ⇒ <code>boolean</code>
    * [.isBoolean(thing)](#Core.isBoolean) ⇒ <code>boolean</code>
    * [.isNumber(thing)](#Core.isNumber) ⇒ <code>boolean</code>
    * [.isString(thing)](#Core.isString) ⇒ <code>boolean</code>
    * [.isDate(thing)](#Core.isDate) ⇒ <code>boolean</code>
    * [.isArray(thing)](#Core.isArray) ⇒ <code>boolean</code>
    * [.isObject(thing)](#Core.isObject) ⇒ <code>boolean</code>
    * [.isFunction(thing)](#Core.isFunction) ⇒ <code>boolean</code>
    * [.assign(target, source, assignFunc)](#Core.assign) ⇒ <code>object</code>
    * [.extend(properties)](#Core.extend) ⇒ <code>object</code>
    * [.channel(name, array)](#Core.channel) ⇒ <code>undefined</code>
    * [.tap(name, func)](#Core.tap) ⇒ <code>undefined</code>
    * [.fire(name, data, callback)](#Core.fire) ⇒ <code>undefined</code>
    * [.plugin(definition, callback)](#Core.plugin) ⇒ <code>undefined</code>

<a name="new_Core_new"></a>

### new Core(options)

| Param | Type | Description |
| --- | --- | --- |
| options | <code>object</code> | instance options. |
| options.name | <code>string</code> | a unique name for the instance. |
| options.plugins | <code>array</code> | an array of plugins to initialize on the instance. |
| options.extend | <code>object</code> | if provided, this object will be merged in to the new instance. |

**Example**  
```js
var core = new Core({
    name: 'client-core',
    plugins: [
        require('./pluginA'),
        require('./pluginB')
    ],
    extend: {
        doStuff(){ ... }
    }
});
```
<a name="Core.typeOf"></a>

### Core.typeOf(thing) ⇒ <code>string</code>
Returns the correct native type in javascript ( unlike the 'typeof' operator ).

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>string</code> - The native javascript type - 'undefined', 'null', 'boolean', 'number', 'string', 'array', 'object' or 'function'.  

| Param | Type | Description |
| --- | --- | --- |
| thing | <code>any</code> | anything you want. |

**Example**  
```js
typeof null; // 'object'
typeof []; // 'object'

core.typeOf(null); // 'null'
core.typeOf([]); // 'array'
```
<a name="Core.isUndefined"></a>

### Core.isUndefined(thing) ⇒ <code>boolean</code>
Checks if a value is undefined.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>boolean</code> - - true if 'thing' is undefined. false otherwise.  

| Param | Type | Description |
| --- | --- | --- |
| thing | <code>any</code> | anything you want. |

**Example**  
```js
core.isUndefined(null); // false
```
<a name="Core.isNull"></a>

### Core.isNull(thing) ⇒ <code>boolean</code>
Checks if a value is null.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>boolean</code> - - true if 'thing' is null. false otherwise.  

| Param | Type | Description |
| --- | --- | --- |
| thing | <code>any</code> | anything you want. |

**Example**  
```js
core.isNull(null); // true
```
<a name="Core.isBoolean"></a>

### Core.isBoolean(thing) ⇒ <code>boolean</code>
Checks if a value is a boolean.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>boolean</code> - - true if 'thing' is boolean. false otherwise.  

| Param | Type | Description |
| --- | --- | --- |
| thing | <code>any</code> | anything you want. |

**Example**  
```js
core.isBoolean(false); // true
core.isBoolean(''); // false
```
<a name="Core.isNumber"></a>

### Core.isNumber(thing) ⇒ <code>boolean</code>
Checks if a value is a number.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>boolean</code> - - true if 'thing' is a number. false otherwise.  

| Param | Type | Description |
| --- | --- | --- |
| thing | <code>any</code> | anything you want. |

**Example**  
```js
core.isNumber('35'); // false
core.isNumber(35); // true
```
<a name="Core.isString"></a>

### Core.isString(thing) ⇒ <code>boolean</code>
Checks if a value is a string.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>boolean</code> - - true if 'thing' is a string. false otherwise.  

| Param | Type | Description |
| --- | --- | --- |
| thing | <code>any</code> | anything you want. |

**Example**  
```js
core.isString('35'); // true
core.isString(35); // false
```
<a name="Core.isDate"></a>

### Core.isDate(thing) ⇒ <code>boolean</code>
Checks if a value is a date object.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>boolean</code> - - true if 'thing' is an array. false otherwise.  

| Param | Type | Description |
| --- | --- | --- |
| thing | <code>any</code> | anything you want. |

**Example**  
```js
core.isDate('6/3/81'); // false
core.isDate(new Date('6/3/81')); // true
```
<a name="Core.isArray"></a>

### Core.isArray(thing) ⇒ <code>boolean</code>
Checks if a value is an array.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>boolean</code> - - true if 'thing' is an array. false otherwise.  

| Param | Type | Description |
| --- | --- | --- |
| thing | <code>any</code> | anything you want. |

**Example**  
```js
core.isArray({}); // false
core.isArray([]); // true
```
<a name="Core.isObject"></a>

### Core.isObject(thing) ⇒ <code>boolean</code>
Checks if a value is an object.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>boolean</code> - - true if 'thing' is an object. false otherwise.  

| Param | Type | Description |
| --- | --- | --- |
| thing | <code>any</code> | anything you want. |

**Example**  
```js
core.isObject({}); // true
core.isObject([]); // false
```
<a name="Core.isFunction"></a>

### Core.isFunction(thing) ⇒ <code>boolean</code>
Checks if a value is a function.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>boolean</code> - - true if 'thing' is a function. false otherwise.  

| Param | Type | Description |
| --- | --- | --- |
| thing | <code>any</code> | anything you want. |

**Example**  
```js
core.isFunction({}); // false
core.isFunction(e => {}); // true
```
<a name="Core.assign"></a>

### Core.assign(target, source, assignFunc) ⇒ <code>object</code>
Copies all properties from 'source' to 'target', similar to Object.assign.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>object</code> - - The target object ( the first parameter ).  

| Param | Type | Description |
| --- | --- | --- |
| target | <code>object</code> | The target object. properties will be copied to this object. |
| source | <code>object</code> | A source, or a number of source objects. |
| assignFunc | <code>function</code> | A function that will be called for each property assignment. if provided, the assigned value will be the return value of this function. |

**Example**  
```js
core.assign({}, {a: 1, b: 2}, (property, key, source) => property + 1);   // { a: 2, b: 3 }
```
<a name="Core.extend"></a>

### Core.extend(properties) ⇒ <code>object</code>
Copies all members in 'properties' to the core instance.

**Kind**: static method of [<code>Core</code>](#Core)  
**Returns**: <code>object</code> - - Returns the target object ( the first parameter ).  

| Param | Type | Description |
| --- | --- | --- |
| properties | <code>object</code> | An |

**Example**  
```js
core.extend({
    getData(){ return this.myData; },
    myData: 45
});

core.getData();  // 45.
core.myData;  // 45.
```
<a name="Core.channel"></a>

### Core.channel(name, array) ⇒ <code>undefined</code>
Adds a new channel to the channels namespace object.

**Kind**: static method of [<code>Core</code>](#Core)  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | The name of the channel. |
| array | <code>array</code> | Optional array of functions. |

**Example**  
```js
core.channel('collection');
core.channels.collection; // [].
```
<a name="Core.tap"></a>

### Core.tap(name, func) ⇒ <code>undefined</code>
tap to a channel.

**Kind**: static method of [<code>Core</code>](#Core)  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | The name of the channel. |
| func | <code>function</code> | A function to attach to the channel. |

**Example**  
```js
core.channel('dataType');

core.tap('dataType', (dataType, done) => {
    dataType.test = 'ok';
    done(dataType);
});

core.fire('dataType', {}, (dataType) => {
    dataType.test; // 'ok'
});
```
<a name="Core.fire"></a>

### Core.fire(name, data, callback) ⇒ <code>undefined</code>
Runs data through a named channel.

**Kind**: static method of [<code>Core</code>](#Core)  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | The name of the channel. |
| data | <code>any</code> | Data to be passed through the channel. |
| callback | <code>function</code> | A function that will be called when the job completes. |

**Example**  
```js
core.channel('dataType', (dataType, done) => {
    dataType.test = 'ok';
    done(dataType);
});

core.fire('dataType', {}, (dataType) => {
    dataType.test; // 'ok'
});
```
<a name="Core.plugin"></a>

### Core.plugin(definition, callback) ⇒ <code>undefined</code>
Adds a plugin to core instance.

**Kind**: static method of [<code>Core</code>](#Core)  

| Param | Type | Description |
| --- | --- | --- |
| definition | <code>object</code> | The plugin definition. |
| definition.name | <code>string</code> | The name of the plugin. |
| callback | <code>function</code> | A function that will be called when the job completes. |

**Example**  
```js
core.plugin({
    name: 'myPlugin',
    extend: {
        getData(){ return core.plugins.myPlugin.data; }
    },
    init(def, done){
        done({ data: 47 })
    }
});
core.getData();  // 47.
```
<a name="Core.channels
A namespace object to hold named channels."></a>

## Core.channels
A namespace object to hold named channels.
**Kind**: global variable  
