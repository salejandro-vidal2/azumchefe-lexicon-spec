# Schema
### Qualities of elements/attributes
- required : this element/attribute is required.
- indexed : this element/attribute is indexed.

## lexicon
- required

The lexicon. It contains lexical entries.
### label
- required

The label of the lexicon. (e.g. Oxford English Dictionary)
## lexical-entry
- required

A lexical entry. It contains forms and senses.
### lemma
- required
- indexed : refers to itself (e.g. [lemma] = [lemma])

The lemma (the canonical form) of the lexical entry.
### language
- required

The language (ISO 639-3) of the lexical entry.
## form
A form of the lexical entry.
### type

The type of form. (Is it an alternative spelling?)
### _text
- required
- indexed : refers to the lexical entry (e.g. [form] = [lemma])

The text content of the element.
## sense
- required

It contains definitions.
### partOfSpeech
- required

The part of speech of the sense.
### editorialNote

An editorial note of the sense.
## definition
- required

A definition. It contains examples.
### editorialNote
An editorial note of the definition.
### _text
- required

The text content of the element.
## example
An example/quote.
### author

The author of the quote.
### _text
- required

The text content of the element.
