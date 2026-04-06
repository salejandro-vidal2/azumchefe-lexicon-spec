# How to read this file?
Some considerations before reading this file.
### Comments
Written in parenthesis next to the element/attribute's title.
- deprecated : the element/attribute should not be used.
- proposal_* : the element/attribute is proposed in proposal_*.

### Qualities of elements/attributes
Written as a list below the element/attribute's title.
- required : the element/attribute is required.
- indexed : the element/attribute is key in indexation.

### Other
**Impl.** : implementation advice.

# Schema

## lexicon
- required

The lexicon. It contains lexical entries.
  ### label
  - required
  
  The label of the lexicon. (e.g. Oxford English Dictionary)
  ### language
  - required
  
  The language (ISO 639-3) of the lexicon. (e.g. 'spa' meaning Spanish)
  ### alphabetOrder (proposal_06042026)
  The order of the alphabetic letters in index. 

  Describes the alphabet order in index. If not present, will just use the traditional latin order.
## lexical-entry
- required

A lexical entry. It contains forms and senses.
  ### lemma
  - required
  - indexed

  The lemma (the canonical form) of the lexical entry.

  **Impl.**: It should be exposed in indexation; When queried, it should refer to itself (e.g. refer Key[lemma] to Value[lemma]).
  ### etymology
  The etymology of the lexical entry.
  ### editorialNote
  The editorial note of the lexical entry.

  Used for notes left by editors. Can also be used as a 'one fits all' category.
## refer
A reference to another lexical entry.
  ### to
  Where the reference leads to.
  ### isExternal
  Does the reference redirect to external sources?

## form
A form of the lexical entry. 

Forms are variations of a lemma (either phonetical or morphological). 

**Impl.**: It should be exposed in indexation; When queried, it should refer to its parent lemma (e.g. refer Key[form] to Value[parent-lemma]).

  ### type
  
  The type of form. (e.g. Is it an alternative spelling?)
  ### _text
  - required
  
  The text content of the element.
## sense
- required

It contains definitions.
  ### partOfSpeech
  - required

  The part of speech of the sense.

  Denotes the use of the sense in speech.
  ### restrictionMark
  The restricion mark of the sense. 
  
  Refers the use of the sense to a specific context or location. (e.g. 'bot' meaning _Bot._ [Botany])
  ### editorialNote
  The editorial note of the sense.

  Used for notes left by editors. Can also be used as a 'one fits all' category.
## definition
- required

A definition. It contains examples.
  ### editorialNote
  The editorial note of the definition.

  Used for notes left by editors. Can also be used as a 'one fits all' category.
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
