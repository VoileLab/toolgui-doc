# Column

Column provides columns layout.

## Usage

- Column create N columns.
- Column2 create 2 columns.
- Column3 create 3 columns.

```go
func Column(c *tgframe.Container, id string, n uint) []*tgframe.Container
func Column2(c *tgframe.Container, id string) (*tgframe.Container, *tgframe.Container)
func Column3(c *tgframe.Container, id string) (*tgframe.Container, *tgframe.Container, *tgframe.Container)
```

* `c`: Parent container.
* `id`: Unique component ID.
* `n`: Number of column.

## Example

```go
cols := tgcomp.Column(colCompCol, "cols", 3)
for i, col := range cols {
	tgcomp.Text(col, fmt.Sprintf("col-%d", i))
}
```
