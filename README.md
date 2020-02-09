# Go Uwaterloo API
Client for UWaterloo Open Data API, written in Golang

## Installation
Using go modules:

```
go get github.com/dhillondeep/go-uw-api
```

## Dependencies
This wrapper depends on [gabs package](https://github.com/Jeffail/gabs), so go get gabs (pun intended) first.

## Usage

```golang
package main

import uwapi "github.com/dhillondeep/go-uw-api"

func main() {
    // api key needed; get it from https://uwaterloo.ca/api/register
    uw := uwapi.Create(API_KEY)
    jsonObj, _ := uw.FoodServices.Menu()
}
```

Then do whatever with the returned `*gabs.Container` (check out their docs for getting, setting, etc...).

As seen in the example, the structs (e.g. `FoodServices`) are all named appropriately, 
i.e. the same as they are in the UW API's docs. However, the methods are not always of the same name due to conflicts or parameters.

All methods return a `*gabs.Container` and an `error` (or `nil`).

Check out the [documentation](https://godoc.org/github.com/SaintDako/uwAPI.go) for more info.

## TODO

- add tests