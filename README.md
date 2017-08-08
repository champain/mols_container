# Mols Container
A project designed to create a docker
container to run the ever-popular mols script
which produces interesting Latin squares.

### Docker service create command
This docker service launches the latin squares script, and accepts two arguments as parameters

0. the order or size of the square the user would like found
1. the full URL to the incoming webhook for slack integration.

```bash
docker service create \
--constraint node.role==worker
--limit-cpu 2.5 \
--no-resolve-image \
--name latin_squares champain/latin_squares:mols_bot \
10 https://hooks.slack.com/services/<slack token here>
```
