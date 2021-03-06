---
layout: "acme"
page_title: "ACME: IIJ DNS Challenge Provider"
sidebar_current: "docs-acme-dns-providers-iij"
description: |-
  Provides a resource to manage certificates on an ACME CA.
---

# IIJ DNS Challenge Provider

The `iij` DNS challenge provider can be used to perform DNS challenges for
the [`acme_certificate`][resource-acme-certificate] resource with
[IIJ][provider-service-page].

[resource-acme-certificate]: /docs/providers/acme/r/certificate.html
[provider-service-page]: https://www.iij.ad.jp

For complete information on how to use this provider with the `acme_certifiate`
resource, see [here][resource-acme-certificate-dns-challenges].

[resource-acme-certificate-dns-challenges]: /docs/providers/acme/r/certificate.html#using-dns-challenges

## Example

```hcl
resource "acme_certificate" "certificate" {
  ...

  dns_challenge {
    provider = "iij"
  }
}
```

## Argument Reference

The following arguments can be either passed as environment variables, or
directly through the `config` block in the
[`dns_challenge`][resource-acme-certificate-dns-challenge-arg] argument in the
[`acme_certificate`][resource-acme-certificate] resource. For more details, see
[here][resource-acme-certificate-dns-challenges].

[resource-acme-certificate-dns-challenge-arg]: /docs/providers/acme/r/certificate.html#dns_challenge

* `IIJ_API_ACCESS_KEY` - The API access key to use.
* `IIJ_API_SECRET_KEY` - The API secret key to use.
* `IIJ_DO_SERVICE_CODE` - The service code of DNS outsource service to use.

The following additional optional variables are available:

* `IIJ_POLLING_INTERVAL` - The amount of time, in seconds, to wait between
  DNS propagation checks (default: `4`).
* `IIJ_PROPAGATION_TIMEOUT` - The amount of time, in seconds, to wait for DNS
  propagation (default: `120`).
* `IIJ_TTL` - The TTL to set on DNS challenge records, in seconds (default:
  `300`).
