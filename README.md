# chainlog-ui

UI and API for GSU Protocol’s chainlog contract

- [chainlog-beta.gsuprotocol.io](https://chainlog-beta.gsuprotocol.io)
- [chainlog-beta.gsuprotocol.io/api.html](https://chainlog-beta.gsuprotocol.io/api.html)
- chainlog-beta.gsuprotocol.io/checksum/\<address\>

## Test locally with Docker

1. Make sure that older Docker images are removed, and containers are stopped, if you want to test new code:

```
docker rmi chainlog-ui
docker rmi chainlog-logger
docker rmi chainlog-checksum
```

2. Build the Docker images and start the 3 containers:

```
docker-compose up -d
```

3. Look at the logs:

```
docker logs -f chainlog-ui
docker logs -f chainlog-logger
docker logs -f chainlog-checksum
```

4. Stop the containers:

```
docker-compose down
```

**Note 1:** nginx.conf.template is being customized with the path `/checksum` and copied into the `chainlog-ui` container, for sending traffic to the container running the `checksum.py` script.
**Note 2:**
you can update the addresses by looking at this commit https://github.com/block360/chainlog-ui/commit/71f2591b5d5b82e3b33e5a2d1347a1ef7a4e72af
