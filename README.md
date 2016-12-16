# golibvue
Vue.js inside a go variable, to compile the library with go

## Install

```
go get github.com/as27/golibvue
```

## Usage http server

The Handler() function makes it easy to include vuejs by just setting a route.

```Go
func main() {
    // With github.com/gorilla/mux
    router := mux.NewRouter()
    //Set a simple route and add the hanlder
    router.HandleFunc(`/lib/vue.min.js`, golibvue.Handler).Methods("GET")
    http.ListenAndServe(":1234", router)
}
```

Now vue.js is ready to use at http://localhost:1234/lib/vue.min.js. No additional files are needed. Everything is compiled into the executable.