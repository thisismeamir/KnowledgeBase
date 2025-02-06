---
File: Knowledge Center/Journals/Computer Science/Domain Specific Language/Introduction to MPS.md
sticker: lucide//newspaper
---
>*The following is a note taken from reading the book* 
# Overview
MPS is an open-source language workbench by Jetbrains that focuses on domain-specific-languages. The name of the tool, MPS, is an acronym for Meta-Programming-System, which emphasizes the focus on meta-programming.

[[Domain Specific Language]] is a fairly established idea of using custom-tailored languages to describe programs or parts of them, such as algorithms or configuration specifications, using notations specific to a particular domain.

DSLs proponents claim that using a mixture of single-purpose DSLs in concert brings benefits such as higher abstraction level, fewer errors in code, smaller technology lock-in, and better communication between developers and business people compared to using a single general-purpose language.

---
# MPS Terminology and Notations
People sometimes get confused about how code is represented in computer programs. Compilers, interpreters and IDEs need to manipulate code that the user has provided. Code is typically stored in text files and the extension of the file indicates the languages used by that file. Computer programs, in order to represent the code in memory, need to read the files and process them with a special tool, called parser. 

Parser uses the known grammar of the language to distinguish individual tokens in the text file and to assign meaning to them. As parser reads the file it gradually builds a data structure that is known as the Abstract Syntax Trees (AST for short) are used by the IDEs to provide assistance to the user, and are used by the compilers to perform transformations that gradually convert the tree into runnable binary code.

## Abstract Syntax Tree 
MPS is different from other language workbenches by avoiding the text form. The programs are always represented by an AST, in memory, and during transformation and code generation. This means that no grammar definitions or parsers are needed to define a language in MPS.

## Node
Nodes from an AST. Each node has a parent node, child nodes, properties and references to other nodes. The nodes that don't have a parent are called root nodes. These are top-most elements of ASTs, For example, in Java the root nodes are classes, interfaces and enums.

## Concept
Nodes can be very different from one another—an if statement certainly looks different than a variable declaration. It is the concept of a node that codifies how a node will behave and what purpose it has in code. Each node stores a reference to its concept. The concept defines the class of nodes and coins the structure of nodes in that class. It specifies which children, properties, and references an instance of a node can have. Concept declarations form an inheritance hierarchy. If one concept extends another, it inherits all children, properties, and references from its superconcept. While nodes compose ASTs, concepts define the possible “categories” of nodes.

## Models vs. Meta-models
The terms models and meta-models are known from model-driven software design. While “models” represent user code, “meta-models” represent the “abstractions” available for creating those “models.” This is somewhat similar to the distinction between “instances” and “classes” in object-oriented programming, where “classes” provide the framework and developers create “instances” of these “classes” in order to create functional systems. In MPS “meta-models” are represented as languages, which hold concepts, and “models” are represented as user code, which consists of nodes in ASTs.

## Language
A language in MPS is a set of concepts with some additional information. The additional information includes details on editors, completion menus, intentions, typesystem, dataflow, etc. associated with the language. A language can extend another language and thus define additional qualities for concepts defined in the extended language.

## Modules
Modules are independent reusable collections of code. There are four types of modules in MPS:
1. *Solution:* represents a piece of user code and is equivalent to how code is structured in traditional IDEs. 
2. *Language:* represents language definition.
3. *Generator:* represents definition of code transformations into another language.
4. *DevKit:* Groups modules for easy reference; does not add any new code or functionality. A module can be a part of multiple DevKits

## Models
Internally, modules are structured into models. Models are a language-agnostic equivalent of Java's packages, Ruby's modules, or JavaScript folders. Modules hold root nodes, which are a rough equivalent to files in traditional languages. Root nodes are code. Technically, they represent the roots of trees and hold other nodes organized into a tree-like hierarchy.

Additionally, MPS has the capacity to organize code inside models hierarchically into what are called virtual packages.

## Generator
The generator gives the code meaning. It transforms the model into a model that uses a different language, typically on a lower level of abstraction. Generation in MPS is done in phases—the output of one generator can become the input for another generator in a pipeline. An optional model-to-text conversion phase (TextGen) may follow to generate code in a textual format. This staged approach helps bridge potentially big semantics gaps between the original problem domain and the technical implementation domain. It also encourages reuse of generators.

## BaseLanguage
MPS comes with a clone of Java language, called BaseLanguage. Since Java is a traditional parser-based GPL, it cannot be used directly in MPS as is, but had to be re-implemented using the MPS language definition mechanisms. This re-implementation is called BaseLanguage. The word base highlights that it is:
1. The fundamental language used throughout MPS to write language definitions logic.
2. A typical target of code generation--high-level DSL code is generated into BaseLanguage, which in turn can be represented as Java source code and then compiled with a Java compiler.
Although originally BaseLanguage copied Java in version 6, numerous extensions have been created over time to provide additional capabilities and bring in many of the later Java features.

However convenient, BaseLanguage is not the only desired target language for code generation. The generator can transform models between any languages, if and only if they have MPS-based definitions available.

---
![[Pasted image 20241229150206.png]]
# Projectional Editor
Editing code in MPS differs fundamentally from other, more traditional, tools. MPS is based on the concept of projectional editor, which is an invention from the 1970s that has been so far adopted mostly by tools outside of the programming mainstream. In essence, a projectional editor lets the developer manipulate the i-memory representation of the code directly, instead of letting them type characters that need to be parsed by the tool.

From the user perspective this feels somewhat similar to editing math formulas in popular text processors.

The editor takes care of the structure of the code and the developer fills in the blanks. Since the code is never represented in a plain text form, there is no need for parsing text in order to build the in-memory representation of code. The code is always in this form—on disk as well as in memory. The challenge for projectional editors is to hide the fact that the user is manipulating the AST. Historically, the editors were not very successful in making text editing convenient enough for the programming community to adopt it widely. Its applicability has thus been limited to only a few domains.

MPS has made an attempt to improve projectional editing and make it universally applicable to a wide range of possible notations. The key element of the MPS projectional editor is the idea of node transformations. When the user presses a key on the keyboard, it is not understood as a character that needs to be inserted into a text document, but instead it is handled as an event by the part of the AST that holds the cursor at that moment. 

A key event is announced to the registered listeners on that particular node of the AST and they will handle the event, typically by transforming the AST to reflect the character represented by the event.

## Notations
The notation directly influences the success of a language. People frequently adopt or refuse a language depending on how familiar they feel when interacting with the code. The notation thus should be simple and concise and provide sensible defaults. If a preferred notation exists already in the domain, it is advisable to reuse to adapt it in the new language.

