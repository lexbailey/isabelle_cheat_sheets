# Generating valid scala code from isabelle for case-insensitive file systems

If you tried generating scala code from isabelle and ended up with a warning about case-insensitive file systems, you're probably in the right place

    [warn] /foo/bar/src/main/scala/exported.scala:41:18: Generated class example$Char differs only in case from example$char.
    [warn]   Such classes will overwrite one another on case-insensitive filesystems.
    [warn] final case class Char(a: Boolean, b: Boolean, c: Boolean, d: Boolean,

This is because isabelle generates code that assumes this won't be a problem (because you're using a case sensitive file system)

change your `export_code` line from something like this:

    export_code "example_func" in Scala module_name my_scala_code

to something like this:

    export_code "example_func" in Scala module_name my_scala_code (case_insensitive)
