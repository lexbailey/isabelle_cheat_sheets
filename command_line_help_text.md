# Isabelle Command line interface help text

Perhaps you have a question like one of these:

 - Why does `isabelle --help` not work?
 - Why does isabelle say `*** Unknown Isabelle tool:` when I try to get the CLI help text?
 - What are all the isabelle command line interface tool names?
 - How do I get isabelle to show the CLI help text?

## Getting isabelle to print list of tools

run this:

`isabelle '-?'`

yes, really

Why is it not `-h` or `--help`? I have no idea. It deliberately uses a syntax that is not common, and I can't see a good reason for it.

Note that you should include the single quotes around `-?`, because in most shells the `?` character in an unquoted string will expand into a list of filenames (glob syntax).

## Getting help text for a specific tool

You can also pass `'-?'` to a specific tool, for example: `isabelle build '-?'` to get help text for a specific tool

## The list of tools as of isabelle 2021

    afp_build - build and manage AFP sessions
    afp_check_roots - check ROOT files of AFP sessions
    afp_churn_pie - pie chart with Mercurial churn statistics
    afp_dependencies - extract dependencies between AFP entries
    browser - Isabelle graph browser
    build - build and manage Isabelle sessions
    build_components - build and publish Isabelle components
    build_csdp - build prover component from official download
    build_cygwin - produce pre-canned Cygwin distribution for Isabelle
    build_doc - build Isabelle documentation
    build_docker - build Isabelle docker image
    build_e - build prover component from source distribution
    build_fonts - construct Isabelle fonts
    build_jdk - build Isabelle jdk component from original archives
    build_polyml - build Poly/ML from sources
    build_polyml_component - make skeleton for Poly/ML component
    build_spass - build prover component from source distribution
    build_sqlite - build Isabelle sqlite-jdbc component from official download
    build_status - present recent build status information from database
    build_vampire - build prover component from repository
    build_verit - build prover component from official download
    build_vscode - build Isabelle/VSCode extension module
    build_zipperposition - build prover component from OPAM repository
    check_sources - some sanity checks for Isabelle sources
    churn - mercurial churn statistics for specified aliases file
    churn_pie - pie chart with Mercurial churn statistics
    client - console interaction for Isabelle servers (with line-editor)
    components - resolve Isabelle components
    console - raw ML process (interactive mode)
    doc - view Isabelle documentation
    document - prepare session theory document
    dump - dump cumulative PIDE session database
    env - run a program in a modified environment
    export - retrieve theory exports
    getenv - get values from Isabelle settings environment
    ghc_setup - setup Glasgow Haskell Compiler via Stack
    ghc_stack - invoke Haskell Tool Stack within the Isabelle environment
    hg_setup - setup remote vs. local Mercurial repository
    install - install standalone Isabelle executables
    java - invoke Java within the Isabelle environment
    java_monitor - monitor another Java process
    jedit - Isabelle/jEdit interface wrapper
    jedit_client - Isabelle/jEdit client for already running application
    latex - run LaTeX (and related tools)
    log - print messages from build database
    logo - create an instance of the Isabelle logo (PDF)
    mirabelle - testing tool for automated proof tools
    mkroot - prepare session root directory
    mutabelle - mutant-testing for counterexample generators and automated tools
    ocaml_opam - invoke OCaml Package Manager within the Isabelle environment
    ocaml_setup - setup OCaml via OPAM
    options - print Isabelle system options
    phabricator - invoke command-line tool within Phabricator home directory
    phabricator_setup - setup Phabricator server on Ubuntu Linux
    phabricator_setup_mail - setup mail for one Phabricator installation
    phabricator_setup_ssh - setup ssh service for all Phabricator installations
    process - raw ML process (batch mode)
    profiling_report - report Poly/ML profiling information from log files
    regenerate_cooper - regenerate ~~/src/HOL/Tools/Qelim/cooper_procedure.ML from ~~/src/HOL/Decision_Proc/Cooper.thy
    scala - invoke Scala within the Isabelle environment
    scala_project - setup Gradle project for Isabelle/Scala/jEdit
    scalac - invoke Scala compiler within the Isabelle environment
    server - manage resident Isabelle servers
    sessions - explore structure of Isabelle sessions
    tptp_graph - TPTP visualisation utility
    tptp_isabelle - Isabelle tactics for TPTP competitive division
    tptp_isabelle_hot - Isabelle tactics for TPTP demo division
    tptp_nitpick - Nitpick for TPTP
    tptp_refute - Refute for TPTP
    tptp_sledgehammer - Sledgehammer for TPTP
    tptp_translate - translate between TPTP formats
    update - update theory sources based on PIDE markup
    update_cartouches - update theory syntax to use cartouches
    update_comments - update formal comments in outer syntax
    update_header - replace obsolete theory header command
    update_then - expand old Isar command conflations 'hence' and 'thus'
    update_theorems - update toplevel theorem keywords
    version - display Isabelle version
    vscode_grammar - generate static TextMate grammar for VSCode editor
    vscode_server - VSCode Language Server for PIDE
