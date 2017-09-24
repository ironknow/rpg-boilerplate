# RPG Boilerplate
## Relay, PostgreSQL, Graphile (GraphQL)
###### A Modern Frontend and API Boilerplate

This boilerplate provides a starting point for developers, especially the community of [PostgraphQL](https://github.com/calebmer/postgraphql/) developers, to build applications powered by Relay Modern.

[GraphQL](http://graphql.org/) and [Relay Modern](https://facebook.github.io/relay/docs/relay-modern.html) 
allow fast, modular apps.  For more on how they work, check out the respective links.

-----
#### Requirements
* [Docker Compose](https://docs.docker.com/compose/) (tested on v1.14.0)
* [Node](https://nodejs.org) (tested on v8.5.0)
* [Yarn](https://yarnpkg.com) (tested on v0.27.5)
* [Sqitch](https://github.com/theory/sqitch) (tested on v0.9995)

#### Installation
```
# clone down the code
git clone https://github.com/chadfurman/rpg-boilerplate.git

# enter into the folder
cd rpg-boilerplate

# install dependencies
cd api && yarn install && cd ../frontend && yarn install && cd ../

# start docker to prep db
docker-compose up 

# after db init, ctrl-c

# deploy migrations to db
sqitch deploy

```

## Running
```
# Start the app
cd rpg-boilerplate
docker-compose up
```

## Development
### Overview
The application is divided into two primary directories: `/api` and `/frontend`

The frontend folder  is further divided into three main parts: 
* `client` is the code that renders in the browser w/o the SSR server
* `server` is the code that runs on the SSR server
* `shared` is the code that runs on both, and is responsible for the UI of the website.

> **NOTE**: Given that the client and server folders are pretty barren and the code therein is somewhat straight-forward, they do not require much explanation.  Take a look and see :)

### Shared Folder
The shared folder is broken up as follows:
* `components` - these are the bulk of the UI elements of the site.  Each component stores its own **stylesheet, images, JavaScript, and data dependency declarations**
* `relay` - houses the apiManager (sets/cancels our JWT during transit) and all of our mutations (queries are built into the components)
* `routes` - Each route file must be manually linked in `routes.js` -- more on routes below.
* `templates` - These are the general skeleton elements that multiple views will share
* `theme` - this folder contains global assets (like a background, not like a logo), and global CSS (reset rules, utility styles, scss variabls)
* `views` - these are the root component rendered for a route.  Each route has a view.  Each view is used by only one route.  Reusable aspects of views should be components.
* `App.js` - This separates public and private routes from eachother, querying for the currentProfile to determine if we're logged in or not.
* `BaseError.js` - An extensible error class
* `routes.js` - exports an array of imported route files to be matched by the SSR server and iterated over in App.js

### To add a new route
TODO

### To add a new mutation
TODO

### To add a new component
TODO

### To add a new view
TODO

### To add a new migration
TODO

### To rework an existing migration
TODO

### To extend the GraphQL API
TODO

5. 
```
