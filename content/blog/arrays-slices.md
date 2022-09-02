---
title: Golang arrays and slices
slug: Golang arrays and slices
# url: Golang arrays and slices

date: 2022-09-01
description: This article teaches you everything you need to know about arrays in Golang
lead: Lets learn Golang arrays, how to declare them and how to use them.

---

After you finish this article you will start playing with arrays like pawns

<!--more-->

Grouping similar data, a collection of homogenuous data, is something pretty familiar in code, a list of strings or list of integers, or other types of data, Go has many ways to doing just that, Slices and Arrays
Lets take a look at arrays:

## Arrays

Arrays in Go, are similar to arrays in C.
Arrays in Go, are the simpler onces, but with a number of gotchas,
- Arrays size has to be defined at declaration time
- Its impossible to resize the array.
- If you pass an array to a function, you are passing a copy of the array, as result, all changes you make are only within the said function.

If you have a problem with any of this reasons, then the Good news, slices are here.

## Slices

Slices in Go, are much more powerful, specially with how dynamic they are, you can grow or shrink slices however you want.

Note that Slices are actually Arrays, each element is an array with a header, Go uses SliceHeader under the hood. where it does use a pointer to the underlying data.
```go
type SliceHeader struct {
    Data uintptr
    Len int
    Cap int
}
```
Here the advantage is passing the slice header is so fast, Go dosent need to make a copy of the slice and its elements. Just the slice header.
To create a slice we can use `make()` or like a slice literal `[]int{}`

### When to use `make`, and when `[]int` or `[]string` (aka slice literal)
- When you want to initialize it at the same time of creation, then using a slice literal is better `[]int{1,2,3}`
- If you dont want to initialize a slice, use `make()` its faster.
- If you want to create a slice with space for a number of elements then you can use `make([]string, 3)` a slice of strings, holding 3 elements. all elements are an empty string, a zero value of string `""`.


Then after slice creation you might want to either fill spaces that has no element (update), or just add new elements to the slice.
- To add more elements to a slice you do `names = append(names, "John", "Jane")`
- If you have an element with zero value, or any other value, you can just `names[i] = "Mohamed"` where the `i` is the index element of the slice.

### Go slices: `cap` capacity and length `len`
To check a slice `cap`, for capacity which means how many elements it has, including the ones with zero value, that you can use `theSlice[i] = "somevalue"`, without allocating more memory.
or `len` which is just for the length of the slice.
The capacity doubles whenever we attempt to add an element that is bigger than current capacity.
> ***Setting the correct capacity of a slice upfront, will make your code faster***

## Let's play

```go
// create an empty slice
var names := []string{}
// tthis prints out an empty slice, len and capacity both 0
//[] 0 0
fmt.Println(names, len(names), cap(names))
// Add elements
names = append(names, "John")
names = append(names, "Jane")
names = append(names, "Joe", "Jean")
// tthis prints out a slice ["John", "Jane", "Joe", "Jean"]
// length is 4, capacity is 4.
// [John Jane Joe Jean] 4 4
fmt.Println(names, len(names), cap(names))
```
Lets create a slice of 3 elements.
```go
t := make([]int, 3)
t[0] = 0
t[1] = 1
t[2] = 2
//[0 1 2] 3 3
fmt.Println(t, len(t), cap(t))
```
### panic: runtime error: index out of range [3] with length 3
```go
t := make([]int, 3)
t[0] = 0
t[1] = 1
t[2] = 2
//[0 1 2] 3 3
fmt.Println(t, len(t), cap(t))
// This line here causes a panic
// panic: runtime error: index out of range [3] with length 3
t[3] = 3
```

### append to a slice
```go
t := make([]int, 3)
t[0] = 0
t[1] = 1
t[2] = 2
//[0 1 2] 3 3
fmt.Println(t, len(t), cap(t))
// This line here causes a panic
// panic: runtime error: index out of range [3] with length 3
// t[3] = 3
t = append(t, 3)
// This returns the slice with length of 4, and capacity of 6 (double the previous one 3)
// [0 1 2 3] 4 6
fmt.Println(t, len(t), cap(t))
```
![append to a slice](img/append-to-a-slice.png "append to a slice")
