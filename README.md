# GraphQL 16 resolution example

This is a minimal reproduction of the issue resolving `graphql@16.x` as a peerDependency within `apollo-server-express`.

## Running instructions

```bash
yarn install
```

You should see a console output similar to...

![output](/screenshots/output.png)

And running `yarn explain peer-requirements <hash>` yields...

![explain](/screenshots/explain.png)

So the problematic area seems to be an incorrect peerDependency inside `@apollographql/apollo-tools@0.5.2`. Strangely,
that package does not seem to have any listed peerDependencies, so I'm a bit stumped.
