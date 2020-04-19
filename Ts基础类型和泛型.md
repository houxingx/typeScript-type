#### Js基本类型：Undefined、Null，Boolean、Number、String、Object、Symbol。

```javascript
console.log(typeof(null));//"object"
console.log(undefined == null); //true
//null和undefined有这样的关系，但它们的用途完全不同。无论在什么情况下都没有必要把一个变量的值显式地设置为undefined，可是同样的规则对null却不适用。换句话说，只要意在保存对象的变量还没有真正保存对象，就应该明确地让该变量保存null值。

let o = {flag: true};
let test=!!o.flag;//等效于var test=o.flag||false;

//JavaScript中，任何数值除以0会返回NaN，因此不会影响其他代码的执行。
alert(NaN == NaN);    //false
```

#### Ts基本类型：Boolean，Number，String，Array，Tuple(元素类型不同的数组)，Any(改写最常用的类型之一),Void，Null 和 Undefined,Never, symbol，Object。

--strictNullChecks 严格空检查模式

![1587307939952](C:\Users\hou\AppData\Roaming\Typora\typora-user-images\1587307939952.png)

```typescript
let anyType: any;
function errorFun(): never {
    throw new Error('this is an error');
}
anyType = errorFun; // ok
```

```typescript
let neverType: never;
function errorFun(): any || never {
    throw new Error('this is an error');
}
neverType = errorFun; // error
```

#### 类型断言：

```
let someValue: any = "this is a string";
let strLength1: number = (<string>someValue).length;
let strLength2: number = (someValue as string).length;
```

然而，当你在TypeScript里使用JSX时，只有 `as`语法断言是被允许的。

#### 泛型