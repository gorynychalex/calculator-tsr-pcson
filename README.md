# calc-tsr

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### Compiles and minifies for production
```
yarn run build
```

### Run your tests
```
yarn run test
```

### Lints and fixes files
```
yarn run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### My project created
```
/home/gorynych/.config/yarn/global/node_modules/@vue/cli/bin/vue.js create calc-tsr
```

### Deploy App
See [Docker (Nginx)](https://cli.vuejs.org/guide/deployment.html#docker-nginx)

```
docker build . -t calctsr-pcson
```

```
scp calctsr-pcson.tar <host>:/home/gorynych/
```

```
docker load -i calctsr-pcson.tar 
```

```
docker run -d -p 8090:80 calctsr-pcson
```
