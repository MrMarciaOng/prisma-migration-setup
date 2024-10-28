## Setup local env

### Set up
```
https://www.prisma.io/docs/orm/prisma-client/setup-and-configuration/introduction

npm install prisma --save-dev
npx prisma

npm install @prisma/client


```


### local bash script setup

```

chmod +x scripts/copy_down_sql.sh
```

### install node_moudles

```
use npm or yarn. but note that nextjs need node v18 and above. Can use NVM to manage the node version on your local machine
```

## Generating SQL migration with Prisma

- Make sure .env for `DATABASE_URL` is pointed to local database
- Make changes to `schema.prisma` file
- Generate revert migration script (down.sql) with command below
- Run `yarn run generate:down` or `npm run generate:down`
- Generate new changes migration script
- Run `yarn run generate:migration` or `npm run generate:migration`
- Bash scripts will auto help you to move the down.sql file into the newly created migration folder

- Run migration changes (migration deploy is way to add changes without nuking data in tables.)
  if you're not sure ask Marcia.

```
npx prisma migrate deploy/dev
```

- Commit changes to git


Take extra care when you're adding migration scripts that may drop existing data columns.