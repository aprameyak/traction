# Traction

A small tool for comparing side projects by return on time. Enter the hours you have put into each project and the revenue it has made, and see them ranked by dollars per hour.

## Features

- Log a project with hours invested and revenue generated
- Revenue per hour is calculated for each project
- Projects are ranked from highest to lowest return per hour
- Returns above $100 per hour are highlighted in green, the rest in red
- Entries are saved to a local JSON file

## Getting started

Requires Node.js.

```bash
npm install
npm start
```

Then open http://localhost:3009. `npm run dev` runs the same command.

## How it works

- `index.html` contains the project form and the ranked list. It calls the API at `http://localhost:3009`.
- `server.js` is an Express app that serves the page and exposes:
  - `POST /api/projects` to save a project and compute its revenue per hour.
  - `GET /api/projects` to return all projects sorted by that figure.
- Data is written to `data.json`, created on first run and ignored by git.
- `utils.js` holds validation and file helpers that are not yet wired into `server.js`.

## Status

Prototype. Single user, numbers entered by hand, no editing or deleting from the UI.

## License

MIT, see [LICENSE](LICENSE).
