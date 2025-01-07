# Features of the gorilla/mux Router

## Methods

Restrict the request handler to specific HTTP methods.

```bash
r.HandleFunc("/books/{title}", CreateBook).Methods("POST")
r.HandleFunc("/books/{title}", ReadBook).Methods("GET")
r.HandleFunc("/books/{title}", UpdateBook).Methods("PUT")
r.HandleFunc("/books/{title}", DeleteBook).Methods("DELETE")
```

## Hostnames & Subdomains

Restrict the request handler to specific hostnames or subdomains.

```bash
r.HandleFunc("/books/{title}", BookHandler).Host("www.mybookstore.com")
```

## Schemes

Restrict the request handler to http/https.

```bash
r.HandleFunc("/secure", SecureHandler).Schemes("https")
r.HandleFunc("/insecure", InsecureHandler).Schemes("http")
```

## Path Prefixes & Subrouters

Restrict the request handler to specific path prefixes.

```bash
bookrouter := r.PathPrefix("/books").Subrouter()
bookrouter.HandleFunc("/", AllBooks)
bookrouter.HandleFunc("/{title}", GetBook)
```
