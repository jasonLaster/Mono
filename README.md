# Mono

Sample mono repo that shows how an application could have local
packages that are not published to npm.

Steps to try it out:

1. `git clone https://github.com/jasonLaster/Mono`
2. `npm install`
3. `node src/main`

:star2: :star:

#### Directory Structure

- `src` application directory
- `packages/<packages>` packages directory

#### Examples

* [VSCode](https://github.com/Microsoft/vscode) has a `src` and `extensions` dir
* [Nuclide](https://github.com/facebook/nuclide) has a `pkg` and `modules` dirs


#### Alternative - Shared Directory

The alternative is to have a `shared` directory without packages e.g. `shared/<foo>/index.js`. Modules can depend on foo, by requiring it directly. e.g. `../shared/foo`.

#### Advantages of Packages

* It is easier for the application to bundle packages.
* It is easier for the application to exclude *shim* packages
* Packages are more natural for tools like *license checker* or *launchpad*
* It is easier to express dependency dependencies e.g. `foo` depends on `bar`
* It is possible to publish a package
* It is easier to have separate package tooling, e.g. `devtools-components` uses storybook...

#### Questions

**Can packages be published?** Yes, but the application depends on the current version of the package.

**Are changes in a package linked?** Yes, npm/yarn add symlinks in the top-level `node_modules` dir.
