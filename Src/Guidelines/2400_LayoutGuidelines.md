<!--
NOTE: Requires Markdown Extra. See http://michelf.ca/projects/php-markdown/extra/
 --> 

# 10. Layout Guidelines

### <a name="av2400"></a> Always use a common layout (AV2400) ![](images/1.png)

- Use an indentation of 4 whitespaces, and don't use tabs

- Always add white-space between keywords like `if` and the expression, but don’t add white-spaces after `(` and before `)` such as: `if (condition == null)`.

- Always add white-space around operators, like `+`, `-`, `==`, etc.

- Always follow the keywords `if`, `else`, `do`, `while`, `for` and `foreach` with opening and closing braces, even though the language does not require it. 

- Always put opening and closing braces on a new line.

- Don't indent object Initializers and initialize each property on a new line, so use a format like this: 
	
		var dto = new ConsumerDto()
		{  
			Id = 123,  
			Name = "Microsoft",  
			PartnerShip = PartnerShip.Gold
		};

- Don't indent lambda statements and use a format like this:

		methodThatTakesAnAction.Do(x =>
		{ 
			// do something like this 
		};

- Put the entire LINQ statement on one line:
		
		var query = from product in products where product.Price > 10 select product;

    or start each keyword at the same indentation:
	
		var query =  
		    from product in products  
		    where product.Price > 10  
		    select product;

- Start the LINQ statement with all the `from` expressions and don't interweave them with restrictions.

- Add an empty line between multi-line statements, between members, after the closing parentheses, between unrelated code blocks, and around the `#region` keyword.


### <a name="av2402"></a> Always order namespaces (AV2402) ![](images/3.png)

	using System;
	using System.Collections;
	using System.XML;
	using AvivaSolutions.Business;
	using AvivaSolutions.Standard;
	using Telerik.WebControls;
	using Telerik.Ajax;

### <a name="av2406"></a> Always place members in a well-defined order  (AV2406) ![](images/1.png)
Maintaining a common order allows other team members to find their way in your code more easily. In general, a source file should be readable from top to bottom, as if reading a book, to prevent readers from having to browse up and down through the code file.

1. Private fields and constants
2. Public constants
3. Public read-only static fields
4. Factory Methods
5. Constructors and the Finalizer
6. Events 
7. Public Properties
8. Other methods and private properties in calling order

### <a name="av2407"></a> Avoid `#regions` (AV2407) ![](images/1.png)
Regions can be helpful, but can also hide the main purpose of a class. Therefore, only consider using `#regions` only for:

- Nested classes
- Interface implementations (only if the interface is not the main purpose of that class)
