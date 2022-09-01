---
title:  Golang bad file descriptor (how to append to a file)
slug: Golang bad file descriptor (how to append to a file)
date: 2022-09-01
# showTaxonomies: ["Go"]
tags: ["Go"]
categories: ["Beginner"]
# showTableOfContents: false
---

Golang bad file descriptor

<!--more-->
<!-- bad-file-descriptor -->
<!-- {{ $image.Resize "600x webp picture" }} -->
<!-- {{ $image := resources.Get "assets/img/bad-file-descriptor.png" }}
{{ with $image }}
  <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}">
{{ end }} -->

![Golang bad file descriptor](img/bad-file-descriptor.png "Golang bad file descriptor")

## Golang updating a file

When you use Golang, Its really a good idea, playing with files is actually fun, however this popular error, occurs when you want to update or append to a file, without deleteing the text written already.

## Golang creating a file

This is only possible if you want to write to the file for the first time.
```go
f, err := os.Create(fileName)
if err != nil {
    return err
}
_, err = f.WriteString("text")
if err != nil {
    return err
}
```

## Golang updating a file

This is how you open a file, and append to it.
{{< highlight go "linenos=false,hl_lines=1" >}}

f, err := os.OpenFile(fileName, os.O_CREATE|os.O_WRONLY|os.O_APPEND, os.ModePerm)
// the args: os.O_CREATE|os.O_WRONLY|os.O_APPEND, os.ModePerm
//f, err := os.Create(fileName)
if err != nil {
    return err
}
_, err = f.WriteString("text")
if err != nil {
    return err
}
{{< /highlight >}}

<!-- {{< highlight go "linenos=table,hl_lines=2" >}} -->

```go
f, err := os.OpenFile(fileName, os.O_CREATE|os.O_WRONLY|os.O_APPEND, os.ModePerm)
_, err = f.WriteString(c.text)
if err != nil {
    return err
}
```

<!-- {{< /highlight >}} -->

for more inforamtions please referr to [this stackoverflow link](https://stackoverflow.com/questions/33851692/golang-bad-file-descriptor).
