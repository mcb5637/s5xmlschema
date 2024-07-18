xml schema validation for shok files

add the following attributes to the root element:

- entity(type): `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/entity.xsd">`
- effect (vanilla list): `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/effects.xsd">`
- effect (ModLoader): `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/efefct.xsd">`
- tasklist: `<CGLETaskList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/tasklist.xsd">`
- technology: `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/tech.xsd">`
- model (vanilla list): `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/models.xsd">`
- model (ModLoader): `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/model.xsd">`
- animset: `<AnimSet xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/animset.xsd">`
- experienceclass: `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/experienceclass.xsd">`
- damageclasses.xml: `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="https://raw.githubusercontent.com/mcb5637/s5xmlschema/master/damageclasses.xsd">`

Note:
- validation requires a strict order of xml elements
- at the moment, all fields are required, even if their default values would suffice (this might change with manual schema edits in the future)
- when using subclasses (of BB::IObject) mark their type like this: `xsi:type="EGL__CGLETaskArgs"` (replace any instancne of :,<> with _)
	requires the classname attribute and optionally defines the classid attribute to specific hardcoded values corresponding to the type used
	(note that shok requires either of the 2, if both are present, classid has precedence. i choose to require classname because it is clearer for human readers)

vs code (or any other schema validation) will mark some xml errors for you.
shok will ignore the additional elements and just load the xml normally, as if no schema were included.
