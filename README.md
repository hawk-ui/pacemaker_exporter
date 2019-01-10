# Pacemaker exporter

[Prometheus](https://prometheus.io/) exporter for [Pacemaker](https://github.com/ClusterLabs/pacemaker) cluster resource manager.

## Getting

```
$ go get github.com/hawk-ui/pacemaker_exporter
```

## Building

```
$ cd $GOPATH/src/github.com/hawk-ui/pacemaker_exporter
$ make
```

## Running

```
$ ./pacemaker_exporter <flags>
```
Note: Please run it as *root* user, otherwise `crm_mon` will be failing.

## Endpoints

 1. http://localhost:9356/metrics for the Prometheus metrics.
 2. http://localhost:9356/html for a HTML cluster status page.
 2. http://localhost:9356/xml for a XML cluster status page.

## What's exported?

This exporter run `crm_mon -X`, and parse its XML output.

|   XML element    |     Status      | Default |
|:----------------:|:---------------:| :------:|
| summary          | implemented     | enabled |
| nodes            | implemented     | enabled |
| node_attributes  | implemented     | enabled |
| node_history     | not implemented |         |
| resources        | implemented     | enabled |
| resources/bundle | not implemented |         |
| resources/group  | implemented     | enabled |
| resources/clone  | not implemented |         |
| tickets          | not implemented |         |
| bans             | implemented     | enabled |
| failures         | implemented     | enabled |
