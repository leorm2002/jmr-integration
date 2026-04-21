## Avvio del cluster
docker compose -f docker-compose.yml up -d
## Tear down del cluster
docker compose -f docker-compose.yml down -v --remove-orphans

## Avvio del job
docker compose --env-file submitter.env -p submit-wc -f docker-compose.submitter.yml up --abort-on-container-exit --exit-code-from submitter submitter
## Cleanup post job
docker compose --env-file submitter.env -p submit-wc -f docker-compose.submitter.yml down -v --remove-orphans