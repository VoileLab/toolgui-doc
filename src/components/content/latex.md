# Latex

Latex component is used to display LaTeX content.

## API

```go
func Latex(c *tgframe.Container, latex string)
```

* `c` is the container to add the LaTeX component to.
* `latex` is the LaTeX content to display.

## Example

```go
tgcomp.Latex(c, "E = mc^2")
```

