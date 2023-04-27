# When using SMT to discharge proof goals including Word types, spurious counterexamples are reported

The Word library is really cool, and does some magic to work with SMT tools (such as Z3) via the normal "apply smt".

However, as of time of writing, it cannot reconstruct proofs from SMT runs to satisfy isabelle.

## The fix

You can tell Isabelle "Just trust Z3 when is says something holds"

    declare [[smt_oracle = true]]
    declare [[z3_extensions = true]]

(I'm not sure if the second line is always needed, but for the proofs I was trying, they were)

see `HOL/SMT_Examples/SMT_Word_Examples.thy` for examples of such SMT proofs.
