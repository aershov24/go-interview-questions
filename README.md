# Golang Interview Questions and Answers

Go hits the very sweet spot of performance and speedy development. It takes some elements from dynamic languages like Python and couples them with static typing at compile time. And according ZipRecruiter Golang Developer Annual Salary in US is $125,851.

> You could also find all the answers here 👉 https://www.fullstack.cafe/Golang.


<p align="center">
  <a href="https://www.fullstack.cafe">
  <img src="https://user-images.githubusercontent.com/13550565/73042889-e7533900-3e9d-11ea-94f2-b4a9e87cc018.png">
  </a>
</p>


## Q1: What is Go? ⭐

**Answer:**

**Go** is a general-purpose language designed with systems programming in mind. It was initially developed at Google in year 2007 by Robert Griesemer, Rob Pike, and Ken Thompson. It is strongly and statically typed, provides inbuilt support for garbage collection and supports concurrent programming. Programs are constructed using packages, for efficient management of dependencies. Go programming implementations use a traditional compile and link model to generate executable binaries.

🔗 **Source:** [tutorialspoint.com](https://www.tutorialspoint.com/go/go_interview_questions.htm)


## Q2: Is Go a new language, framework or library? ⭐

**Answer:**

**Go** isn't a library and not a framework, it's a new language. 

Go is mostly in the C family (basic syntax), with significant input from the Pascal/Modula/Oberon family (declarations, packages). Go does have an extensive library, called the runtime, that is part of every Go program. Although it is more central to the language, Go's runtime is analogous to libc, the C library. It is important to understand, however, that Go's runtime does not include a virtual machine, such as is provided by the Java runtime. Go programs are compiled ahead of time to native machine code.

🔗 **Source:** [golang.org](https://golang.org/doc/faq)


## Q3: What are the benefits of using Go programming? ⭐⭐

**Answer:**

Following are the benefits of using Go programming:

*   Support for environment adopting patterns similar to dynamic languages. For example type inference (`x := 0` is valid declaration of a variable `x` of type `int`).
*   Compilation time is fast.
*   In built concurrency support: light-weight processes (via goroutines), channels, select statement.
*   Conciseness, Simplicity, and Safety.
*   Support for Interfaces and Type embedding.
*   The go compiler supports static linking. All the go code can be statically linked into one big fat binary and it can be deployed in cloud servers easily without worrying about dependencies.

🔗 **Source:** [tutorialspoint.com](https://www.tutorialspoint.com/go/go_interview_questions.htm)


## Q4: What is static type declaration of a variable in Go? ⭐⭐

**Answer:**

*Static type variable declaration* provides assurance to the compiler that there is one variable existing with the given type and name so that compiler proceed for further compilation without needing complete detail about the variable. A variable declaration has its meaning at the time of compilation only, compiler needs actual variable declaration at the time of linking of the program.

🔗 **Source:** [tutorialspoint.com](https://www.tutorialspoint.com/go/go_interview_questions.htm)


## Q5: What is dynamic type declaration of a variable in Go? ⭐⭐

**Answer:**

A *dynamic type variable declaration* requires compiler to interpret the type of variable based on value passed to it. Compiler don't need a variable to have type statically as a necessary requirement.

🔗 **Source:** [tutorialspoint.com](https://www.tutorialspoint.com/go/go_interview_questions.htm)


## Q6: Can you declared multiple types of variables in single declaration in Go? ⭐⭐

**Answer:**

Yes. Variables of different types can be declared in one go using type inference.

```go
var a, b, c =  3,  4,  "foo"  
```

🔗 **Source:** [tutorialspoint.com](https://www.tutorialspoint.com/go/go_interview_questions.htm)


## Q7: What is a pointer? ⭐⭐

**Answer:**

A **pointer variable** can hold the *address* of a variable.

Consider:
```go
var x =  5  var p *int p =  &x
fmt.Printf("x = %d",  *p)
```

Here `x` can be accessed by `*p`.

🔗 **Source:** [tutorialspoint.com](https://www.tutorialspoint.com/go/go_interview_questions.htm)


## Q8: Can you return multiple values from a function? ⭐⭐

**Answer:**

A Go function can return multiple values.

Consider:
```go
package main
import "fmt"

func swap(x, y string) (string, string) {
   return y, x
}
func main() {
   a, b := swap("Mahesh", "Kumar")
   fmt.Println(a, b)
}
```

🔗 **Source:** [tutorialspoint.com](https://www.tutorialspoint.com/go/go_interview_questions.htm)


## Q9: What are some advantages of using Go? ⭐⭐

**Answer:**

**Go** is an attempt to introduce a new, concurrent, garbage-collected language with fast compilation and the following benefits: 
* It is possible to compile a large Go program in a few seconds on a single computer.
* Go provides a model for software construction that makes dependency analysis easy and avoids much of the overhead of C-style include files and libraries.
* Go's type system has no hierarchy, so no time is spent defining the relationships between types. Also, although Go has static types, the language attempts to make types feel lighter weight than in typical OO languages.
* Go is fully garbage-collected and provides fundamental support for concurrent execution and communication.
* By its design, Go proposes an approach for the construction of system software on multicore machines.

🔗 **Source:** [golang.org](https://golang.org/doc/faq)


## Q10: Why the Go language was created? ⭐⭐

**Answer:**

**Go** was born out of frustration with existing languages and environments for systems programming. 

Go is an attempt to have:
* an interpreted, dynamically typed language with 
* the efficiency and safety of a statically typed, compiled language
* support for networked and multicore computing
* be fast in compilation

To meet these goals required addressing a number of linguistic issues: an expressive but lightweight type system; concurrency and garbage collection; rigid dependency specification; and so on. These cannot be addressed well by libraries or tools so a new language was born.


🔗 **Source:** [golang.org](https://golang.org/doc/faq)


## Q11: Does Go have exceptions? ⭐⭐

**Answer:**

No, Go takes a different approach. For plain error handling, Go's **multi-value returns** make it easy to report an error without overloading the return value. Go code uses error values to indicate an abnormal state. 

Consider:
```go
func Open(name string) (file *File, err error)
```
```go
f, err := os.Open("filename.ext")
if err != nil {
    log.Fatal(err)
}
// do something with the open *File f
```

🔗 **Source:** [golang.org](https://golang.org/doc/faq)


## Q12: What are Goroutines? ⭐⭐

**Answer:**

**Goroutines** are functions or methods that run concurrently with other functions or methods. Goroutines can be thought of as light weight threads. The cost of creating a Goroutine is tiny when compared to a thread. Its common for Go applications to have thousands of Goroutines running concurrently.

🔗 **Source:** [golangbot.com](https://golangbot.com/goroutines/)


## Q13: Let's talk variable declaration in Go. Could you explain what is a variable "zero value"? ⭐⭐

**Answer:**

Variable is the name given to a memory location to store a value of a specific type. There are various syntaxes to declare variables in go.

```go
// 1 - variable declaration, then assignment
var age int
age = 29

// 2 - variable declaration with initial value
var age2 int = 29

// 3 - Type inference
var age3 = 29

// 4 - declaring multiple variables
var width, height int = 100, 50

// 5 - declare variables belonging to different types in a single statement
var (  
      name1 = initialvalue1,
      name2 = initialvalue2
)
// 6 - short hand declaration
name, age4 := "naveen", 29 //short hand declaration
```

If a variable is not assigned any value, go automatically initialises it with the **zero value of the variable's type**. Go is strongly typed, so variables declared as belonging to one type cannot be assigned a value of another type.

🔗 **Source:** [golangbot.com](https://golangbot.com/variables/)


## Q14: What kind of type conversion is supported by Go? ⭐⭐

**Answer:**

Go is very strict about **explicit typing**. There is no automatic type promotion or conversion. Explicit type conversion is required to assign a variable of one type to another. 

Consider:
```go
i := 55      //int
j := 67.8    //float64
sum := i + int(j) //j is converted to int
```

🔗 **Source:** [golangbot.com](https://golangbot.com/types/)


## Q15: How to efficiently concatenate strings in Go? ⭐⭐

**Questions Details:**

In Go, a `string` is a primitive type, which means it is read-only, and every manipulation of it will create a new string.

So if I want to concatenate strings many times without knowing the length of the resulting string, what's the best way to do it?


**Answer:**

Beginning with Go 1.10 there is a `strings.Builder`. A Builder is used to efficiently build a string using Write methods. It minimizes memory copying. The zero value is ready to use.

```go
package main

import (
    "strings"
    "fmt"
)

func main() {
    var str strings.Builder

    for i := 0; i < 1000; i++ {
        str.WriteString("a")
    }

    fmt.Println(str.String())
}
```

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/1760757/how-to-efficiently-concatenate-strings/47798475#47798475)


## Q16: Explain this code ⭐⭐

**Questions Details:**

In Go there are various ways to return a struct value or slice thereof. Could you explain the difference?

```go
type MyStruct struct {
    Val int
}

func myfunc() MyStruct {
    return MyStruct{Val: 1}
}

func myfunc() *MyStruct {
    return &MyStruct{}
}

func myfunc(s *MyStruct) {
    s.Val = 1
}
```


**Answer:**

Shortly: 
* the first returns a copy of the struct, 
* the second a pointer to the struct value created within the function, 
* the third expects an existing struct to be passed in and overrides the value.

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/23542989/pointers-vs-values-in-parameters-and-return-values)


## Q17: Have you worked with Go 2? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q18: Name some advantages of Goroutines over threads ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q19: Is Go an object-oriented language? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q20: What is "rune" type in Go? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q21: What is so special about constants in Go? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q22: How to initialise a struct in Go? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q23: How to check if a map contains a key in Go? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q24: Is there a foreach construct in the Go language? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q25: Can Go have optional parameters?  ⭐⭐⭐

**Questions Details:**

Or can I just define two functions with the same name and a different number of arguments?


 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q26: What is the preferred way to handle configuration parameters for a Go program? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q27: What is the difference between the = and := operator?  ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q28: What is the difference between C.sleep() and time.Sleep()? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q29: What are the differences between unbuffered and buffered channels? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q30: Why would you prefer to use an empty struct{}? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q31: How do you swap two values? Provide a few examples. ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q32: Implement a function that reverses a slice of integers ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q33: How to copy map in Go? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q34: What would you do if you need a hash displayed in a fixed order? ⭐⭐⭐

**Questions Details:**

You would need to sort that hash’s keys.

```go
fruits := map[string]int{
	"oranges": 100,
	"apples":  200,
	"bananas": 300,
}

// Put the keys in a slice and sort it.
var keys []string
for key := range fruits {
	keys = append(keys, key)
}
sort.Strings(keys)

// Display keys according to the sorted slice.
for _, key := range keys {
	fmt.Printf("%s:%v\n", key, fruits[key])
}
// Output:
// apples:200
// bananas:300
// oranges:100
```


 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q35: List the functions can stop or suspend the execution of current goroutine, and explain their differences. ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q36: What is an idiomatic way of representing enums in Go? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q37: What are the use(s) for tags in Go? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q38: How to find a type of an object in Go? ⭐⭐⭐⭐

**Questions Details:**

How do I find the type of an object in Go? In Python, I just use `typeof` to fetch the type of object. Similarly in Go, is there a way to implement the same ?


 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q39: When is the init() function run? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q40: What is the idiomatic Go equivalent of C's ternary operator? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q41: How can I check if two slices are equal? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q42: How does Go compile so quickly? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q43: What might be wrong with the following small program? ⭐⭐⭐⭐

**Questions Details:**

```go 
func main() {
	scanner := bufio.NewScanner(strings.NewReader(`one
two
three
four
`))
	var (
		text string
		n    int
	)
	for scanner.Scan() {
		n++
		text += fmt.Sprintf("%d. %s\n", n, scanner.Text())
	}
	fmt.Print(text)

	// Output:
	// 1. One
	// 2. Two
	// 3. Three
	// 4. Four
}
```

The program numbers the lines in a buffer and uses the `text/scanner` to read the input line-by-line. What might be wrong with it?


 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q44: Briefly describe how GC works in GO? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q45: What is $GOROOT and $GOPATH? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q46: What is the difference, if any, in the following two slice declarations, and which one is more preferable? ⭐⭐⭐⭐

**Questions Details:**

```go
var a []int
```
and 
```go
a := []int{}
```


 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q47: When go runtime allocates memory from heap, and when from stack? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q48: What is the malloc threshold of Map object? How to modify it? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**


## Q49: How to compare two interfaces in Go? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Golang)**



