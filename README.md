xml schema validation for shok files

add the following attributes to the root element:

- entity(type): `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/entity.xsd">`
effect (vanilla list): `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/effects.xsd">`
- effect (ModLoader): `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/efefct.xsd">`
- tasklist: `<CGLETaskList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/tasklist.xsd">`
- technology: `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/tech.xsd">`

mark subclasses with `xsi:type="EGL__CGLETaskArgs"`, where a classname/classid attribute usually is used.

Note:
- validation requires a strict order of xml elements
- at the moment, all fields are required, even if their default values would suffice (this might change with manual schema edits in the future)

vs code (or any other schema validation) will mark some xml errors for you.
shok will ignore the additional elements and just load the xml normally, as if no schema were included.
