# Timepicker

Timepicker create a timepicker and return its selected time.

## API

```go
func Timepicker(s *tgframe.State, c *tgframe.Container, label string) string
```

* `s` is State.
* `c` is Parent container.
* `label` is the label for timepicker.

## Example

```go
dateValue := tgcomp.Datetimepicker(p.State, p.Main, "Datetimepicker")
tgcomp.TextWithID(p.Main, "Value: "+dateValue, "datetimepicker_result")
```

![timepicker component](timepicker.png)

