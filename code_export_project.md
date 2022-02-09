# How do I export code from isabelle?

You are reding this because you want to:
 - export code from isabelle in:
    - Haskel
    - SML
    - OCaml
    - or Scala

## Assumptions:

(it should be obvious how to deviate from these assumptions)

 - You want to export code from isabelle for a project called `my_example`.
 - The code you want to export will be in a file called `my_code.thy`
 - You start with `~` as your working directory
 - You are working with isabelle/HOL
 - You want Haskell code (see "Changes you might want to make" for other languages)

## Steps

1. Create a session, if you haven't already

`~/> isabelle mkroot my_example`

This creates `~/my_example`

2. Build the session, to make sure it works

`~/>isabelle build -D my_example`

3. Create the theory file if you haven't already

Create/edit the file:
`~/my_example/my_code.thy`

To look something like this:

    theory my_code
      imports Main
    begin
    
    fun example_func_double :: "nat \<Rightarrow> nat"
      where "example_func_double a = a + a"
    
    export_code "example_func_double" in Haskell module_name my_haskell_code
    
    end

Notice that `\<Rightarrow>` should appear as `⇒` in isabelle-jedit

4. Make sure that the theory file is part of the session

edit `~/my_example/ROOT` to look something like:

    session my_example = HOL +
      options [document = pdf, document_output = "output"]
      theories
        my_code
      document_files
        "root.tex"

5. Run the code generator:

From inside the session directory:

`~/my_example/> isabelle export -d . -x'*:**' my_example`

Or from outside the session directory:

`~/> isabelle export -d my_example/ -x'*:**' my_example`

6. Find the generated code file:

Your code should be in: `~/my_example/export/my_example.my_code/code/export1/My_haskell_code.hs`

## Changes you might want to make

### Selecting another language

Simply change the `export_code` command in the .thy file

    export_code "example_func_double" in Haskell module_name my_haskell_code
    export_code "example_func_double" in SML module_name my_sml_code
    export_code "example_func_double" in OCaml module_name my_ocaml_code
    export_code "example_func_double" in Scala module_name my_scala_code (case_insensitive)

Note that the scala generator usually needs the `(case_insensitive)` option, if you are using MacOS or Windows, where the filenames are usualy case-insensitive (see [scala_case_insensitive_class_names.md](scala_case_insensitive_class_names.md))

Note that the location of the output file is not always the same, in particular Haskell is different to the others:

from `~/my_example/export/my_example.my_code/`:

    Haskell: code/export1/My_haskell_code.hs
    SML: code/export1.ML
    OCaml: code/export1.ocaml
    Scala: code/export1.scala

### Selecting a different output directory for code

Pass `-O other_dir` to `isabelle build`

`~/my_example/> isabelle export -d . -x'*:**' -O other_dir my_example`
