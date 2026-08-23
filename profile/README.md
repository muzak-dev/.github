# Muzak

A type-safe web framework for Go, and the things around it.

A handler is an ordinary typed function. Its input type is the request, its
return type is the response body, and both are checked when you compile rather
than when a request arrives.

```go
type Params struct {
    Username string `path:"username" doc:"The username to look up"`
}

type UserOut struct {
    Username string `json:"username"`
}

r.Get("/users/{username}", func(ctx *muzak.Context, in Params) (UserOut, error) {
    return UserOut{Username: in.Username}, nil
})
```

```bash
go get muzak.dev/framework
```

## Repositories

| | |
| [**framework**](https://github.com/muzak-dev/framework) | The framework. Routing, binding, validation, dependency injection, WebSockets, server-sent events, rate limiting and OpenAPI 3.1 generation, built on `net/http` with no third-party dependencies. |
| [**muzak.dev**](https://github.com/muzak-dev/muzak.dev) | The landing page and the documentation at [muzak.dev/docs](https://muzak.dev/docs). |
| [**openapi**](https://github.com/muzak-dev/openapi) | A standalone API reference and request console that reads a service's OpenAPI document. Work in progress. |

## Links

- Documentation: [muzak.dev/docs](https://muzak.dev/docs)
- Package reference: [pkg.go.dev/muzak.dev/framework](https://pkg.go.dev/muzak.dev/framework)
- Machine-readable docs: [muzak.dev/llms.txt](https://muzak.dev/llms.txt)
