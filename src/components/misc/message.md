# Message

Message is a component that displays a message.

## API

### Interface

```go
func Message(c *tgframe.Container, text string)
func MessageWithConf(c *tgframe.Container, text string, conf *MessageConf)
```

### Parameters

* `c`: Parent container.
* `text`: Text to display.
* `conf`: Configuration for the message component.

```go
type MessageConf struct {
	// Title is the title of the message. Optional.
	Title string

	// Color is the color of the message. Default is tcutil.ColorNull.
	Color tcutil.Color

	// ID is the unique identifier of the component.
	ID string
}
```

## Example

```go
tgcomp.Message(c, "Hello, World!")
```

```go
tgcomp.MessageWithConf(c, "Hello, World!", &tgcomp.MessageConf{
	Title: "Info",
	Color: tcutil.ColorInfo,
})
```