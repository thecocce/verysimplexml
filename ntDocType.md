# Description #

Node types of `ntDocType` are Document Type Definition nodes, which don't have child nodes nor attributes - just an unparsed text value. They may be expanded to multiple lines by using the `[` character and closed by `]`.


# Example #

```xml

<!DOCTYPE animal [
<!ELEMENT animal (cat|tiger|leopard)+>
<!ELEMENT cat EMPTY>
<!ELEMENT tiger (#PCDATA)>
<!ELEMENT leopard ANY>
<!ELEMENT small EMPTY>
<!ELEMENT big EMPTY>
<!ATTLIST tiger color CDATA #REQUIRED>
]>
```

DocType nodes aren't parsed or evaluated at all - the complete text is put into the `Node.Text` property.

## Delphi Code ##
```delphi

var
Node: TXmlNode;
XmlDoc: TXmlVerySimple;
begin
...
// Add a doc type node
Node := XmlDoc.AddChild('', ntDocType); // Document nodes don't have a name
Node.Text := ' <!ELEMENT cat EMPTY>';

```