# node-builder
bootstrap a node environment from the package.json of a node project folder.

This image is intended to be the base for other Dockerfile builds.

This container includes an up to date version of node, npm, and n,
installed on ubuntu trusty.

It includes some ONBUILD commands which will run when you use this
as a base for another build.  

1. Copies in your package.json to `/opt/build`
2. uses n to install the version of node listed in the package.json's engines
section
3. Runs `npm install` in `/opt/build`
4. Copies the rest of the current folder into `/opt/build`
5. Sets working directory to `/opt/build`

Default command is `npm test`, but you can run any npm or project commands.
