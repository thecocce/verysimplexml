# Description #

Node types of `ntElement` are the default node types, which may have child nodes and attributes and a text value.


# Example #

```xml

<book id="bk101">A book text

Unknown end tag for &lt;/book&gt;


```

Will be parsed into a node with type `ntElement` and an attribute called `id` with `bk101` as its attribute value, as well as `A book text` as the text property.

## Delphi Code ##
```delphi

Node := TXmlNode.Create;  // Creates a new ntElement node
Node.Attributes['id'] := 'bk101';
Node.Text := 'A book text';```