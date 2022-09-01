---
title: What is _ (underscore) in Go?
# slug: "golang-variables"
url: blank-identifier
date: 2022-08-23
description: If you did enconter _ (underscore), let me tell you what is it
lead: Underscore _ explained in Go.
# date: 2022-08-15T14:00:00.000Z
# series: ['Golang', 'Beginner']
# showTaxonomies:  ["Beginner"]
categories: ["Beginner"]
tags: ["Golang"]

cover:
  image: ![Alt text](/img/mohamedallam.jpg "Image caption")
  caption: golang missing function body or unexpected semicolon

---

Underscore _ demisified in Go.

<!--more-->
## Blank identifier

<!-- ![Alt text](/img/mohamedallam.jpg "Image caption") -->

The blank identifier is represented by the underscore character _. It serves as an anonymous placeholder instead of a regular (non-blank) identifier and has special meaning in declarations, as an operand, and in assignment statements.

Official Docs:
- [The Go Programming Language Specification](https://go.dev/ref/spec#Blank_identifier)
- [Effective Go](https://go.dev/doc/effective_go#blank)

## Why we use it?

As you know, in Golang, every should be used in its declaration scope, But what if you have a variable that is not used, and also irrelevant to you? The compiler will throw an exception, so to
Example

Its also common if you use a function that returns more than one value, and you want to ignore one of the values (commonly to test things out you ignore the error)
Underscore will be your friend, and if you want more details.

The blank identifier may be used whenever syntax requires a variable name but program logic does not, for instance to discard an unwanted loop index when we require only the element value.
- Copywrite The Go Programming Language (Addison-Wesley Professional Computing Series)

## Common use case

If you see an import statement with underscore, Jon Explains it here [Why we import SQL drivers as the blank identifier](https://www.calhoun.io/why-we-import-sql-drivers-with-the-blank-identifier/)
