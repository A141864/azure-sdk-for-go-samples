# Azure SDK for Go - Samples

azure-sdk-for-go-samples provides easy-to-understand, continuously-tested samples for using Azure services via [Azure/azure-sdk-for-go][]. These are currently targeting
Go SDK For Azure **v14.0.0**.

[![Build Status](https://travis-ci.org/Azure-Samples/azure-sdk-for-go-samples.svg?branch=master)](https://travis-ci.org/Azure-Samples/azure-sdk-for-go-samples)

The goal of this project is to provide a library of code snippets for common
and not-so-common operations in Azure via the Go SDK. Code is organized by
services as well as snippet type. The repo will continue to be testable to
ensure our samples reflect current recommendations and best practices!

Read the [main SDK README][] for more help getting started with the Go SDK.

## To run tests

1. Set the following environment variables (those marked * are required). Use
the following instructions to find or create these values if necessary.

    * `AZURE_SUBSCRIPTION_ID`*
    * `AZURE_TENANT_ID`*
    * `AZURE_CLIENT_ID`*
    * `AZURE_CLIENT_SECRET`*
    * `AZURE_SP_OBJECT_ID`
    * `AZURE_LOCATION`
    * `AZURE_RESOURCE_GROUP_PREFIX`
    * `AZURE_KEEP_SAMPLE_RESOURCES`

    Using [the Azure CLI][azure-cli], you can get your subscription ID by running `az account
    list`. You can check your tenant ID and get a client ID and secret by
    running `az ad sp create-for-rbac -n "<yourAppName>"`.

    If `AZURE_RESOURCE_GROUP_PREFIX` isn't specified, `azure-samples-go` will be used.

    If `AZURE_LOCATION` isn't specified `westus2` will be used.

    If `AZURE_KEEP_SAMPLE_RESOURCES` is set to `1` tests won't clean up resources
    they create when done. This can be helpful if you want to further experiment
    with those resources.

    `AZURE_SP_OBJECT_ID` represents a service principal ObjectID. It is needed to run the Create VM with encrypted managed disks sample.

    **NOTE:** the environment variables are listed in [.env.tpl](./.env.tpl)
    so you can copy that to .env (e.g. `cp .env.tpl .env`) and update for
    convenience. The samples pick up environment variables from .env files
    automatically.

1. Run `dep ensure` to get dependencies.
1. Run tests with `go test` as follows:

    1. To run individual samples, refer to that folder, e.g. `go test ./storage/`, `go test ./network/`.
        * If you use a .env file, copy it into the folder first, e.g. `cp .env ./network/`.
    1. If you're feeling lucky and want to test all the samples, try `go test ./...`
        * This only requires the root .env file.

# Resources

- SDK code is at [Azure/azure-sdk-for-go][].
- SDK docs are at [godoc.org](https://godoc.org/github.com/Azure/azure-sdk-for-go/).
- SDK notifications are published via the [Azure update feed][].
- Azure API docs are at [docs.microsoft.com/rest/api](https://docs.microsoft.com/rest/api/).
- General Azure docs are at [docs.microsoft.com/azure](https://docs.microsoft.com/azure).

# License

This code is provided under the MIT license. See [LICENSE][] for details.

# Contribute

We welcome your contributions! For instructions and our code of conduct see [CONTRIBUTING.md][]. And thank you!

[main SDK README]: https://github.com/Azure/azure-sdk-for-go/blob/master/README.md
[Azure update feed]: https://azure.microsoft.com/updates/
[Azure/azure-sdk-for-go]: https://github.com/Azure/azure-sdk-for-go
[azure-cli]: https://github.com/Azure/azure-cli
[LICENSE]: ./LICENSE.md
[CONTRIBUTING.md]: ./CONTRIBUTING.md
