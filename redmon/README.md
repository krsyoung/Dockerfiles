# Redmon

Docker image for the Redis web UI [Redmon](https://github.com/steelThread/redmon).
This image has the entry point set to `redmon`.  Just run it with your desired
parameters.  

```
redmon $ docker run --rm -it redmon:latest --help
Usage: /usr/local/bundle/bin/redmon (options)
    -a, --address ADDRESS            The thin bind address for the app (default: 0.0.0.0)
    -b, --base-path BASE_PATH        The base path to expose the service at (default: /)
    -l, --lifespan MINUTES           Lifespan(in minutes) for polled data (default: 30)
    -n, --namespace NAMESPACE        The root Redis namespace (default: redmon)
    -i, --interval SECS              Poll interval in secs for the worker (default: 10)
    -p, --port PORT                  The thin bind port for the app (default: 4567)
    -r, --redis URL                  The Redis url for monitor (default: redis://127.0.0.1:6379, note: password is support, ie redis://:password@127.0.0.1:6379)
    -s, --secure CREDENTIALS         Use basic auth. Colon separated credentials, eg admin:admin.
        --no-app                     Do not run the web app to present stats (default: true)
        --no-worker                  Do not run a worker to collect the stats (default: true)
```
