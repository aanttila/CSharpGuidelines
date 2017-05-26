<!--
NOTE: Requires Markdown Extra. See http://michelf.ca/projects/php-markdown/extra/
 --> 
<link href="style.css" type="text/css" rel="stylesheet"/>

<table width="100%">
<tr>
<td class="title">C# Coding Guidelines Cheat Sheet</td>
</tr>
<tr>
<td><div class="subTitle">Design & Maintainability</div> (level 1 and 2 only)</td>
</tr>
</table>

<table width="100%">
<tr>
<td class="column" markdown="1">
<div markdown="1" class="sidebar">
**Basic Principles**

* The Principle of Least Surprise   
* Keep It Simple Stupid   
* You Ain’t Gonne Need It  
* Don’t Repeat Yourself
</div>

**Class Design**

*  Always have a single purpose for a class or interface (AV1000)
*  Always have small and focused interfaces (AV1003)  
*  Prefer decoupling classes from each other using interfaces (AV1005)  
*  Never hide inherited members with the `new` keyword (AV1010)  
*  Always allow for a derived object to be treated as if it were its base class object (AV1011)  
*  Never refer to derived classes from the base class (AV1013)  
*  Avoid exposing the objects an object depends on (AV1014)  
*  Avoid bidirectional dependencies (AV1020)  
*  Prefer classes with state and behavior (AV1025)  

<br/>
**Member Design**  

* Always allow properties to be set in any order (AV1100)  
* Never use mutually exclusive properties (AV1110)  
* Prefer methods and properties that only do one thing (AV1115)  
* Never expose stateful objects through static members (AV1125)   
* Always expose `IEnumerable<T>` or `ICollection<T>` instead of a concrete collection class (AV1130)   
* Never use `null` for properties, methods, or arguments representing collections (AV1135)  
* Always define parameters as specific as possible (AV1137)   
</td>
<td class="column">
**Miscellaneous Design**  

* Always throw exceptions rather than returning status values (AV1200)  
* Always provide rich and meaningful exception message text (AV1202)  
* Never swallow errors by catching generic exceptions  (AV1210)  
* Always check an event handler delegate for `null` (AV1220)  
* Always handle exceptions properly in asynchronous code (AV1215)  
* Always use a protected virtual method to raise each event (AV1225)  
* Never pass `null` as the sender parameter when raising an event (AV1235)  
* Prefer generic constraints (AV1240)  
* Always evaluate the result of a LINQ expression before returning it (AV1250)  

<br/>
**Maintainability**  

* Prefer a small number of statements in a method (AV1500)  
* Avoid conditions with double negatives (AV1502)  
* Never use "magic numbers" (AV1515)  
* Prefer using `var` when the type is very obvious (AV1520)  
* Always declare and initialize variables as late as possible (AV1521)  
* Prefer object and collection initializers over separate statements (AV1523)  
* Never make explicit comparisons to `true` or `false` (AV1525)  
* Never change a loop variable inside a `for` or `foreach` loop (AV1530)  
* Avoid nested loops (AV1532)  
</td>

<td class="column">
* Always add a block after keywords such `if`, `else`, `while`, `for`, `foreach` and `case` (AV1535)  
* Prefer a `default` block after the last `case` in a `switch` statement (AV1536)  
* Prefer an `else`-part after every `if`-`else`-`if `statement (AV1537)  
* Avoid multiple `return` statements (AV1540)  
* Prefer simple (conditional) assignments instead of `if`-`else` statements (AV1545)  
* Prefer encapsulation of complex expressions in a method or property (AV1547)  
* Prefer calling the more overloaded method from other overloads (AV1551)  
* Prefer using optional arguments only when replacing overloads (AV1553)  
* Avoid using named arguments (AV1555)  
* Prefer a small number of arguments for methods and constructors (AV1561)  
* Avoid `ref` or `out` parameters (AV1562)  
* Avoid methods that take a `bool` flag (AV1564)  
* Always check the result of an `as` operation (AV1570)  
* Never comment-out code (AV1575)  

<br/>
**Framework Guidelines**  

* Always use C# type aliases instead of the types from the `System` namespace (AV2201)  
* Always build with the highest warning level (AV2210)  
* Prefer Lambda expressions instead of delegates (AV2221)  
* Avoid the `dynamic` keyword except when talking to a dynamic object (AV2230)  
* Prefer `async`/`await` over `Task` (AV2235)  
</td>
<tr>

<table width="100%" class="footer">
<tr>
<td>
  Adrian Anttila (original by Dennis Doomen)  
  Version %semver% (%commitdate%)  
</td>
<td style="text-align:right">
  Based on [www.csharpcodingguidelines.com](http://www.csharpcodingguidelines.com)  
</td>
</tr>
</table>

<table width="100%" style="page-break-before: always;">
 <tr>
  <td class="title">C# Coding Guidelines Cheat Sheet</td>
 </tr>
 <tr>
 <td><div class="subTitle">Naming & Layout</div> (level 1 and 2 only)</td>
 </tr>
</table>

<table width="100%">
<tr>
<td class="column" markdown="1">
<div class="sidebar">

|**Pascal Casing**||
|:-------------------------------|-----------|
|Class, Struct					         |`AppDomain`|
|Interface 						           |`IBusinessService`|
|Enumeration type 				       |`ErrorLevel`
|Enumeratiion values			       |`FatalError`
|Event 							             |`Click`
|Protected field 				         |`MainPanel`
|Const field 					           |`MaximumItems`
|Read-only static field	         |`RedValue`	
|Method 						             |`ToString`
|Namespace 						           |`System.Drawing`
|Property 						           |`BackColor`
|Type Parameter                  |`TEntity`
| |  
|<br/>**Camel Casing**||
|Private field                   |`listItem`
|Variable                        |`listOfValues`
|Const variable                  |`maximumItems`
|Parameter                       |`typeName`

</div>

<br/>
**Naming**  

* Always use US English (AV1701)
* Avoid numbers in variables, parameters, and type members  (AV1704)
* Never prefix fields (AV1705)
* Never use abbreviations (AV1706)
* Always name members, parameters and variables according their meaning and not their type (AV1707)
* Always name types using nouns, noun phrases, or adjective phrases (AV1708)
* Never repeat the name of a class or enumeration in its members (AV1710)
* Avoid short names or names that can be mistaken with other names (AV1712)
* Always name methods using verb-object pair (AV1720)
* Always name namespaces using names, layers, verbs, and features (AV1725)
* Always use an underscore for irrelevant lambda parameters (AV1739)
</td>
<td class="column">

**Documentation**  

* Always write comments and documentation in US English (AV2301)
* Prefer documenting public, protected, and internal types and members (AV2305)
* Avoid inline comments (AV2310)
* Prefer comments for complex algorithms or decisions only (AV2316)
* Avoid using comments for tracking work to be done later (AV2318)
<br/>

**Layout**

* Always indent 4 spaces, don’t use Tabs
* Always add white-space between keywords like `if` and the expression, but don’t add white-spaces after `(` and before `)`.
* Always add white-space around operators, like `+`, `-`, `==`, etc.
* Always add braces after keywords `if`, `else`, `do`, `while`, `for` and `foreach`
* Always put opening and closing braces on a new line.
* Never indent object initializers and initialize each property on a new line.
* Never indent lambda statements
* Always put the entire LINQ statement on one line, or start each keyword at the same indentation.

**Performance**

* Always use `Any()` to determine whether an `IEnumerable<T>` is empty (AV1800)
* Always use classes from `System.Collections.Generics` instead of `System.Collections` (AV1810)
* Always wrap `IDisposable` instances in a `using` statement (AV1840)
</td>
<td class="column">

<div markdown="1" class="sidebar">
**Empty lines**

* Between members
* Between multi-line statements
* Between unrelated code blocks 
* Around the `#region` keyword
</div>

<div class="sidebar">
**Member order**

1.	Private fields and constants
1.	Public constants
1.	Public read-only static fields
1.	Factory Methods
1.	Constructors and the Finalizer
1.	Events
1.	Public Properties
1.	Other methods and private properties
</div>

<div markdown="1" class="sidebar">
**Important Note**

These coding guidelines are an extension to Visual Studio's Code Analysis functionalty, so make sure you enable that for all your projects. Check the full document for more details.
</div>

<td/>
<tr>

<table width="100%" class="footer">
<tr>
 <td>
   Adrian Anttila (original by Dennis Doomen)   
   Version %semver% (%commitdate%)   
 </td>
 <td style="text-align:right">
  Based on [www.csharpcodingguidelines.com](http://www.csharpcodingguidelines.com)  
  </td>
</tr>
</table>
