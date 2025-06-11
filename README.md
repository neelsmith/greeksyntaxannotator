# Citable annotation of Greek syntax

> *A vibe-coded single-page web app for annotating the syntax of ancient Greek.*


`syntaxannotator.html` is an app for annotating the syntactic structure of a citable text in ancient Greek. When you load a text corpus, it is tokenized and segmented into sentences you can annotate in four steps:

1. identify connecting words (particles or conjunctions) relating this sentence to its context.
2. identify subject-verb expressions ("verbal units"), including participles and subject-verb expressions with infinitives
3. assign tokens to verbal units
4. define syntactic relations among tokens



It uses the same model of Greek syntax described in [this Julia package](https://neelsmith.github.io/GreekSyntax.jl), and serializes annotations to the  file format documented there.


## Contents

Version 2.x is a complete rewrite of the app. Its main features are:

- load a citable corpus from CEX source
- annotate syntax as summarized above
- save the results to a structured plain-text file



## Summary of values used in annotations




### Relations among tokens


- `conjunction`: joins two parallel items of any kind, and therefore should link to two nodes of the same kind
- `subordinate conjunction`: conjunction introducing a clause with explicit or implicit finite verb. Links to the `unitverb` of the superior clause; finite verb form of the subordinate links to this token as `unitverb`
- `relative pronoun`: this value relates a token to its antecedent substantive; it must have a second relation indicating its function in the subordinate clause. Frequently, this will be a relation to the verb of the suboridinate clause (as `subject`, `direct object` or `dative` relation), but could also be `object of preposition` of a preposition belonging to the subordinate clause.
- `unit verb`: every verbal unit should have an explicit or implicit token with a `unit verb` relation, unless the verbal unit is the initial independent clause in a sentence with asyndeton. Possible relations depend on the type of verbal unit:
    - `independent clause`: relate token to connecting word except in case of asyndeton
   - `subordinate clause`: relate token to subordinating conjunction or relative pronoun
    - `circumstantial participle`: relate participle to unit verb of superior verbal unit
    - `attributive participle`: relate participle to article?
    - `infinitive in indirect statement`: relate infinitive to verb of speaking
    - `participle in indirect statement`: relate participle to verb of speaking
    - `quote`: relate principal verb to implied or explicit verb of speaking
- `predicate`: relate
- `subject`
- `direct address`
- `complementary infinitive`
- `supplementary participle`
- `modal particle`
- `adverbial`
- `attributive`
- `article`
- `antecedent`
- `dative`: relation of a substantive to another token (verb, noun, adjective) expressed by dative case alone
- `genitive`: relation of two substantives expressed by genitive case alone



### Annotations on verbal units

Recognized syntactic types:

- independent clause
- subordinate clause
- circumstantial participle
- attributive participle
- infinitive in indirect statement
- participle in indirect statement
- quote

Recognized semantic types:


- transitive
- intransitive
- linking

## Caveats

The web app and accompanying guide was written entirely by gemini-2.5-pro. The code passes some sanity tests, but I have not even looked at the javascript. When I encountered errors, I let gemini fix them. Use the code as you like, but be aware that I have no idea what it does or how it works.


