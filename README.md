# todos-vue - Udemy - Build A TodoList with Java, Spring Boot and Vue

https://www.udemy.com/course/build-a-todolist-with-java-spring-boot-and-vue/learn/lecture/28872522#overview

## Proxy Setup

- As to Ubuntu, set ignore hosts in Network Proxy Settings

```value
0.0.0.0, localhost, 127.0.0.0/8, ::1
```

## Front-end Development Setup

- Install node.js and npm using nvm

https://github.com/nvm-sh/nvm

```shell
nvm -v
nvm ls-remote
nvm install --lts
nvm list
```

- Install vue cli using npm

https://cli.vuejs.org/guide/installation.html

```shell
npm install -g @vue/cli
vue --version
```

- Install vue-axios for using Axios conveniently to make HTTP requests to back-end server or API

https://www.npmjs.com/package/vue-axios

```shell
npm install --save axios vue-axios
npm list
```

- Install element-plus for high-quality components like buttons, tables, dialogs, etc.

https://element-plus.org/en-US/guide/installation.html#version

```shell
npm install element-plus --save
npm list
npm info element-plus
```

## Blank Front-end Project Setup - vue cli

```shell
vue create todos-vue
````

## IDE Setup

- Install WebStorm

## Project setup to install all dependencies
```
npm install
```

### How to run the vue.js app - Compiles and hot-reloads the front-end app for development
```
npm run serve
```

Visit the app from localhost or another machine
http://localhost:8080/
http://192.168.31.180:8080

### Compiles and minifies for production
```
npm run build
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
