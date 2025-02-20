# Docker/Turbo issue reproduction repo

This is a repo to reproduce a docker-compose problem for turborepo commands

## To reproduce:

After installing deps with `pnpm i` and having turbo globally installed with `pnpm i turbo@latest -g`:

```sh
turbo dev
```
This will run the `docker compose --build` command in the db package. After it is successfully running, hit cntrl+c and exit out. Inspect the container again. You will notice that the container is still actively running.
If you run pnpm dev from `packages/db`, you will see that the container stops successfully after stopping the process or killing the process entirely. The same should happen for the turbo command.
