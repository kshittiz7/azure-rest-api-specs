## Go

These settings apply only when `--go` is specified on the command line.

``` yaml $(go) && $(track2)
license-header: MICROSOFT_MIT_NO_VERSION
module-name: sdk/resourcemanager/datafactory/armdatafactory
module: github.com/Azure/azure-sdk-for-go/$(module-name)
output-folder: $(go-sdk-folder)/$(module-name)
azure-arm: true
directive:
  - from: swagger-document
    where: $.definitions.LinkedServiceReference.properties.type
    debug: true
    transform: >
      $["x-ms-enum"].name = "LinkedServiceReferenceType"
```
