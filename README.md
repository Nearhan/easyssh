# easyssh
Golang package for easy remote execution through SSH

So easy to use!

For example `ps ax`

```
package main

import (
	"fmt"

	"github.com/weekface/easyssh"
)

func main() {
	ssh := &easyssh.MakeConfig{
		User:   "cjc",
		Server: "localhost",
		Key:    "/.ssh/id_rsa",
	}

	err := ssh.Scp("/home/cjc/zipkin.rb")

	if err != nil {
		panic("Can't run remote command: " + err.Error())
	} else {
		fmt.Println("success")
	}
}
```

For scp function, see: example/scp.go
