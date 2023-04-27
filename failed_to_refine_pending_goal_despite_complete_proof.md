# When you have what you believe is a complete and valid proof, but isabelle won't accept it

This is a very specific issue that I had, and it was not clear why.

I had an Isar proof that I thought was valid, so ended it with `finally show ?thesis.`, but isabelle told me `Failed to refine any pending goal`.

## The fix

The fix: using `proof -` instead of `proof`.

## The explanation

The first thing after the `proof` keyword is something to apply to the current goal to transform it somehow.

If the goal is transformed in some way, then it no longer matches what's in `?thesis` which is always the goal as originally stated in the lemma.

By default Isabelle tries to be clever and transform your goal for you before you start your proof.

The `-` tells Isabelle "please leave this goal as it is and immediately start readint this proof".
