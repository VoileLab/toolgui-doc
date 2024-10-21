# Number Input

NumberInput create a number input and return its value.

## API

### Interface

```go
func NumberFloat64(s *tgframe.State, c *tgframe.Container, label string) *float64
func NumberWithConfFloat64(s *tgframe.State, c *tgframe.Container, label string, conf *NumberConf[float64]) *float64

func NumberInt64(s *tgframe.State, c *tgframe.Container, label string) *int64
func NumberWithConfInt64(s *tgframe.State, c *tgframe.Container, label string, conf *NumberConf[int64]) *int64
```

### Parameters

* `s` is State.
* `c` is Parent container.
* `label` is the label of the number input.

```go
// NumberConf is the configuration for a number component.
type NumberConf[T float64 | int64] struct {
	// Default is the default value of the number component.
	Default *T

	// Min is the minimum value of the number component.
	Min *T

	// Max is the maximum value of the number component.
	Max *T

	// Step is the step of the number component.
	Step *T

	// Color is the color of the number component.
	Color tcutil.Color

	// Placeholder is the placeholder of the number component.
	Placeholder string

	// Disabled is the disabled state of the number component.
	Disabled bool

	// ID is the ID of the number component.
	ID string
}

func (c *NumberConf[T]) SetDefault(default T) *NumberConf[T] {
	c.Default = &default
	return c
}

func (c *NumberConf[T]) SetMin(min T) *NumberConf[T] {
	c.Min = &min
	return c
}

func (c *NumberConf[T]) SetMax(max T) *NumberConf[T] {
	c.Max = &max
	return c
}

func (c *NumberConf[T]) SetStep(step T) *NumberConf[T] {
	c.Step = &step
	return c
}
```

## Example

```go
numberValue := tgcomp.NumberWithConfFloat64(numberCompCol, p.State, "Number",
	(&tgcomp.NumberConf[float64]{
		Placeholder: "input the value here",
		Color:       tcutil.ColorSuccess,
	}).SetMin(10).SetMax(20).SetStep(2))

valStr := ""
if numberValue != nil {
	valStr = fmt.Sprint(*numberValue)
}

tgcomp.TextWithID(numberCompCol, "Value: "+valStr, "number_result")
```
