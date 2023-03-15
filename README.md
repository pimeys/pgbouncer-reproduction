# Reproduction of Problems With PgBouncer

This showcases problems when using Prisma with pgBouncer.

## Setup

Do the npm dance.

```bash
> npm i --save-dev
```

Start the bouncer and the database with `docker`:

```bash
> docker compose up -d
```

At this point, running migrations should always fail:

```bash
> npx prisma migrate dev
```

This will give you a problem dropping shadow database.

To move forward with our tests, we can use `db push` that works fine:

```bash
> npx prisma db push
```

Now, execute the test script a few times, until it crashes:

```bash
> npx ts-node script.ts
```