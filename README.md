# twt-nextjstemplate
Simple template of an empty next.js project that has some preconfigured stuff like security.txt and support for docker.

# usage
This project can be run/host directly or via docker.

## Run via locally
To run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Run via docker
To run the production server via docker:

`docker build -t twt-nextjstemplate .`

`docker run -p 3000:3000 twt-nextjstemplate`

# Setup
The following additional options are added:

## Robots
An example of the robots.txt is already added. This can be found on [http://localhost:3000/robots.txt](http://localhost:3000/robots.txt)

## Security.txt
An example of the security.txt is already added. This can be found on [http://localhost:3000/.well-known/security.txt](http://localhost:3000/.well-known/security.txt) 

## Headers
- An example header is added in the middleware
- The default powered by header is removed in next.config.js

## Rate limiting
A very simple rate limiter that is not dependent on any external packages is added. An example of an API that is 
rate limited to 10 request per minute can be found at [http://localhost:3000/api/example](http://localhost:3000/api/example). 

When the limit is hit a 429 (Too Many Requests) response will be returned. The limit and `x-ratelimit-limit` remaining limit `x-ratelimit-remaining` will be added as headers.