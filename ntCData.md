# Description #

Node types of `ntCData` are CDATA section nodes which don't have child nodes nor attributes - just an unparsed text value.

# Example #

```xml

<book><![CDATA[now we can use < > without escaping]]>

Unknown end tag for &lt;/book&gt;


```

The book node doesn't have a `.text` property, only a ntCData child node.

## Delphi Code ##
```delphi

var
BookNode, Node: TXmlNode;
begin
...
// Add a node
Node.AddChild('book');

// Add a CDATA section
BookNode.AddChild('', ntCData).Text := 'now we can use < > without escaping'```