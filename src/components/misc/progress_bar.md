# Progress Bar

ProgressBar is a component that displays a progress bar.

## API

### Interface

```go
func ProgressBar(c *tgframe.Container, value int, label string) *ProgressBarComponent
```

### Parameters

* `c`: Parent container.
* `value`: Value of the progress bar.
* `label`: Label of the progress bar.

## Example

```go
bar := tgcomp.ProgressBar(c, 50, "Progress")
for i := 0; i <= 100; i++ {
	bar.SetValue(i)
	time.Sleep(100 * time.Millisecond)
}

bar.SetLabel("Completed")
```
