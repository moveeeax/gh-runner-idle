# gh-runner-idle

> Too few runners, or the right runners wearing the wrong labels.

**Status:** 🚧 In development

## Overview

Report self-hosted runner utilization, queue wait time and idle cost, answering whether the fleet is too small or simply mis-labelled.

## Features

- Samples runner state from the Actions API and joins it against queued and running jobs
- Splits queue wait into "no free capacity" and "no runner carries these labels"
- Utilization per label set and per runner group, bucketed hourly so peaks show up
- Idle cost estimate from an hourly rate you supply per runner group
- Names the mis-labelled case directly: jobs waiting while idle runners sit available
- Prometheus metrics endpoint alongside the one-shot report, for continuous tracking

## Stack

Go + go-github, prometheus/client_golang, cobra, olekukonko/tablewriter.

## Usage

```bash
gh-runner-idle --org example-org --since 7d --hourly-rate 0.096 --format table
```

## License

MIT
