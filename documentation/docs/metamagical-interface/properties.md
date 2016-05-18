

# properties()


```javascript
type PropertyKind is 'value' or 'getter' or 'setter'
type Property     is { name: String, value: Any, kind: PropertyKind }

Interface.() => Array { category: String, members: Array Property }
```




> 
> **Stability: 1 - Experimental**
> 
> This feature is experimental and likely to change (or be removed) in the
> future.
> 


  - **From:**
    metamagical-interface
  - **Defined in:**
    Interface
  - **Copyright:**
    (c) 2016 Quildreen Motta
  - **Licence:**
    MIT
  - **Repository:**
    git://github.com/origamitower/metamagical.git
  - **Category:**
    Additional reflective methods
  - **Platforms:**
      - ECMAScript 2015
  - **Maintainers:**
      - Quildreen Motta <queen@robotlolita.me> (http://robotlolita.me/)
  - **Authors:**
      - Quildreen Motta <queen@robotlolita.me>



Retrieves a categorised list of properties owned by the current
context.



## Source


```javascript
properties() {
    const byName     = (a, b) => compare(a.name, b.name);
    const byCategory = (a, b) => compare(a.category, b.category);

    const sortedProperties = (object) => entriesOf(object).sort(byName);
    const asCategoryObject = ([category, members]) => ({ category, members });

    const category = ({ value }) =>
      isObject(value) ?  this.for(value)
                             .get(this.fields.category)
                             .getOrElse('(Uncategorised)')
      : /* else */       '(Uncategorised)';

    return groupBy(sortedProperties(this.object), category)
             .map(asCategoryObject)
             .sort(byCategory);
  }
```




## Properties in `properties()`




### (Uncategorised)




#### `name`



```haskell
String
```

(No documentation)



#### [`prototype`](../(unknown module)/metamagical-interface/properties/prototype)



(No documentation)






## Properties inherited from `(Anonymous)`




### (Uncategorised)




#### `apply()`



(No documentation)



#### `get arguments`



(No documentation)



#### `set arguments`



(No documentation)



#### `bind()`



(No documentation)



#### `call()`



(No documentation)



#### `get caller`



(No documentation)



#### `set caller`



(No documentation)



#### `constructor()`



(No documentation)



#### `toString()`



(No documentation)






## Properties inherited from `(Anonymous)`




### (Uncategorised)




#### `__defineGetter__()`



(No documentation)



#### `__defineSetter__()`



(No documentation)



#### `__lookupGetter__()`



(No documentation)



#### `__lookupSetter__()`



(No documentation)



#### `set __proto__`



(No documentation)



#### `get __proto__`



(No documentation)



#### `constructor()`



(No documentation)



#### `hasOwnProperty()`



(No documentation)



#### `isPrototypeOf()`



(No documentation)



#### `propertyIsEnumerable()`



(No documentation)



#### `toLocaleString()`



(No documentation)



#### `toString()`



(No documentation)



#### `valueOf()`



(No documentation)







