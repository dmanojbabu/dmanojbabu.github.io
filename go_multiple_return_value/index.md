# Golang: Multiple Return Values


Go has built-in support to return more than one values. 
<!--more-->

We have used In most programming languages, functions can return single value, but in Go, they can return any number of values.

The main use case of returning more than one values is to return the return the functions result and then the value to identify any error.


##### Example:1
The below function shows that the function returns result and then the value to identify any error

```golang
package main

import (
  "bufio"
  "fmt"
  "os"
  "strings"
  "strconv"
)

func main() {

  reader := bufio.NewReader(os.Stdin)
  fmt.Println("Quiz: Answer True/False")
  fmt.Println("Go is an open source programming language? ")
  name, _ := reader.ReadString('\n')
  name = strings.Replace(name, "\n", "", -1)

  var res bool = true
  res, err := strconv.ParseBool(name)
  if err != nil {
	       fmt.Println("Error: ", err)
	}
  fmt.Println("Input answer is = ", res)
}
```

##### Example:2

The below function shows that it returns 2 ints.

```golang
package main 

import "fmt"

func maxmin(a int, b int) (int, int) { 
	if a > b { 
		return a, b 
	} else { 
		return b, a 
	} 
} 

func main() { 
	var a = 30
	var b = 60

	var max, min = maxmin(a, b) 
	fmt.Println("Max = ", max, "\nMin = ", min) 
} 
```