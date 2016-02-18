# Description #

Node types of `ntComment` are the comment nodes types, which don't have child nodes nor attributes - just a text value.


# Example #

```xml

<!-- This is the first book -->
<book id="bk101">A book text

Unknown end tag for &lt;/book&gt;



<!-- This is the second book -->
<book id="bk102">Another book text

Unknown end tag for &lt;/book&gt;


```

Comments may appear before or after any nodes or as child nodes in between.

## Delphi Code ##
```delphi

var
Node: TXmlNode;
XmlDoc: TXmlVerySimple;
begin
...
// Add a comment
Node := XmlDoc.AddChild('', ntComment); // Comment nodes don't have a name
Node.Text := ' This is the first book '; // Note the spaces!

// Add the book
XmlDoc.AddChild('book').SetAttribute('id', 'bk101').Text := 'A book text';

// Add a comment by using the fluent interface functions
XmlDoc.AddChild('', ntComment).Text := ' This is the second book ';

// Add the second book
XmlDoc.AddChild('book').SetAttribute('id', 'bk102').Text := 'Another book text';
...
end;
```