# App Cache

An app-level cache stores data for the entire duration of the application's execution,
from launch to termination.

This cache is not provided by ToolGUI and needs to be implemented by the developer.

For example:

```go
type App1 struct {
	sync.Map data
}

func (app *App) QueryData(key string) {
	if v, ok := data.Load(key); ok{
		return v
	}

	// ...
	v, _ := data.LoadOrStore(key, calVal)
	return v
}

func (app *App) Page1(...) {
	tgcomp.text(app.QueryData(...))
}
```

Additional Considerations:

- Cache Invalidation: As the application runs, the underlying data sources might change. It's crucial to have a strategy to invalidate cached data when necessary to ensure consistency. This could involve periodically refreshing the cache or implementing mechanisms to detect changes in the source data.

- Memory Usage: App-level caches can consume memory. It's essential to choose appropriate data structures and cache eviction policies to balance performance gains with memory constraints.
