# Atlas-Of-Thrones

An interactive "Game of Thrones" map powered by Leaflet, PostGIS, and Redis.


#### Structure
- `app/` - The front-end web application source.
- `public/` - The compiled and minified front-end code.
- `server/` - The Node.js API server code.
- `data_augmentation/` - A collection of scripts to augment the shapefile data with summary data scraped from various wikis.
- `geojson_preview` - A simple html page to preview geojson data on a map.

#### Setup

To setup the project, simply download or clone the project to your local machine and `npm install`.

You can find a SQL database dump here with all of the content pre-loaded and ready to be queried - https://cdn.patricktriest.com/atlas-of-thrones/atlas_of_thrones.sql

The only extra step is adding a `.env` file in order to properly initialize the required environment variables.

Here's an example `.env` file with sensible defaults for local development -
```
PORT=5000
DATABASE_URL=postgres://patrick@localhost:5432/atlas_of_thrones?ssl=false
REDIS_HOST=localhost
REDIS_PORT=6379
CORS_ORIGIN=*
```

You'll need to change the username in the DATABASE_URL entry to match your PostgreSQL user credentials. Unless your name is "Patrick", that is, in which case it might already be fine.

Run `npm run dev` to start the API server on `localhost:5000`, and to build/watch/serve the frontend code from `localhost:8080`.

Good luck