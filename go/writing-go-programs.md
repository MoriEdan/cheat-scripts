Writing Go Programs cheats
==========================

<h4>Workspaces</h4>
<p>
src: Go source files organized into packages<br>
pkg: contains package objects<br>
bin: contains executable commands<br>
</p>

<h4>Create Workspace</h4>
<pre>
$ cd ~
$ mkdir go
</pre>

<h4>Create environment variable</h4>
<pre>
$ export GOPATH = $HOME/go
$ export PATH=$PATH:$GOPATH/bin
</pre>

<h4>Sample Program</h4>
<pre>
$ cd $GOPATH
$ mkdir src/github.com/your_username/hello_world
$ nano hello.go
# add to the file

package main
import "fmt"
func main() {
	fmt.Printf("Hello, world.\n")
}
</pre>

<h4>Build Program</h4>
<pre>
$ go install github.com/your_username/hello_world
or
$ cd $GOPATH
$ cd github.com/your_username/hello_world
$ go install
</pre>

<h4>Run Program</h4>
<pre>
$ hello
</pre>


<h4>Create package directory</h4>
<pre>
$ cd $GOPATH/src/github.com/your_username
$ mkdir formula
$ cd formula
$ nano sqrt.go
# add to the file: 

package formula

func Sqrt(x float64) float64 {
	z := 1.0
	for i := 0; i &lt; 1000; i++ {
		z -= (z*z - x) / (2 * z)
	}
	return z
}

</pre>

<h4>Build Package</h4>
<pre>
$ go build github.com/your_username/formula
</pre>

<h4>Add Package to existing program</h4>
<pre>
package main
import (
	"fmt"
	"github.com/user/formula"
)
func main() {
	fmt.Printf("Hello, world.  Sqrt(2) = %v\n", formula.Sqrt(2))
}

</pre>

<h4>Build Program w/ package dependency</h4>
<pre>
$ go install github.com/your_username/hello_world
</pre>

<h4>Run Program w/ package dependency</h4>
<pre>
$ hello
</pre>
