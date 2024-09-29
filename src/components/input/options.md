# Options

Radio create a group of radio items and return its selected value.

## API

```go
func Radio(s *tgframe.State, c *tgframe.Container, label string, items []string) string
```

* `s` is State.
* `c` is Parent container.
* `label` is the label for options group.
* `items` is the list of options.

## Example

```go
radioValue := tgcomp.Radio(p.State, p.Main, "Radio", []string{"Value3", "Value4"})
tgcomp.TextWithID(p.Main, "Value: "+radioValue, "radio_result")
```

![options component](options.png)
