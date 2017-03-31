# e2e-example

```sh
docker run \
  -d \
  --name selenium-hub \
  -p 4444:4444 \
  selenium/hub:3.1

docker run --rm \
  -v /e2e/uploads:/e2e/uploads \
  -e HUB_PORT_4444_TCP_PORT=4444 \
  selenium/node-chrome:3.1

docker run --rm \
  --link selenium-hub:hub \
  -v /e2e/uploads:/e2e/uploads \
  -e HUB_PORT_4444_TCP_PORT=4444 \
  selenium/node-firefox:3.1
```