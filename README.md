# Bookinfo for Conusl Service Mesh

## Overview

These examples deploy Istio's [Bookinfo application](https://istio.io/latest/docs/examples/bookinfo/) and then adapt it to demonstrate Consul's [Service Mesh](https://developer.hashicorp.com/consul/docs/connect) functionality.

This deploys the following microservices:

- **productpage**: calls details and reviews services to populate the pages
- **details**: provides book information
- **reviews**: calls the ratings service to provide book reviews and the "star" ratings
- **ratings**: provides book ranking information through the reviews service

The reviews service has three versions:

- **v1**: does not call the ratings service
- **v2**: calls ratings service, displays ratings as 1 to 5 black stars
- **v3**: calls ratings service, displays ratings as 1 to 5 red stars

## Dependencies

All of these examples use the following images:

```bash
docker.io/istio/examples-bookinfo-details-v1:1.17.0
docker.io/istio/examples-bookinfo-productpage-v1:1.17.0
docker.io/istio/examples-bookinfo-ratings-v1:1.17.0
docker.io/istio/examples-bookinfo-reviews-v1:1.17.0
docker.io/istio/examples-bookinfo-reviews-v2:1.17.0
docker.io/istio/examples-bookinfo-reviews-v3:1.17.0
```

All examples are tested with Consul 1.15.0 but might work with earlier versions too.
