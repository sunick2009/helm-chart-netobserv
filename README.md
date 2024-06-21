# netObserv Helm Chart

- [Overview](#overview)
- [Installation](#installation)
- [Configuration](#configuration)

## Overview

The ElastiFlow Unified Flow Collector receives, decodes, transforms, normalizes, translates and enriches network flow records and telemetry sent from network devices and applications using IPFIX, Netflow, sFlow and AWS VPC Flow Logs. The resulting records can be sent to various platforms and services, including:

- Elasticsearch
- Elastic Cloud
- Elastic Cloud Enterprise
- OpenSearch
- AWS OpenSearch Service
- Apache Kafka
- Confluent Platform
- Redpanda
- Splunk
- Cribl Stream

## Installation

```sh
helm repo add elastiflow https://elastiflow.github.io/helm-chart-netobserv/
helm repo update
helm install netobserv elastiflow/netobserv
```

## Configuration

### License Setup

To configure an ElastiFlow Account ID and License key, you can add the following to your `values.yaml`:

```yaml
license:
  createSecret: true
```

Then make sure to use helm's `set` option to configure the account id and license key when installing the chart. For example:

```sh
helm install netobserv elastiflow/netobserv --set license.licenseKey="licensekeygoeshere" --set license.accountId="accountidgoeshere"
```

For additional configuration secrets, please refer to the [configuration reference guide](https://docs.elastiflow.com/docs/config_ref/).
