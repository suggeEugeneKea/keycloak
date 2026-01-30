# Devices data

This [data](./pkg/combined_data.go) file is automatically fetched and generated from netbox's [devicetype-library](https://github.com/netbox-community/devicetype-library). Current version is matched with latest [commit](./sha.txt) on master branch.

For more info see [generator](/cmd/generator/generator.go).

## Usage

```go
package main

import (
  "fmt"

  devices "github.com/src-doo/go-devicetype-library/pkg"
)

func main() {
  for manufacturer, deviceType2device := range devices.DeviceTypesMap {
    fmt.Printf("Manufacturer: %s\n", manufacturer)
    for deviceType, device := range deviceType2device {
      fmt.Printf("Device Type[%s]: %+v\n", deviceType, device)
    }
  }
}
```
