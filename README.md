# The TypeScript Cheat Sheet

This "cheat sheet" was originally taken from an excellent [article](http://www.sitepen.com/blog/2013/12/31/typescript-cheat-sheet/) on [Site Pen](http://www.sitepen.com/). We made a copy of it here in github because it is a great way to maintain this cheat sheet and keep it up-to-date.

To improve this document, please fork and submit a pull request!

Last updated for: TypeScript 0.9.5

<table class="typescript-reference">
    <tr>
      <th colspan="2">Primitive types</th>
    </tr>

    <tr>
      <td>Any type (explicitly untyped)</td>

      <td><code>any</code></td>
    </tr>

    <tr>
      <td>void type (null or undefined, use for function returns only)</td>

      <td><code>void</code></td>
    </tr>

    <tr>
      <td>String</td>

      <td><code>string</code></td>
    </tr>

    <tr>
      <td>Number</td>

      <td><code>number</code></td>
    </tr>

    <tr>
      <td>Boolean</td>

      <td><code>boolean</code></td>
    </tr>

    <tr>
      <th colspan="2">Named types (interface, class, enum)</th>
    </tr>

    <tr>
      <td>Interface</td>

      <td><code>interface IChild extends IParent, SomeClass {<br />
      &nbsp; property:Type;<br />
      &nbsp; optionalProp?:Type;<br />
      &nbsp; optionalMethod?(arg1:Type):ReturnType;<br />
      }</code></td>
    </tr>

    <tr>
      <td>Class</td>

      <td><code>class Child extends Parent implements IChild, IOtherChild {<br />
      &nbsp; property:Type;<br />
      &nbsp; defaultProperty:Type = 'default value';<br />
      &nbsp; private _privateProperty:Type;<br />
      &nbsp; static staticProperty:Type;<br />
      &nbsp; constructor(arg1:Type) {<br />
      &nbsp; &nbsp; super(arg1);<br />
      &nbsp; }<br />
      &nbsp; private _privateMethod():Type {}<br />
      &nbsp; methodProperty:(arg1:Type) =&gt; ReturnType;<br />
      &nbsp; overloadedMethod(arg1:Type):ReturnType;<br />
      &nbsp; overloadedMethod(arg1:OtherType):ReturnType;<br />
      &nbsp; overloadedMethod(arg1:CommonT):CommonReturnT {}<br />
      &nbsp; static staticMethod():ReturnType {}<br />
      &nbsp; subclassedMethod(arg1:Type):ReturnType {<br />
      &nbsp; &nbsp; super.subclassedMethod(arg1);<br />
      &nbsp; }<br />
      }</code></td>
    </tr>

    <tr>
      <td>Enum</td>

      <td><code>enum Options {<br />
      &nbsp; FIRST,<br />
      &nbsp; EXPLICIT = 1,<br />
      &nbsp; BOOLEAN = Options.FIRST | Options.EXPLICIT<br />
      }</code></td>
    </tr>

    <tr>
      <th colspan="2">Object type literals</th>
    </tr>

    <tr>
      <td>Object with implicit Any properties</td>

      <td><code>{ foo; bar; }</code></td>
    </tr>

    <tr>
      <td>Object with optional property</td>

      <td><code>{ required:Type; optional?:Type; }</code></td>
    </tr>

    <tr>
      <td>Hash map</td>

      <td><code>{ [key:string]:Type; }</code></td>
    </tr>

    <tr>
      <th colspan="2">Arrays</th>
    </tr>

    <tr>
      <td>Array of strings</td>

      <td><code>string[]</code> or<br />
      <code>Array&lt;string&gt;</code></td>
    </tr>

    <tr>
      <td>Array of functions that return strings</td>

      <td><code>{ ():string; }[]</code> or<br />
      <code>Array&lt;() =&gt; string&gt;</code></td>
    </tr>

    <tr>
      <th colspan="2">Functions</th>
    </tr>

    <tr>
      <td>Function</td>

      <td><code>{ (arg1:Type, argN:Type):Type; }</code> or<br />
      <code>(arg1:Type, argN:Type) =&gt; Type;</code></td>
    </tr>

    <tr>
      <td>Constructor</td>

      <td><code>{ new ():ConstructedType; }</code> or<br />
      <code>new () =&gt; ConstructedType;</code></td>
    </tr>

    <tr>
      <td>Function type with optional param</td>

      <td><code>(arg1:Type, optional?:Type) =&gt; ReturnType</code></td>
    </tr>

    <tr>
      <td>Function type with <code>rest</code> param</td>

      <td><code>(arg1:Type, ...allOtherArgs:Type[]) =&gt; ReturnType</code></td>
    </tr>

    <tr>
      <td>Function type with static property</td>

      <td><code>{ ():Type; staticProp:Type; }</code></td>
    </tr>

    <tr>
      <td>Default argument</td>

      <td><code>function fn(arg1:Type = 'default'):ReturnType {}</code></td>
    </tr>

    <tr>
      <td>Arrow function</td>

      <td><code>(arg1:Type):ReturnType =&gt; {}</code> or<br />
      <code>(arg1:Type):ReturnType =&gt; Expression</code></td>
    </tr>

    <tr>
      <th colspan="2">Generics</th>
    </tr>

    <tr>
      <td>Function using type parameters</td>

      <td><code>&lt;T&gt;(items:T[], callback:(item:T) =&gt; T):T[]</code></td>
    </tr>

    <tr>
      <td>Interface with multiple types</td>

      <td><code>interface Pair&lt;T1, T2&gt; {<br />
      &nbsp; first:T1;<br />
      &nbsp; second:T2;<br />
      }</code></td>
    </tr>

    <tr>
      <td>Constrained type parameter</td>

      <td><code>&lt;T extends ConstrainedType&gt;():T</code></td>
    </tr>

    <tr>
      <th colspan="2">Other</th>
    </tr>

    <tr>
      <td>Type of a variable</td>

      <td><code>typeof varName</code></td>
    </tr>
  </table>
