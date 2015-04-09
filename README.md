# The TypeScript Cheat Sheet

This "cheat sheet" was originally taken from an excellent [article](http://www.sitepen.com/blog/2013/12/31/typescript-cheat-sheet/) on [Site Pen](http://www.sitepen.com/). We made a copy of it here in github because it is a great way to maintain this cheat sheet and keep it up-to-date.

To improve this document, please fork and submit a pull request!

Last updated for: TypeScript 0.9.5

## Primitive Types

Type | Code      
--- | ---
Any type (explicitly untyped) | `any`
void type (null or undefined, use for function returns only) | `void`
String | `string`
Number | `number`
Boolean | `boolean`

## Named types (interface, class, enum)

**Interface**

```typescript
 interface IChild extends IParent, SomeClass {
     property: Type;
     optionalProp?: Type;
     optionalMethod?(arg1: Type): ReturnType;
 }
 ```

**Class**
```typescript
 class Child extends Parent implements IChild, IOtherChild {
   property:Type;
   defaultProperty:Type = 'default value';      
   private _privateProperty:Type;      
   static staticProperty:Type;      
   constructor(arg1:Type) {      
    super(arg1);      
   }      
   private _privateMethod():Type {}      
   methodProperty:(arg1:Type) => ReturnType;      
   overloadedMethod(arg1:Type):ReturnType;      
   overloadedMethod(arg1:OtherType):ReturnType;      
   overloadedMethod(arg1:CommonT):CommonReturnT {}      
   static staticMethod():ReturnType {}      
   subclassedMethod(arg1:Type):ReturnType {      
      super.subclassedMethod(arg1);      
   }      
 } 
```

**Enum**
```typescript
enum Options {
    FIRST,
    EXPLICIT = 1,
    BOOLEAN = Options.FIRST | Options.EXPLICIT
}
```

## Object type literals

Concept | Code      
--- | ---
Object with implicit Any properties | `{ foo; bar; }`
Object with optional property | `{ required:Type; optional?:Type; }`
Hash map | `{ [key:string]:Type; }`

## Arrays

Concept | Code      
--- | ---
Array of strings | `string[]` or `Array<string>`
Array of functions that return strings | `{ ():string; }[]` or `Array<()=>string>`

## Functions

Concept | Code      
--- | ---
Function | `{ (arg1:Type, argN:Type):Type; }` or `(arg1:Type, argN:Type) => Type;`
Constructor | `{ new ():ConstructedType; }` or `new () => ConstructedType;`
Function type with optional param | `(arg1:Type, optional?:Type) =>; ReturnType`
Function type with `rest` param | `(arg1:Type, ...allOtherArgs:Type[]) =>; ReturnType`
Function type with static property | `{ ():Type; staticProp:Type; }`
Default argument | `function fn(arg1:Type = 'default'):ReturnType {}`
Arrow function | `(arg1:Type):ReturnType =>; {}` or `(arg1:Type):ReturnType =>; Expression`

## Generics

**Function using type parameters**

```typescript
<T>(items:T[], callback:(item:T) => T):T[]
```

**Interface with multiple types**

```typescript
interface Pair<T1, T2> {
   first:T1;
   second:T2;
}
```

**Constrained type parameter**

```
<T extends ConstrainedType>():T
```

## Other

Concept | Code      
--- | ---
Type of a variable | `typeof varName`

##Contributors
- Bhagya Nirmaan Silva (http://about.me/bhagyas)

