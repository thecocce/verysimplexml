# Description #

Node types of `ntText` are text nodes which don't have child nodes nor attributes - just an unparsed text value. They may appear before or after a ntElement node or after a child node.

# Example #

```xml

<books>

<book>this is the normal text of the book
<extranode>this is a child node

Unknown end tag for &lt;/extranode&gt;

 some text afterwards (this is the text node)


Unknown end tag for &lt;/book&gt;





Unknown end tag for &lt;/books&gt;


```

You should avoid mixing text and element nodes like above.

## Delphi Code ##
```delphi

var
Node: TXmlNode;
begin
...
// Add a node
Node.AddChild('extranode').Text := 'this is a child node';

// Add a text type node as a child node (text nodes don't have a name)
Node.AddChild('', ntText).Text := ' some text afterwards ';

```