# odev_task 
#####by Idel Ishaev, i.ishbaev@innopolis.unniversity
1. You need to install [Docker](https://www.docker.com/)
2. Clone this project on your computer
3. With terminal go to directory web_app_swp
4. In terminal run
###hint:
#####"odev_task" - filename 
#####"odev_task-1" - filename+"-1"
```
docker build -t odev_task .
docker run -it -p 8080:8080 --rm --name odev_task-1 odev_task
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
