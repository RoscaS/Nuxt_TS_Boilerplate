# nuxt-ts-boilerplate

## Starter

* `npx create-nuxt-app appname`


## Typescript

* `tsc filename.ts`
* `tsc filename.ts --watch`
* `tsc --init` compile all
    *  `tsc --init watch` watch all
    

## Nuxt

### Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

### Invalid component name: "_id"

To avoir this error, the file name in the subfolder of page should be _id.vue but the component name should be changed to `id` 

```
[Vue warn]: Invalid component name: "_id". Component names should conform to valid custom element name in html5 specification.
```

### Axios

* [axios](https://axios.nuxtjs.org/)
* `npm install @nuxtjs/axios`

```js
// nuxt.config.js
module.exports = {
  modules: [
    '@nuxtjs/axios',
  ],

  axios: {
    baseURL: process.env.BASE_URL
  }
}
```

```
// tsconfig.json

{
  "compilerOptions": {
    "types": [
      "@nuxt/types",
      "@nuxtjs/axios"
    ]
  }
}
```
