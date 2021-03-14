# Golang How to Return Multiple Value and Error Handling


**Go** has built-in support to return more than one values and its main use case is to identify any error.

<!--more-->

## Synopsis

We have used In most programming languages, functions can return single value, but in Go, they can return any number of values.

The main use case of returning more than one values is to return the functions result and then the value to identify any error.


### Example:1 Function returns result and error

The below function shows that the function returns result and then the value to identify any error

{{< highlight golang "linenos=true,codeFences=true,lineNumbersInTable=true,noClasses=false" >}}

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
{{< /highlight >}}

### Example:2 Function return multiple value

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
