# MicroMifedomMockAPI

A very simple API deployment, that allows to quickly spin up disparate individual API responders, using a minimally configured nginx image that responds to any route sent to it, providing not much more
than a sanity check for your mifedom's [api-gateway](https://github.com/micro-cosm/micro-mifedom) configuration/testing.

**NOTE:**  Built to work seamlessly with [bin-go](https://github.com/wejafoo/bin-go) mife build/deploy utility

----
### Deploy local service

$   `bingo --local`

### Deploy remote api service 1, api service 2

$   `bingo --remote --alias=stage --service=api1`

$   `bingo --remote --alias=stage --service=api2 --route="sapi/api2"`
