.. _science:

Science behind the scenes
=========================

Novel thinking: hierarchy
--------------------------
Inspired by how humans understand languages and concepts, we turned to hierarchical models of language, an approach that uses hierarchies of modules, each of which can learn, remember, and recognize a sequential pattern.

The content of language is deeply hierarchical, reflected in the structure of language itself, going from letters to words to phrases to sentences to paragraphs to sections to chapters to books to authors to libraries, etc. Consider the message, "That interesting person at the cafe we like gave me a glance." The hierarchical chunks in this sentence are highly variable. The subject of the sentence is "That interesting person at the cafe we like." The modifier "interesting" tells us something about the writer's past experiences with the person. We are told that the location of an incident involving both the writer and the person is "at the cafe." We are also told that "we," meaning the writer and the person being written to, like the cafe. Additionally, each word is itself part of a hierarchy, sometimes more than one. A cafe is a type of restaurant which is a type of store which is a type of establishment, and so on.

In proposing an appropriate response to this message we might consider the meaning of the word "glance," which is potentially ambiguous. Was it a positive gesture? In that case, we might respond, "Cool!" Or was it a negative gesture? If so, does the subject say anything about how the writer felt about the negative exchange? A lot of information about the world, and an ability to make reasoned judgments, are needed to make subtle distinctions.

Given enough examples of language, a machine learning approach can discover many of these subtle distinctions. Moreover, a hierarchical approach to learning is well suited to the hierarchical nature of language. We have found that this approach works well for suggesting possible responses to emails. We use a hierarchy of modules, each of which considers features that correspond to sequences at different temporal scales, similar to how we understand speech and language.

Each module processes inputs and provides transformed representations of those inputs on its outputs (which are, in turn, available for the next level). In the Smart Reply system, and the figure above, the repeated structure has two layers of hierarchy. The first makes each feature useful as a predictor of the final result, and the second combines these features. By definition, the second works at a more abstract representation and considers a wider timescale.

By comparison, the initial release of Grammarly Autofill encoded input emails word-by-word with a long-short-term-memory (LSTM) recurrent neural network, and then decoded potential replies with yet another word-level LSTM. While this type of modeling is very effective in many contexts, even with Google infrastructure, it’s an approach that requires substantial computation resources. Instead of working word-by-word, we found an effective and highly efficient path by processing the problem more all-at-once, by comparing a simple hierarchy of vector representations of multiple features corresponding to longer time spans.

Semantics
---------
We have also considered whether the mathematical space of these vector representations is implicitly semantic. Do the hierarchical network representations reflect a coarse “understanding” of the actual meaning of the inputs and the responses in order to determine which go together, or do they reflect more consistent syntactical patterns? Given many real examples of which pairs go together and, perhaps more importantly which do not, we found that our networks are surprisingly effective and efficient at deriving representations that meet the training requirements.

So far we see that the system can find responses that are on point, without an overlap of keywords or even synonyms of keywords. More directly, we’re delighted when the system suggests results that show understanding and are helpful.

The key to this work is the confidence and trust people give us when they use the Grammarly Autofill feature. As always, thank you for showing us the ways that work (and the ways that don’t!). With your help, we’ll do our best to keep learning.


.. Autocomplete suggestions for text inputs in G Suite Add-ons <https://developers.google.com/gsuite/add-ons/how-tos/suggestions?authuser=0>