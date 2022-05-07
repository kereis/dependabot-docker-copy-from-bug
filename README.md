# Example repository for Dependabot not respecting Docker images used in `COPY`

> See issue https://github.com/dependabot/dependabot-core/issues/5103

This reproduces a possible current issue with Dependabot where Docker images used in a `COPY --from` statement inside Dockerfiles are not picked up. This results in Docker images not being updated.

## Steps to reproduce
1. Clone this repository
2. Push it to your own repository
3. Wait until Dependabot ran a scan for dependency updates
4. Check pull requests and check if the pull request for `Dockerfile.docker` suggests updating `ldez/traefik-certs-dumper` used in the `COPY --from` statement