# 关于 Map 和 Object

* day log 01.07

### Object
  > key: value 存储     
  > key 会自动转成字符串来存储；
  
```js

    const obj = {};
    const keys = o => console.log(Object.keys(o));
    // number
    obj[1] = 'num-1';
    keys(obj);  // ['1']
    // string
    obj['1'] = 'str-1';
    keys(obj);  // ['1']
    // array
    const arr = [1];
    obj[arr] = 'arr-1';
    keys(obj);  // ['1']
    // boolean
    obj[true] = 'bool-true';
    obj[false] = 'bool-false';
    keys(obj);  //  [ '1', 'true', 'false' ]
    // object
    const obj_1 = {};
    const obj_2 = {};
    obj[obj_1] = 'obj-1';
    obj[obj_2] = 'obj-2';
    keys(obj);  // [ '1', 'true', 'false', '[object Object]' ]
    console.log(obj[obj_2]);    //  'obj-2'
    
```
  
### Map
> 设计目的就是为了实现值对值的功能 value: value

```js

    const map = new Map();
    map.set(1, 'num-1').set('1', 'str-1');
    console.log(map.keys());    // [Map Iterator] { 1, '1' }
    
```     

                
                
**************
>toString 规则 (大概？)        

    key: number 	=> 	Number(key).toString();     
    key: object 	=> 	key.toString();     
    key: array 	=> 	Array(key).toString();      
    key: symbol 	=> 	Symbol(key).toString(); /// ?????       
    key: boolean 	=> 	Boolean(key).toString();        
    key: string 	=> 	key;        
