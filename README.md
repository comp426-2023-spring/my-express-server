# my-express-server

This repo contains a bare-bones logging webserver (with API extensibility) built on ExpressJS.

You can use it to test your HTML and CSS without having to build your own or install another HTTP server.

This is very rudimentary and there are many other similar things out there, but hopefully it will be useful for front-end work.

## Install

To install the package, create a fork, clone the repo, and then run `npm install`.

## Serving HTML and related files

To serve files, put them in the `./public` directory and run the server. 

## Run the server

For testing HTML or related JS and CSS you are actively working on:

```
npm test
```

For the full run instructions, see the help message:
```
usage: node server.js --port=5000

This package serves the static HTML, CSS, and JS files in a /public directory.
It also creates logs in a common log format (CLF) so that you can better.

  --stat,  -s    Specify the directory for static files to be served
                    Default: ./public/
  --port, -p    Specify the port for the HTTP server to listen on
                    Default: 8080
  --log,  -l    Specify the directory for the log files
                    Default: ./log/
  --help, -h    Displays this help message and exit 0 
                    (Does not work when run with nodemon)
  --debug       Echos more information to STDOUT so that you can see what is
                    stored in internal variables, etc.
```

Look also at the script lines in the `package.json`:

```
"scripts": {
    "test": "nodemon -e js,css,html server.js --port=5000 --debug",
    "start": "node server.js",
    "demo": "nodemon -e js,css,html server.js --port=5000 --stat=demo"
  },
```

Using nodemon will let the server reload when you make changes to your HTML, JS, or CSS. 
Otherwise you will have to kill and reload the process.
