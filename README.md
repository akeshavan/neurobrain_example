# neurobrain_example

Testing the neuroimage

```bash
git clone https://github.com/akeshavan/neurobrain_example
cd neurobrain_example
npm install
ln -s $PATH_TO_NEUROBRAIN_REPO node_modules/neurobrain #symlink your neurobrain repo so its inside node_modules
npm run dev #
```

and also make sure you have

```bash
cd $PATH_TO_NEUROBRAIN_REPO
yarn dev
```

running. Both are hot reloading, so when you make a change to neurobrain, the examples works as well.

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
