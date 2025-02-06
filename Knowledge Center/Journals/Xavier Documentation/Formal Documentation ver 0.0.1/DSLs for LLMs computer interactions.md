---
sticker: lucide//newspaper
---
# Xavier xScript DSL - Language Definition

## Version

**xScript Version**: 0.0.1

## Introduction

The `xScript` language is designed for efficient interaction between an AI (e.g., Xavier) and various computational environments such as file systems, APIs, and the Internet. This document defines the syntax and structure of `xScript` to enable interpretable and executable commands.

---

## Comment Syntax

- **Single-line comment**: `-- Your comment here`
- **Multi-line comment**: `--- Your multi-line comment here ---`

---

## Variable Definitions

### Basic Variable Definition

Variables are defined using the following syntax:

```xScript
def variableName -> value
```

**Example:**

```xScript
def x -> 2
```

This defines a variable `x` with the value `2`.

### File Variable with Multiline Content

Variables of type `File` can hold multiline content using the following syntax:

```xScript
def variableName :: File ->
beginFile as fileExtension

endFile
```

**Example:**

```xScript
def report :: File ->
beginFile as md
*A Markdown Value for the content*.
endFile
```

---

## Data Types

`xScript` supports the following types:

- `string`
- `int`
- `double`
- `boolean`
- `path`
- `file`
- `time`

### Complex Data Types

- Lists: Append `[]` to a type (e.g., `string[]` for a list of strings).
- Pairs: Use `<type1, type2>` (e.g., `<double, string>` for a double and a string).

---

## Language Constructs

### Calling an Action

Actions are invoked using the following syntax:

```xScript
do ActionName :: param1 : value1, param2 : value2
```

**Example:**

```xScript
do calculateSum :: num1 : 5, num2 : 10
```

_Note: While defining functions and variables, types are required, but when invoking functions, types are omitted._

### Categorizing Actions

Actions can be grouped into categories for better organization. Use this syntax:

```xScript
@ CategoryName {
    def varName -> value
    do ActionName :: param1 : value1, param2 : value2
    def variableName :: File ->
    beginFile as fileExtension
    The multi-line content value
    endFile
}
```

**Example:**

```xScript
@ MathOperations {
    def pi -> 3.14159
    do calculateArea :: radius : 5
}
```

---

## Predefined Categories and Commands

The following categories and commands are predefined in `xScript`.

### Terminal

```xScript
@ Terminal {
    do changeDirectory :: path : /home/user
    do makeDirectory :: path : /home/user/newDir
    do moveFile :: origin : /file.txt, destination : /newDir
    do deleteFile :: filePath : /file.txt
    do listfiles :: path : /home/user
    do getCurrentDirectory ::

    def currentPath -> /home/user;  -- Stores the current directory path
}
```

### Git

```xScript
@ Git {
    do cloneRepository :: repoUrl : "https://github.com/repo.git", destination : /home/user/repo
    do commitChanges :: message : "Initial commit"
    do pushChanges :: branch : "main"
    do getStatus ::;

    def currentBranch -> "main"  -- Stores the current branch name
}
```

### Google

```xScript
@ Google {
    do search :: query : "xScript language"
    do searchImages :: query : "xScript language images"
    do searchScholar :: query : "xScript language research"

    def searchQuery -> "xScript language"  -- Stores the most recent search query
}
```

### Arxiv

```xScript
@ Arxiv {
    do searchPapers :: query : "quantum computation"
    do getPaper :: paperId : "1234.56789"
    do searchByAuthor :: author : "John Doe"

    def arxivQuery -> "quantum computation"  -- Stores the most recent Arxiv search query
}
```

### Wikipedia

```xScript
@ Wikipedia {
    do search :: query : "Quantum mechanics"
    do getSummary :: pageTitle : "Quantum mechanics"
    do getFullArticle :: pageTitle : "Quantum mechanics"

    def wikiQuery -> "Quantum mechanics"  -- Stores the most recent Wikipedia search query
}
```

---

## Additional Notes

1. New categories and commands must align with the existing syntax and structure.
2. When Xavier produces text, he can make inline code blocks for commands using the `xScript` syntax:

```xScript
commands here
```

3. Xavier can also write normal text to interact with users.

---