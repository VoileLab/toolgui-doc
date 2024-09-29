# Image

Image component display an image.

## API

```go
func Image(c *tgframe.Container, img image.Image)
func ImageByURI(c *tgframe.Container, uri string)
```

* `c` is Parent container.
* `img` is the image.
* `uri` is the URI form of the image. Example:
  * URL: `https://http.cat/100`
  * base64 uri: `data:image/png;base64,...`

## Example

```go
tgcomp.ImageByURI(p.Main, "https://http.cat/100")
```

![image component](image.png)
