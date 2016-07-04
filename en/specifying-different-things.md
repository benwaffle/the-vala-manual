

Specifying Different Things
===========================

To specify a:

  ---------------------- ---------------------------
  Function               `name_of_function`
  Type                   `Type`
  Property               `Type:property_name`
  Signal                 `Type::signal_name`
  Field                  `Type.field_name`
  Parameter (Function)   `name_of_function.param`
  Parameter (Delegate)   `DelegateName.param`
  Parameter (Signal)     `Type::signal_name.param`
  ---------------------- ---------------------------

For example, hiding a symbol:

  ---------- ----------------------------
  Type       `Foo hidden="1"`
  Function   `some_function hidden="1"`
  Field      `Foo.bar hidden="1"`
  ---------- ----------------------------

