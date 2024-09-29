# State Cache

State-level cache stores data specific to the current view or "page" displayed to the user.
This data lost when the user navigates away from the page or refreshes it.

Here we provide a state-level TODO App example.
It stores list of todos in the state:

```go
func Main(p *tgframe.Params) error {
	tgcomp.Title(p.Main, "Example for Todo App")

	var todos []string
	err := p.State.GetObject("todos", &todos)
	if err != nil {
		return err
	}

	inp := tgcomp.Textbox(p.State, p.Main, "Add todo")
	if tgcomp.Button(p.State, p.Main, "Add") {
		todos = append(todos, inp)
		p.State.Set("todos", todos)
	}

	for i, todo := range todos {
		tgcomp.TextWithID(p.Main,
			fmt.Sprintf("%d: %s", i, todo),
			fmt.Sprintf("todo_%d", i))
	}

	return nil
}
```
