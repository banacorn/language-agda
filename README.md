# language-agda package

Adds syntax highlighting to [Agda](http://wiki.portal.chalmers.se/agda/pmwiki.php) files in Atom.

Contributions are greatly appreciated. Please fork this repository and open an pull request to add snippets, make grammar tweaks, etc.

## Snippets

### with-abstraction

Whenever you need a with-abstraction

```agda
filter : {A : Set} → (A → Bool) → List A → List A
filter p [] = []
filter p (x ∷ xs) $1 = ?
```

Simply type `with` at the `$1` position before `= ?` and then press <kbd>tab</kbd> or <kbd>enter</kbd>, the snippet would set up a scaffolding with cursor positioned at`$1`, press <kbd>tab</kbd> to jump the cursor from `$1` to `$2`.

```agda
filter : {A : Set} → (A → Bool) → List A → List A
filter p [] = []
filter p (x ∷ xs) with $1
... | $2 = ?
```

### (in)equational-reasoning

`eq` for this:

```agda
begin
    {! $1 !}
≡⟨ {!   !} ⟩
    {!   !}
≡⟨ {!   !} ⟩
    {!   !}
≡⟨ {!   !} ⟩
    {!   !}
≡⟨ {!   !} ⟩
    {!   !}
∎
```

`eqs` for a small step:

```agda
≡⟨ {! $1 !} ⟩
    {!   !}
```

`po` for this:

```agda
start
    {!  !}
≤⟨ {!   !} ⟩
    {!   !}
≤⟨ {!   !} ⟩
    {!   !}
≤⟨ {!   !} ⟩
    {!   !}
≤⟨ {!   !} ⟩
    {!   !}
□
```

note that the operators of pre-order reasoning are renamed to prevent conflicts with equational reasoning

```agda
open ≡-Reasoning
open ≤-Reasoning renaming (begin_ to start_; _∎ to _□; _≡⟨_⟩_ to _≈⟨_⟩_)
```

also `pos` for a small step:

```agda
≤⟨ {!  !} ⟩
    {!   !}
```

``px`` and ``pxs`` in case you have reflexive relations in pre-order reasoing:

```agda
start
    {!  !}
≈⟨ {!   !} ⟩
    {!   !}
≈⟨ {!   !} ⟩
    {!   !}
≈⟨ {!   !} ⟩
    {!   !}
≈⟨ {!   !} ⟩
    {!   !}
□
```

## How to contribute

1. clone the repo and load it as a development package
2. open the repo in the development mode

```bash
apm develop language-agda
atom -d ~/github/language-agda
```
