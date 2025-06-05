OK, let's try this. Add an option for the user to download the annotations data. We'll write data for sentences, verbal units, and tokens to a single plain-text file, with 3 blocks of delimited-text data.

The first block will begin with a labelling line `#!sentences`, followed by a pipe-delimited header line `sentence|sequence|connector`. This will be followed by one line for each annotated sentence, with three pipe-delimited columns. The first column will be the identifier for the sentence in the form used in the user menu. The second column will be the sequence number of that sentence in the menu. The third column will be an identifier for the connecting word, or empty if the sentence illustrates asyndeton. The identifier to use is the `urn` property of the `Token` object that the user chose as the connecting word.
**Example**: If the user chose a sentence identifier `urn:cts:greekLit:tlg0540.tlg001.omar_tokens:1.6.1-1.6.46a`, and it was the tenth sentence in the menu, then chose a token with text value `γὰρ` that was identified by the `urn` property `urn:cts:greekLit:tlg0540.tlg001.omar_tokens:1.6.2`, that would be represented with this line:

`urn:cts:greekLit:tlg0540.tlg001.omar_tokens:1.6.1-1.6.46a|10|urn:cts:greekLit:tlg0540.tlg001.omar_tokens:1.6.2`


The second block will begin with a labelling line `#!verbal_units`, then the pipe-delimited header line `vuid|syntactic_type|semantic_type|depth|sentence`, followed by one pipe-delimited line of data for each verbal unit. `vuid` is a unique id for this verbal unit; `syntactic_type`, `semantic_type`, and `depth` are the values of the columns "Syntactic type", "Semantic type",  and "Depth", respectively. `sentence` is the same ID value for the sentence that was used in the first block of sentences (and hence can be used by other applications to join verbal units and sentences)

The third block will begin with a labelling line  `#!tokens`, then the pipe-delimited header line `urn|reference|tokentype|text|verbalunit|node1|node1relation|node2|node2relation`.  This will be followed by one line for each token assigned to a verbal unit. It is very important that for the first column record the value of the `urn` property of the `Token` object that was annotated. The remaining columns will have the values of the columns "Reference", "Token", "Node 1 (ID)", "Node 1 Relation", "Node 2 (ID)", and "Node 2 Relation" from the user-edited table.

Please implement this.

--

Great! Let's move the "Download Annotations" section to the bottom of the page, below the table where the user edits relations of tokens. Can you let the user select a name for the local output file, with a default of "greek_annotations.cex" ?

---

Excellent. Two tiny tweaks. 1) Let's keep the "Download Annotations" section hidden until the user has actually defined at least one token realtion in Mode 4. 

2) In the "Verbal Unit Token Grouping" section, we should ignore any connecting word the user has identified. **Example**: Consider a sequence where, of the first 3 tokens, where token 1 belongs to verbal unit 1, token 2 is the connector token, and token 3 belongs to verbal unit. We place token 1 on a line to start the display. We ignore token 2 because it's the connector token. We see that connector 3 belongs to verbal unit 1 and look at the preceding token -- but here that means we should look at token 1 since we're ignoring the connector. We see that token 1 also belongs to verbal unit 1, so we continue token 3 on the same line. 

Could you implement this?

---

Perfect!