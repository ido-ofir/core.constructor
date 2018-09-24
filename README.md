<a name="core"></a>

## core
**Kind**: global class  

* [core](#core)
    * [new core(options)](#new_core_new)
    * [.typeOf(thing)](#core.typeOf) ⇒ <code>string</code>

<a name="new_core_new"></a>

### new core(options)

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
<a name="core.typeOf"></a>

### core.typeOf(thing) ⇒ <code>string</code>
Returns the correct native type in javascript ( unlike the 'typeof' operator ).

**Kind**: static method of [<code>core</code>](#core)  
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
