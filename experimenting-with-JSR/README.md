We first talked about what JSR is:

- JSR does not try to replace NPM, it is a superset for NPM.
- It helps with modules exporting types
- There is a JSR score when a set of rules is fulfilled, e.g.
  - has a README or module doc
  - has a description
  - no slow types are allowed
    - slow types are types when TS has to figure out return types of functions itself. [read more](https://jsr.io/docs/about-slow-types)
  - ...
- If they'd ever add more rules, there will probably be rather percentages over 100% and the existing packages stay as they are :)
- You can reference NPM in JSR. JSR acts like a separate registry.
- You will still use npm/pnpm/yarn. JSR is not another package manager. It's a registry, not a package manager. NPM is both.

### Demo

We're doing a Demo next:

We're using jsr.io/@std/ as an example (although it got a loooow score of 82%! ;))

In the terminal, we execute:

```bash
mkdir jsr-test
cd jsr-test
npm init -y
npx jsr i
npx jsr add ...
(sorry ran out of time writing it down :)
```

NPM allows you to redirect to another scope, using `npm:` e.g.

```
"dependencies": {
  "@std/fmt": "npm:@jsr/std__fmt@^0.225.4"
}
```

and combined with

```
@jsr:registry=https://npm.jsr.io
```

it goes directly to the JSR endpoints.

A question arises what would happen if someone tries to "steal" a package, e.g. naming it `react-router`. But everything at JSR has to be within a scope (e.g. `@std`). Then JSR can check if the owners are actually the owners before getting approval for the scope.

### Yanking

https://jsr.io/docs/packages#yanking-versions
JSR does not delete specific versions, but you can "yank" them in an archive mode. Then, when already in a lock file, the version can still be downloaded, but new installs cannot happen anymore. You can only delete a version if it is not used anywhere. They are preventing the leftpad situation.
