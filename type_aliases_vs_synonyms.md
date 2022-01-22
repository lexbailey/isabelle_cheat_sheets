# Type aliases don't work in isabelle

You're here because you want to define a type alias in isabelle but you tried `type_alias` and it didn't work

Suppose you want to define `nat_pair` to be `nat * nat`

You do _not_ want the `type_alias` command (I know, the name is confusing) you want `type_synonym` as in this example:

    type_synonym pair = "nat * nat"
    
    fun max_of_pair :: "pair ⇒ nat"
      where "max_of_pair (a,b) = (if a > b then a else b)"
    
    value "max_of_pair (14,2)" (* answer is 14 *)
