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

## Blank Front-end Project Setup - vue cli

```shell
vue create todos-vue
````

## IDE Setup

- Install WebStorm

## Project setup to install all dependencies
```
yarn install
```

### Compiles and hot-reloads the front-end app for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
