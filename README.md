## Avvio del cluster
docker compose -f docker-compose.yml up -d
## Avvio del job
docker compose --env-file submitter.env -p submit-a -f docker-compose.submitter.yml up --abort-on-container-exit --exit-code-from submitter submitter