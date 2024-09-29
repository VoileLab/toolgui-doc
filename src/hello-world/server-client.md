# Server-Client

## Step by step Hello World

1. Create `main.go`:

```go
package main

import (
	"github.com/VoileLab/toolgui/toolgui/tgcomp"
	"github.com/VoileLab/toolgui/toolgui/tgexec"
	"github.com/VoileLab/toolgui/toolgui/tgframe"
)

func main() {
	app := tgframe.NewApp()
	app.AddPage("index", "Index", func(p *tgframe.Params) error {
		tgcomp.Text(p.Main, "Hello world")
		return nil
	})

	e := tgexec.NewWebExecutor(app).StartService(":3001")
}

```

2. Create go.mod and download toolgui:

```bash
go mod init toolgui-helloworld
go mod tidy
```

3. Run helloworld

```go
go run main.go
```

## Explain

* Create a ToolGUI App: The `App` intance include the info that app needs.

```go
app := tgframe.NewApp()
```

* Register a **page** in App: Tell `App` instance, we will have a page in the App.
  * `index` is the name.
  * `Index` is the title.

```go
app.AddPage("index", "Index", ...)
```

* The Page Func: Draw a text component in the **Main** container.

```go
func(p *tgframe.Params) error {
	tgcomp.Text(p.Main, "Hello world")
	return nil
}
```

* WebExecuter: The `App` only includes the logic of app, but not includes GUI.
The we executer provide web server GUI interface for `App`.

```go
tgexec.NewWebExecutor(app).StartService(":3001")
```
