# Fileupload

Fileupload create a fileupload and return its selected file.

## API

```go
type FileObject struct {
	Name string `json:"name"`
	Type string `json:"type"`
	Size int    `json:"size"`

	Bytes []byte `json:"_"`
}

func Fileupload(s *tgframe.State, c *tgframe.Container, label string) FileObject
```

* `s` is State.
* `c` is Parent container.
* `label` is the label for options group.

## Example

```go
fileObj := tgcomp.Fileupload(p.State, p.Main, "Fileupload")
tgcomp.Text(p.Main, "Fileupload filename: "+fileObj.Name)
tgcomp.Text(p.Main, fmt.Sprintf("Fileupload bytes length: %d", len(fileObj.Bytes)))
```

![fileupload component](fileupload.png)
