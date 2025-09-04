# rabbit-test
Scaling test for RabbitMQ in compose environment

Run:
```bash
docker compose -f docker-compose.yaml up -d
```

UI for RabbitMQ is exposed at http://localhost:15672 and for HAProxy is at http://localhost:8404.


To test if scaling works, use:
```bash
docker run -it --rm --network host pivotalrabbitmq/perf-test:latest --uri amqp://guest:guest@localhost -s 500
```

To compare, uncomment commented nodes 3 and 4 in docker-compose.yaml (don't forget L81 andL82), haproxy.cfg and rabbitmq.conf, and run the same command again.

