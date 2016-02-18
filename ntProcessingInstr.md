# Description #

Node types of `ntProcessingInstr` are processing instruction nodes which don't have child nodes nor attributes - just an unparsed text value.
If you need to parse the processing instructions you may set the `XmlDocument.Options` to `doParseProcessingInstr` before loading the xml file.

# Example #

```xml

<?xml version="1.0"?>
<?pi uppercase="true"?>
```


## Delphi Code ##
```delphi

var
Node: TXmlNode;
XmlDoc: TXmlVerySimple;
begin
// Create an example XML and save it
XmlDoc := TXmlVerySimple.Create;
Node := XmlDoc.AddChild('pi', ntProcessingInstr);
Node.Attributes['uppercase'] := 'true';
XmlDoc.SaveToFile('test.xml');
XmlDoc.Free;

// Now load it with doParseProcessingInstr turned on
XmlDoc := TXmlVerySimple.Create;
XmlDoc.Otpions := XmlDoc.Options + [doParseProcessingInstr];
XmlDoc.LoadFromFile('text.xml');

// find a processing instruction node called 'pi'
Node := XmlDoc.ChildNodes.Find('pi', ntProcessingInstr);

// because we've turned doParseProcessingInstr on, we're able
// to access the attributes by the attributes list
if Node.Attributes['uppercase'] = 'true' then
...

```