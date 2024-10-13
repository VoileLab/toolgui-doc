# Number Input

NumberInput create a number input and return its value.

## API

### Interface

```go
func Number(s *tgframe.State, c *tgframe.Container, label string) int
func NumberWithConf(s *tgframe.State, c *tgframe.Container, label string, conf *NumberConf) int
```

### Parameters

* `s` is State.
* `c` is Parent container.
* `label` is the label of the number input.

```go
// NumberConf is the configuration for a number component.
type NumberConf struct {
	// Default is the default value of the number component.
	Default *float64

	// Min is the minimum value of the number component.
	Min *float64

	// Max is the maximum value of the number component.
	Max *float64

	// Step is the step of the number component.
	Step *float64

	// Color is the color of the number component.
	Color tcutil.Color

	// Placeholder is the placeholder of the number component.
	Placeholder string

	// Disabled is the disabled state of the number component.
	Disabled bool

	// ID is the ID of the number component.
	ID string
}

func (c *NumberConf) SetMin(min float64) *NumberConf {
	c.Min = &min
	return c
}

func (c *NumberConf) SetMax(max float64) *NumberConf {
	c.Max = &max
	return c
}

func (c *NumberConf) SetStep(step float64) *NumberConf {
	c.Step = &step
	return c
}
```

## Example

```go
numberValue := tgcomp.NumberWithConf(numberCompCol, p.State, "Number",
	(&tgcomp.NumberConf{
		Placeholder: "input the value here",
		Color:       tcutil.ColorSuccess,
	}).SetMin(10).SetMax(20).SetStep(2))

valStr := ""
if numberValue != nil {
	valStr = fmt.Sprint(*numberValue)
}

tgcomp.TextWithID(numberCompCol, "Value: "+valStr, "number_result")
```
