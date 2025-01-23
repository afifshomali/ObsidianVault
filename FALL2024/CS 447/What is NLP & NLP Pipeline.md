---
tags:
  - CS447
---
---
# What is NLP
---
![[Pasted image 20240828223239.png]]
![[Pasted image 20240828223436.png]]
![[Pasted image 20240828223709.png]]
Responses are not appropriate for context of the conversation 
![[Pasted image 20240828223823.png]]

## Huge Language Models to solve NLP? 
- A language model can be used to generate text. 
- Massive neural network trained on more text than any human has read
- ex GPT-3 
- But the models have no access to what the text actually means:
![[Pasted image 20240828224150.png]]

Still works need to be done

## Current State of NLP
- Lots of commercial applications and interests
	- Some working well while others not so much
- A lot of hype around Deep Learning and AI
	- Neural nets are powerful classifiers and sequence models
	- Public libraries and datasets make it easy for anybody to get a model up and running
	- End to end models put into question whether we still need tradition NLP pipeline
	- Still in the middle of this paradigm shift 
	- Still lots of fundamental problems that haven't gone away

## Examples of NLP applications
- Natural Language and speech interfaces
- Search/IR, database access, image search, image description
- Dialog systems like customer service, chatbots
- Information extraction, summarization, translation
- Process large amount of text automatically
- Convenience like grammar checking and automatic email filling

## NLP Tasks 
- Natural language understanding
	- Extract Information about the events, entities from text
	- Translate raw text into meaningful representation
	- Reason about the information given in the text
	- Execute NL instructions
- Natural language generation and summarization
	- Translate database entries
	- Produces appropriate responses
	- Summarize articles, describe images
- Natural language translation


# NLP Pipeline
---
## Tokenization/Segmentation
- Need to split text into words & sentences
	- Some languages don't have spaces between words
	- Some languages may define boundaries between what a word is, what a sentence is differently
- Even in English splitting can't be done deterministically:![[Pasted image 20240828225419.png]]
- So we want to know what the most likely segmentation/tokenization is 

## Part-of-Speech-tagging

![[Pasted image 20240828225537.png]]
Many different potential groupings for having parts of speech that is difficult for a computer but easy for us. Want to find the the tagging sequence with the highest probability 
![[Pasted image 20240828225807.png]]
This we can apply to any language and the specific parts of speech from those languages, some languages may have different parameters
![[Pasted image 20240828230012.png]]
![[Pasted image 20240828230230.png]]
Need to take context from other sentences to help with these ambiguities. But sometimes that may not even help like in the last example.
![[Pasted image 20240828230336.png]]

## Syntactic Parsing
![[Pasted image 20240828230406.png]]
This sentence is also a command
![[Pasted image 20240828230422.png]]

## What is grammar?
- Grammar formalisms (= linguists' programming languages)
	- A precises way to define and describe the structure of sentences
- Specific grammars (= linguists' programs)
	- Implementations for a particular language
![[Pasted image 20240828230747.png]]
Difficult to get perfect generation, Grammars will tend to always Over generate or Under generate
![[Pasted image 20240828230836.png]]

## Semantic Analysis
![[Pasted image 20240828230926.png]]
Can make up a logical representation of the sentence
![[Pasted image 20240828231152.png]]

## Understanding texts

- Means being able to answer questions about text 
![[Pasted image 20240828231312.png]]
![[Pasted image 20240828231420.png]]
![[Pasted image 20240828231516.png]]
![[Pasted image 20240828231537.png]]
![[Pasted image 20240828231640.png]]

