# MicroMifedomMockAPI

A very simple API deployment, that allows to quickly spin up disparate individual API responders, using a minimally configured nginx image that responds to any route sent to it, providing not much more
than a sanity check for your mifedom's [api-gateway](https://github.com/micro-cosm/micro-mifedom) configuration/testing.

**NOTE:**  Built to work seamlessly with [bin-go](https://github.com/wejafoo/bin-go) mife build/deploy utility

----
### Deploy local api

$   `bingo --local`

### Deploy remote api1, api2

$   `bingo --remote --alias=stage --service=api1`

$   `bingo --remote --alias=stage --service=api2 --route="sapi/api2"`

## Log Levels
    debug:          debugging info about the plugins runloop and each individual plugin or other components.
                    Very chatty like Jeremy said, but useful when debugging, e.g. is plugin xyz running?
    info/notice:    informational log about normal behavior, can mostly be ignored.
                    Kong does not make a big difference between both of these levels (although syslog(2) does).
    warn:           abnormal behavior, not resulting in dropped transactions, but should be investigated.
    error:          an error that resulted in a request being dropped. The client probably received an HTTP 500 response or similar.
                    Monitoring the rate of these logs is important, as they can happen occasionally,
                    but an abnormally high rate of error logs can mean that something is wrong and a large number of clients are suffering from it.
    crit:           Kong is operating in critical conditions; most likely not working for a large number of clients.
                    This log level warrants waking somebody up from your team.
