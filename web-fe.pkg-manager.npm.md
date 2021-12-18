---
id: vn2rdYADJbL87dT0B1gcp
title: Npm
desc: ''
updated: 1639846042813
created: 1639838780065
---

# How to test a developing module

Can use softlink to this. Both yarn and npm have this `link` help do this.
But the ultimate solution is `monorepo` (Tools like lerna and turborebo are monorepo manager, but we won't expand it here).

# Using npm

## Registry

To resolve packages by name and version, npm talks to a registry website that implements the CommonJS Package Registry specification for reading package info. Npm is configured to use the npm public registry at https://registry.npmjs.org by default.  
You can configure npm to use any compatible registry you like, and even run your own registry.  
The npm public registry is powered by a CouchDB database.

**The registry URL used is determined by the scope of the package** (see [scope](#Scope). If no scope is specified, the default registry is used, which is supplied by the registry config parameter. See [npm config](https://docs.npmjs.com/cli/v8/commands/npm-config), [npmrc](https://docs.npmjs.com/cli/v8/configuring-npm/npmrc), and [config](https://docs.npmjs.com/cli/v8/using-npm/config) for more on managing npm's configuration.

### Prevent package from being published in the official registry

Set `"private": true` in your package.json to prevent it from being published at all, or `"publishConfig":{"registry":"http://my-internal-registry.local"}` to force it to be published only to your internal/private registry.

## Scope

Scopes are a way of grouping related packages together, and also affect a few things about the way npm treats the package.  
When used in package names, scopes are preceded by an @ symbol and followed by a slash, e.g.

> @somescope/somepackagename

Each npm user/organization has their own scope, and only you can add packages in your scope. This means you don't have to worry about someone taking your package name ahead of you. Thus it is also a good way to signal official packages for organizations.

## Associat a scope with a registry

Scopes can be associated with a separate registry. This allows you to seamlessly use a mix of packages from the primary npm registry and one or more private registries.

You can associate a scope with a registry at login, e.g.

> npm login --registry=http://reg.example.com --scope=@myco

Scopes have a many-to-one relationship with registries: one registry can host multiple scopes, but a scope only ever points to one registry.  
You can also associate a scope with a registry using npm config:

> npm config set @myco:registry http://reg.example.com

Once a scope is associated with a registry, any `npm install` for a package with that scope will request packages from that registry instead. Any `npm publish` for a package name that contains the scope will be published to that registry instead.
