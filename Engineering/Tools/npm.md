# npm install
- installs dependencies and their peer dependencies
- adds them to `node_modules`
- adds them to machine-local cache
## npm ci
- installs exactly the tree from `package-lock.json`
## peer dependencies
### conflicts
- two or more dependencies need a package in a different version
## --legacy-peer-deps
- peer-dependencies are ignored and skipped from the [installation process](https://docs.npmjs.com/cli/v7/using-npm/config#legacy-peer-deps)
- recommended option to use
- could also lead to missing packages
- `npm config set legacy-peer-deps=true --location=project`
### --force
- does not skip the peer-dependencies, but rather installs all associated _peer-dependency_ versions instead
## Installing dependencies from scratch
```bash
// remove the local node_modules folder  
rm -rf node_modules  
// remove all cached dependencies  
npm cache clean --force  
npm install --force
```



# References
[npm ci vs npm install](https://blog.bitsrc.io/stop-using-npm-install-in-your-ci-cd-pipeline-ba0378bbebfb)